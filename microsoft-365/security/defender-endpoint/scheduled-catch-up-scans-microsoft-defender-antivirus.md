---
title: 使用扫描计划定期快速和完全Microsoft Defender 防病毒
description: 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 常规
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789264"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="04ebe-104">配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="04ebe-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="04ebe-105">**Applies to:**</span></span>

- [<span data-ttu-id="04ebe-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04ebe-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="04ebe-107">默认情况下，Microsoft Defender 防病毒扫描前 15 分钟检查更新。</span><span class="sxs-lookup"><span data-stu-id="04ebe-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="04ebe-108">你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。</span><span class="sxs-lookup"><span data-stu-id="04ebe-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="04ebe-109">除了始终打开实时保护和按需扫描之外，还可以设置[](run-scan-microsoft-defender-antivirus.md)定期计划扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="04ebe-110">可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后发生还是使用终结点。 [](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="04ebe-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="04ebe-111">还可以指定应何时进行特殊扫描以完成修正。</span><span class="sxs-lookup"><span data-stu-id="04ebe-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="04ebe-112">本文介绍如何使用组策略、PowerShell cmdlet 和 WMI 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="04ebe-113">还可以配置计划[扫描，Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)[或](/mem/intune/configuration/device-restrictions-windows-10)Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="04ebe-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="04ebe-114">配置本文中所述的组策略设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="04ebe-115">在组策略管理计算机上，在组策略编辑器中，转到计算机配置管理模板 Windows 组件 Microsoft Defender 防病毒  >    >    >    >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="04ebe-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="04ebe-116">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="04ebe-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="04ebe-117">指定组策略对象的设置，**然后选择确定。**</span><span class="sxs-lookup"><span data-stu-id="04ebe-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="04ebe-118">对要配置的每个设置重复步骤 1-4。</span><span class="sxs-lookup"><span data-stu-id="04ebe-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="04ebe-119">像平常一样部署组策略对象。</span><span class="sxs-lookup"><span data-stu-id="04ebe-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="04ebe-120">如果需要有关组策略对象的帮助，请参阅 [创建组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="04ebe-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="04ebe-121">另请参阅 [管理何时应下载](manage-protection-update-schedule-microsoft-defender-antivirus.md) 和应用保护更新和阻止或允许用户 [在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="04ebe-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="04ebe-122">快速扫描与完全扫描和自定义扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="04ebe-123">设置计划扫描时，可以设置扫描应为完全扫描还是快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="04ebe-124">快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-124">Quick scan</span></span>  |<span data-ttu-id="04ebe-125">完全扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-125">Full scan</span></span>  | <span data-ttu-id="04ebe-126">自定义扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="04ebe-127">快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。</span><span class="sxs-lookup"><span data-stu-id="04ebe-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="04ebe-128">在大多数情况下，快速扫描已足够，建议用于计划扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="04ebe-129">完整扫描首先运行快速扫描，然后继续针对所有已装载的固定磁盘和可移动/网络驱动器进行连续文件扫描 (如果完全扫描配置为) 。</span><span class="sxs-lookup"><span data-stu-id="04ebe-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="04ebe-130">完整扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据的数量和类型。</span><span class="sxs-lookup"><span data-stu-id="04ebe-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="04ebe-131">完成完整扫描后，新的安全智能可用，并且需要新扫描以确保新安全智能不会检测到任何其他威胁。</span><span class="sxs-lookup"><span data-stu-id="04ebe-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="04ebe-132">自定义扫描是在指定的文件和文件夹上运行的快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="04ebe-133">例如，你可以选择扫描 USB 驱动器或设备本地驱动器上的特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="04ebe-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="04ebe-134">默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。</span><span class="sxs-lookup"><span data-stu-id="04ebe-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="04ebe-135">我如何知道要选择哪个扫描类型？</span><span class="sxs-lookup"><span data-stu-id="04ebe-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="04ebe-136">使用下表选择扫描类型。</span><span class="sxs-lookup"><span data-stu-id="04ebe-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="04ebe-137">应用场景</span><span class="sxs-lookup"><span data-stu-id="04ebe-137">Scenario</span></span>  |<span data-ttu-id="04ebe-138">推荐的扫描类型</span><span class="sxs-lookup"><span data-stu-id="04ebe-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="04ebe-139">想要设置定期计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="04ebe-140">快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-140">Quick scan</span></span> <p><span data-ttu-id="04ebe-141">快速扫描检查设备上的过程、内存、配置文件和特定位置。</span><span class="sxs-lookup"><span data-stu-id="04ebe-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="04ebe-142">与 [始终开启的](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="04ebe-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="04ebe-143">实时保护在打开和关闭文件时以及用户导航到文件夹时检查文件。</span><span class="sxs-lookup"><span data-stu-id="04ebe-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="04ebe-144">在单个设备上检测到恶意软件等威胁</span><span class="sxs-lookup"><span data-stu-id="04ebe-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="04ebe-145">快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-145">Quick scan</span></span> <p><span data-ttu-id="04ebe-146">在大多数情况下，快速扫描将捕获并清理检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="04ebe-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="04ebe-147">想要运行 [按需扫描](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="04ebe-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="04ebe-148">快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-148">Quick scan</span></span>       |
| <span data-ttu-id="04ebe-149">你想要确保便携式设备（如 USB 驱动器）不包含恶意软件</span><span class="sxs-lookup"><span data-stu-id="04ebe-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="04ebe-150">自定义扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-150">Custom scan</span></span> <p><span data-ttu-id="04ebe-151">通过自定义扫描，可以选择特定位置、文件夹或文件，并运行快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="04ebe-152">关于快速和完整扫描，我还需要了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="04ebe-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="04ebe-153">恶意文件可以存储在快速扫描中未包含的位置。</span><span class="sxs-lookup"><span data-stu-id="04ebe-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="04ebe-154">但是，始终启用实时保护会检查所有打开和关闭的文件，以及用户访问的文件夹中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="04ebe-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="04ebe-155">实时保护和快速扫描相结合有助于提供强大的恶意软件防护。</span><span class="sxs-lookup"><span data-stu-id="04ebe-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="04ebe-156">具有云保护的 [On-access Protection](cloud-protection-microsoft-defender-antivirus.md) 有助于确保使用最新的安全智能和云机器学习模型扫描系统上访问的所有文件。</span><span class="sxs-lookup"><span data-stu-id="04ebe-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="04ebe-157">当实时保护检测到恶意软件并且最初未确定受影响文件的范围时，Microsoft Defender 防病毒在修正过程中启动完全扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="04ebe-158">完全扫描可以检测其他扫描未检测到的恶意文件，例如快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="04ebe-159">但是，完整扫描可能需要一段时间，并使用有价值的系统资源来完成。</span><span class="sxs-lookup"><span data-stu-id="04ebe-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="04ebe-160">如果设备长时间处于脱机状态，则完整扫描可能需要更长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="04ebe-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="04ebe-161">设置计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-161">Set up scheduled scans</span></span>

<span data-ttu-id="04ebe-162">计划的扫描将在你指定的日期和时间运行。</span><span class="sxs-lookup"><span data-stu-id="04ebe-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="04ebe-163">可以使用组策略、PowerShell 和 WMI 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="04ebe-164">如果在计划的完全扫描期间设备已拔下并运行在电池上，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。</span><span class="sxs-lookup"><span data-stu-id="04ebe-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="04ebe-165">Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="04ebe-166">使用组策略计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="04ebe-167">位置</span><span class="sxs-lookup"><span data-stu-id="04ebe-167">Location</span></span> | <span data-ttu-id="04ebe-168">设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-168">Setting</span></span> | <span data-ttu-id="04ebe-169">说明</span><span class="sxs-lookup"><span data-stu-id="04ebe-169">Description</span></span> | <span data-ttu-id="04ebe-170">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="04ebe-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04ebe-171">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-171">Scan</span></span> | <span data-ttu-id="04ebe-172">指定用于计划扫描的扫描类型</span><span class="sxs-lookup"><span data-stu-id="04ebe-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="04ebe-173">快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-173">Quick scan</span></span> |
|<span data-ttu-id="04ebe-174">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-174">Scan</span></span> | <span data-ttu-id="04ebe-175">指定一周中的哪些天运行计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="04ebe-176">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="04ebe-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="04ebe-177">永不</span><span class="sxs-lookup"><span data-stu-id="04ebe-177">Never</span></span> |
|<span data-ttu-id="04ebe-178">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-178">Scan</span></span> | <span data-ttu-id="04ebe-179">指定运行计划扫描的时间</span><span class="sxs-lookup"><span data-stu-id="04ebe-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="04ebe-180">指定午夜过后的分钟数 (例如，输入 **60** 表示上午 1 点) 。</span><span class="sxs-lookup"><span data-stu-id="04ebe-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="04ebe-181">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="04ebe-181">2 a.m.</span></span> |
|<span data-ttu-id="04ebe-182">根</span><span class="sxs-lookup"><span data-stu-id="04ebe-182">Root</span></span> | <span data-ttu-id="04ebe-183">随机化计划任务时间</span><span class="sxs-lookup"><span data-stu-id="04ebe-183">Randomize scheduled task times</span></span> |<span data-ttu-id="04ebe-184">在Microsoft Defender 防病毒中，将扫描的开始时间随机化为 0 到 4 小时之间的任意间隔。</span><span class="sxs-lookup"><span data-stu-id="04ebe-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="04ebe-185">在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，将扫描随机化为任意间隔加减 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="04ebe-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="04ebe-186">这可在虚拟机或 VDI 部署中非常有用。</span><span class="sxs-lookup"><span data-stu-id="04ebe-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="04ebe-187">启用</span><span class="sxs-lookup"><span data-stu-id="04ebe-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="04ebe-188">使用 PowerShell cmdlet 计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="04ebe-189">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04ebe-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="04ebe-190">有关详细信息，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="04ebe-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="04ebe-191">使用 Windows Management Instruction (WMI) 计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="04ebe-192">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="04ebe-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="04ebe-193">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="04ebe-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="04ebe-194">仅在终结点不使用时启动计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="04ebe-195">可以将计划扫描设置为仅在终结点打开时发生，但不与组策略、PowerShell 或 WMI 一同使用。</span><span class="sxs-lookup"><span data-stu-id="04ebe-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="04ebe-196">这些扫描不会接受 CPU 限制配置，并充分利用可用资源尽快完成扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="04ebe-197">使用组策略计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="04ebe-198">位置</span><span class="sxs-lookup"><span data-stu-id="04ebe-198">Location</span></span> | <span data-ttu-id="04ebe-199">设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-199">Setting</span></span> | <span data-ttu-id="04ebe-200">说明</span><span class="sxs-lookup"><span data-stu-id="04ebe-200">Description</span></span> | <span data-ttu-id="04ebe-201">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="04ebe-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04ebe-202">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-202">Scan</span></span> | <span data-ttu-id="04ebe-203">仅在计算机打开但没有使用时启动计划扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="04ebe-204">计划的扫描将不会运行，除非计算机已打开但没有使用</span><span class="sxs-lookup"><span data-stu-id="04ebe-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="04ebe-205">启用</span><span class="sxs-lookup"><span data-stu-id="04ebe-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="04ebe-206">使用 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="04ebe-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="04ebe-207">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04ebe-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="04ebe-208">有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="04ebe-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="04ebe-209">使用 Windows Management Instruction (WMI) </span><span class="sxs-lookup"><span data-stu-id="04ebe-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="04ebe-210">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="04ebe-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="04ebe-211">有关 API 和允许的参数详细信息，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="04ebe-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="04ebe-212">配置应何时运行完全扫描以完成修正</span><span class="sxs-lookup"><span data-stu-id="04ebe-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="04ebe-213">某些威胁可能需要完全扫描才能完成删除和修正。</span><span class="sxs-lookup"><span data-stu-id="04ebe-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="04ebe-214">可以使用组策略、PowerShell 或 WMI 指定何时应进行这些扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="04ebe-215">使用组策略计划修正所需的扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="04ebe-216">位置</span><span class="sxs-lookup"><span data-stu-id="04ebe-216">Location</span></span> | <span data-ttu-id="04ebe-217">设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-217">Setting</span></span> | <span data-ttu-id="04ebe-218">说明</span><span class="sxs-lookup"><span data-stu-id="04ebe-218">Description</span></span> | <span data-ttu-id="04ebe-219">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="04ebe-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="04ebe-220">修正</span><span class="sxs-lookup"><span data-stu-id="04ebe-220">Remediation</span></span> | <span data-ttu-id="04ebe-221">指定一周中的哪些天运行计划的完全扫描以完成修正</span><span class="sxs-lookup"><span data-stu-id="04ebe-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="04ebe-222">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="04ebe-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="04ebe-223">永不</span><span class="sxs-lookup"><span data-stu-id="04ebe-223">Never</span></span> |
|<span data-ttu-id="04ebe-224">修正</span><span class="sxs-lookup"><span data-stu-id="04ebe-224">Remediation</span></span> | <span data-ttu-id="04ebe-225">指定一天中运行计划完整扫描以完成修正的时间</span><span class="sxs-lookup"><span data-stu-id="04ebe-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="04ebe-226">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="04ebe-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="04ebe-227">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="04ebe-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="04ebe-228">使用 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="04ebe-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="04ebe-229">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04ebe-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="04ebe-230">请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。</span><span class="sxs-lookup"><span data-stu-id="04ebe-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="04ebe-231">使用 Windows Management Instruction (WMI) </span><span class="sxs-lookup"><span data-stu-id="04ebe-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="04ebe-232">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="04ebe-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="04ebe-233">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="04ebe-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="04ebe-234">设置每日快速扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-234">Set up daily quick scans</span></span>

<span data-ttu-id="04ebe-235">除了使用组策略、PowerShell 或 WMI 进行其他计划扫描外，还可以启用每日快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="04ebe-236">使用组策略计划每日扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="04ebe-237">位置</span><span class="sxs-lookup"><span data-stu-id="04ebe-237">Location</span></span> | <span data-ttu-id="04ebe-238">设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-238">Setting</span></span> | <span data-ttu-id="04ebe-239">说明</span><span class="sxs-lookup"><span data-stu-id="04ebe-239">Description</span></span> | <span data-ttu-id="04ebe-240">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="04ebe-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="04ebe-241">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-241">Scan</span></span> | <span data-ttu-id="04ebe-242">指定每天运行快速扫描的间隔</span><span class="sxs-lookup"><span data-stu-id="04ebe-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="04ebe-243">指定下一次快速扫描之前应经过的小时数。</span><span class="sxs-lookup"><span data-stu-id="04ebe-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="04ebe-244">例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。</span><span class="sxs-lookup"><span data-stu-id="04ebe-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="04ebe-245">输入 **0** 从不运行每日快速扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="04ebe-246">永不</span><span class="sxs-lookup"><span data-stu-id="04ebe-246">Never</span></span> |
|<span data-ttu-id="04ebe-247">扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-247">Scan</span></span> | <span data-ttu-id="04ebe-248">指定每日快速扫描的时间</span><span class="sxs-lookup"><span data-stu-id="04ebe-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="04ebe-249">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="04ebe-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="04ebe-250">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="04ebe-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="04ebe-251">使用 PowerShell cmdlet 计划每日扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="04ebe-252">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="04ebe-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="04ebe-253">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和 Defender [cmdlet。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="04ebe-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="04ebe-254">使用 Windows Management Instruction (WMI) 安排每日扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="04ebe-255">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="04ebe-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="04ebe-256">有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="04ebe-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="04ebe-257">在保护更新后启用扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-257">Enable scans after protection updates</span></span>

<span data-ttu-id="04ebe-258">可以使用组策略强制每次保护 [更新后](manage-protection-updates-microsoft-defender-antivirus.md) 执行扫描。</span><span class="sxs-lookup"><span data-stu-id="04ebe-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="04ebe-259">使用组策略计划保护更新后的扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="04ebe-260">位置</span><span class="sxs-lookup"><span data-stu-id="04ebe-260">Location</span></span> | <span data-ttu-id="04ebe-261">设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-261">Setting</span></span> | <span data-ttu-id="04ebe-262">说明</span><span class="sxs-lookup"><span data-stu-id="04ebe-262">Description</span></span> | <span data-ttu-id="04ebe-263">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="04ebe-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="04ebe-264">签名更新</span><span class="sxs-lookup"><span data-stu-id="04ebe-264">Signature updates</span></span> | <span data-ttu-id="04ebe-265">在安全智能更新后打开扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="04ebe-266">扫描将在下载新保护更新后立即发生</span><span class="sxs-lookup"><span data-stu-id="04ebe-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="04ebe-267">启用</span><span class="sxs-lookup"><span data-stu-id="04ebe-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="04ebe-268">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04ebe-268">See also</span></span>

- [<span data-ttu-id="04ebe-269">阻止或允许用户在本地修改策略设置</span><span class="sxs-lookup"><span data-stu-id="04ebe-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04ebe-270">配置并运行按需 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="04ebe-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04ebe-271">配置 Microsoft Defender 防病毒软件扫描选项</span><span class="sxs-lookup"><span data-stu-id="04ebe-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04ebe-272">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="04ebe-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="04ebe-273">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="04ebe-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="04ebe-274">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="04ebe-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)