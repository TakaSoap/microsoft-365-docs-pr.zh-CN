---
title: 使用 Microsoft Defender 防病毒计划定期快速和完整扫描
description: 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 常规
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bfa616423fc0c097b9909df8abf5b9c414490383
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764083"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="31751-104">配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="31751-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="31751-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="31751-105">**Applies to:**</span></span>

- [<span data-ttu-id="31751-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31751-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="31751-107">默认情况下，Microsoft Defender 防病毒会在任何计划扫描前 15 分钟检查更新。</span><span class="sxs-lookup"><span data-stu-id="31751-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="31751-108">你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。</span><span class="sxs-lookup"><span data-stu-id="31751-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="31751-109">除了始终打开实时保护和按需扫描之外，还可以设置[](run-scan-microsoft-defender-antivirus.md)定期计划扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="31751-110">可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后发生还是使用终结点。 [](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="31751-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="31751-111">还可以指定应何时进行特殊扫描以完成修正。</span><span class="sxs-lookup"><span data-stu-id="31751-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="31751-112">本文介绍如何使用组策略、PowerShell cmdlet 和 WMI 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="31751-113">还可使用 Microsoft Endpoint [Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 或 [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="31751-114">配置本文中所述的组策略设置</span><span class="sxs-lookup"><span data-stu-id="31751-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="31751-115">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="31751-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="31751-116">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="31751-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="31751-117">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="31751-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="31751-118">将树展开到 **Microsoft Defender > Windows** 组件，然后展开下表中指定的位置。 </span><span class="sxs-lookup"><span data-stu-id="31751-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="31751-119">双击 **下表中指定的** 策略设置，将选项设置为所需的配置。</span><span class="sxs-lookup"><span data-stu-id="31751-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="31751-120">单击 **"确定**"，然后对任何其他设置重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="31751-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="31751-121">另请参阅 [管理何时应下载](manage-protection-update-schedule-microsoft-defender-antivirus.md) 和应用保护更新和阻止或允许用户 [在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="31751-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="31751-122">快速扫描与完全扫描和自定义扫描</span><span class="sxs-lookup"><span data-stu-id="31751-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="31751-123">设置计划扫描时，可以设置扫描应为完全扫描还是快速扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="31751-124">快速扫描会查看所有可能注册了恶意软件以从系统启动的位置，例如注册表项和已知的 Windows 启动文件夹。</span><span class="sxs-lookup"><span data-stu-id="31751-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="31751-125">与 [始终启用](configure-real-time-protection-microsoft-defender-antivirus.md) 实时保护功能（在打开和关闭文件时以及用户导航到文件夹时查看文件）相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="31751-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="31751-126">在大多数情况下，这意味着快速扫描足以找到未通过实时保护选取的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="31751-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="31751-127">完全扫描在遇到恶意软件威胁的终结点上非常有用，可用于标识是否有需要更彻底清理的非活动组件。</span><span class="sxs-lookup"><span data-stu-id="31751-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="31751-128">在这种情况下，你可能想要在运行按需扫描时使用 [完全扫描](run-scan-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="31751-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="31751-129">自定义扫描允许你指定要扫描的文件和文件夹，例如 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="31751-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="31751-130">默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。</span><span class="sxs-lookup"><span data-stu-id="31751-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="31751-131">设置计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-131">Set up scheduled scans</span></span>

<span data-ttu-id="31751-132">计划的扫描将在你指定的日期和时间运行。</span><span class="sxs-lookup"><span data-stu-id="31751-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="31751-133">可以使用组策略、PowerShell 和 WMI 配置计划扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="31751-134">如果在计划的完整扫描期间计算机已拔下并按电池运行，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。</span><span class="sxs-lookup"><span data-stu-id="31751-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="31751-135">Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="31751-136">使用组策略计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="31751-137">位置</span><span class="sxs-lookup"><span data-stu-id="31751-137">Location</span></span> | <span data-ttu-id="31751-138">设置</span><span class="sxs-lookup"><span data-stu-id="31751-138">Setting</span></span> | <span data-ttu-id="31751-139">说明</span><span class="sxs-lookup"><span data-stu-id="31751-139">Description</span></span> | <span data-ttu-id="31751-140">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="31751-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="31751-141">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-141">Scan</span></span> | <span data-ttu-id="31751-142">指定用于计划扫描的扫描类型</span><span class="sxs-lookup"><span data-stu-id="31751-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="31751-143">快速扫描</span><span class="sxs-lookup"><span data-stu-id="31751-143">Quick scan</span></span> |
|<span data-ttu-id="31751-144">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-144">Scan</span></span> | <span data-ttu-id="31751-145">指定一周中的哪些天运行计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="31751-146">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="31751-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="31751-147">从不</span><span class="sxs-lookup"><span data-stu-id="31751-147">Never</span></span> |
|<span data-ttu-id="31751-148">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-148">Scan</span></span> | <span data-ttu-id="31751-149">指定运行计划扫描的时间</span><span class="sxs-lookup"><span data-stu-id="31751-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="31751-150">指定午夜过后的分钟数 (例如，输入 **60** 表示上午 1 点) 。</span><span class="sxs-lookup"><span data-stu-id="31751-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="31751-151">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="31751-151">2 a.m.</span></span> |
|<span data-ttu-id="31751-152">根</span><span class="sxs-lookup"><span data-stu-id="31751-152">Root</span></span> | <span data-ttu-id="31751-153">随机化计划任务时间</span><span class="sxs-lookup"><span data-stu-id="31751-153">Randomize scheduled task times</span></span> |<span data-ttu-id="31751-154">在 Microsoft Defender 防病毒中：将扫描的开始时间随机化为 0 到 4 小时之间的任意间隔。</span><span class="sxs-lookup"><span data-stu-id="31751-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="31751-155">在 FEP/SCEP 中：随机化为任意间隔加减 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="31751-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="31751-156">这可在 VM 或 VDI 部署中非常有用。</span><span class="sxs-lookup"><span data-stu-id="31751-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="31751-157">已启用</span><span class="sxs-lookup"><span data-stu-id="31751-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="31751-158">使用 PowerShell cmdlet 计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="31751-159">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="31751-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="31751-160">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="31751-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="31751-161">使用 Windows Management Instruction (WMI) 计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="31751-162">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="31751-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="31751-163">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="31751-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="31751-164">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="31751-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="31751-165">仅在终结点不使用时启动计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="31751-166">可以将计划扫描设置为仅在终结点打开时发生，但不与组策略、PowerShell 或 WMI 一同使用。</span><span class="sxs-lookup"><span data-stu-id="31751-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="31751-167">这些扫描不会接受 CPU 限制配置，并充分利用可用资源尽快完成扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="31751-168">使用组策略计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="31751-169">位置</span><span class="sxs-lookup"><span data-stu-id="31751-169">Location</span></span> | <span data-ttu-id="31751-170">设置</span><span class="sxs-lookup"><span data-stu-id="31751-170">Setting</span></span> | <span data-ttu-id="31751-171">说明</span><span class="sxs-lookup"><span data-stu-id="31751-171">Description</span></span> | <span data-ttu-id="31751-172">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="31751-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="31751-173">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-173">Scan</span></span> | <span data-ttu-id="31751-174">仅在计算机打开但没有使用时启动计划扫描</span><span class="sxs-lookup"><span data-stu-id="31751-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="31751-175">计划的扫描将不会运行，除非计算机已打开但没有使用</span><span class="sxs-lookup"><span data-stu-id="31751-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="31751-176">已启用</span><span class="sxs-lookup"><span data-stu-id="31751-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="31751-177">使用 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="31751-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="31751-178">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="31751-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="31751-179">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="31751-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="31751-180">使用 Windows Management Instruction (WMI) </span><span class="sxs-lookup"><span data-stu-id="31751-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="31751-181">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="31751-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="31751-182">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="31751-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="31751-183">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="31751-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="31751-184">配置应何时运行完全扫描以完成修正</span><span class="sxs-lookup"><span data-stu-id="31751-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="31751-185">某些威胁可能需要完全扫描才能完成删除和修正。</span><span class="sxs-lookup"><span data-stu-id="31751-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="31751-186">可以使用组策略、PowerShell 或 WMI 计划这些扫描应发生的时间。</span><span class="sxs-lookup"><span data-stu-id="31751-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="31751-187">使用组策略计划修正所需的扫描</span><span class="sxs-lookup"><span data-stu-id="31751-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="31751-188">位置</span><span class="sxs-lookup"><span data-stu-id="31751-188">Location</span></span> | <span data-ttu-id="31751-189">设置</span><span class="sxs-lookup"><span data-stu-id="31751-189">Setting</span></span> | <span data-ttu-id="31751-190">说明</span><span class="sxs-lookup"><span data-stu-id="31751-190">Description</span></span> | <span data-ttu-id="31751-191">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="31751-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="31751-192">修正</span><span class="sxs-lookup"><span data-stu-id="31751-192">Remediation</span></span> | <span data-ttu-id="31751-193">指定一周中的哪些天运行计划的完全扫描以完成修正</span><span class="sxs-lookup"><span data-stu-id="31751-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="31751-194">指定运行 () 或从不运行扫描的日。</span><span class="sxs-lookup"><span data-stu-id="31751-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="31751-195">从不</span><span class="sxs-lookup"><span data-stu-id="31751-195">Never</span></span> |
|<span data-ttu-id="31751-196">修正</span><span class="sxs-lookup"><span data-stu-id="31751-196">Remediation</span></span> | <span data-ttu-id="31751-197">指定一天中运行计划完整扫描以完成修正的时间</span><span class="sxs-lookup"><span data-stu-id="31751-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="31751-198">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="31751-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="31751-199">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="31751-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="31751-200">使用 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="31751-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="31751-201">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="31751-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="31751-202">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="31751-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="31751-203">使用 Windows Management Instruction (WMI) </span><span class="sxs-lookup"><span data-stu-id="31751-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="31751-204">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="31751-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="31751-205">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="31751-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="31751-206">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="31751-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="31751-207">设置每日快速扫描</span><span class="sxs-lookup"><span data-stu-id="31751-207">Set up daily quick scans</span></span>

<span data-ttu-id="31751-208">除了使用组策略、PowerShell 或 WMI 进行其他计划扫描外，还可以启用每日快速扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="31751-209">使用组策略计划每日扫描</span><span class="sxs-lookup"><span data-stu-id="31751-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="31751-210">位置</span><span class="sxs-lookup"><span data-stu-id="31751-210">Location</span></span> | <span data-ttu-id="31751-211">设置</span><span class="sxs-lookup"><span data-stu-id="31751-211">Setting</span></span> | <span data-ttu-id="31751-212">说明</span><span class="sxs-lookup"><span data-stu-id="31751-212">Description</span></span> | <span data-ttu-id="31751-213">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="31751-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="31751-214">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-214">Scan</span></span> | <span data-ttu-id="31751-215">指定每天运行快速扫描的间隔</span><span class="sxs-lookup"><span data-stu-id="31751-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="31751-216">指定下一次快速扫描之前应经过的小时数。</span><span class="sxs-lookup"><span data-stu-id="31751-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="31751-217">例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。</span><span class="sxs-lookup"><span data-stu-id="31751-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="31751-218">输入 **0** 从不运行每日快速扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="31751-219">从不</span><span class="sxs-lookup"><span data-stu-id="31751-219">Never</span></span> |
|<span data-ttu-id="31751-220">扫描</span><span class="sxs-lookup"><span data-stu-id="31751-220">Scan</span></span> | <span data-ttu-id="31751-221">指定每日快速扫描的时间</span><span class="sxs-lookup"><span data-stu-id="31751-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="31751-222">指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点) </span><span class="sxs-lookup"><span data-stu-id="31751-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="31751-223">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="31751-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="31751-224">使用 PowerShell cmdlet 计划每日扫描</span><span class="sxs-lookup"><span data-stu-id="31751-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="31751-225">使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="31751-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="31751-226">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="31751-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="31751-227">使用 Windows Management Instruction (WMI) 安排每日扫描</span><span class="sxs-lookup"><span data-stu-id="31751-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="31751-228">对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：</span><span class="sxs-lookup"><span data-stu-id="31751-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="31751-229">有关详细信息和允许的参数，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="31751-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="31751-230">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="31751-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="31751-231">在保护更新后启用扫描</span><span class="sxs-lookup"><span data-stu-id="31751-231">Enable scans after protection updates</span></span>

<span data-ttu-id="31751-232">可以使用组策略强制每次保护 [更新后](manage-protection-updates-microsoft-defender-antivirus.md) 执行扫描。</span><span class="sxs-lookup"><span data-stu-id="31751-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="31751-233">使用组策略计划保护更新后的扫描</span><span class="sxs-lookup"><span data-stu-id="31751-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="31751-234">位置</span><span class="sxs-lookup"><span data-stu-id="31751-234">Location</span></span> | <span data-ttu-id="31751-235">设置</span><span class="sxs-lookup"><span data-stu-id="31751-235">Setting</span></span> | <span data-ttu-id="31751-236">说明</span><span class="sxs-lookup"><span data-stu-id="31751-236">Description</span></span> | <span data-ttu-id="31751-237">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="31751-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="31751-238">签名更新</span><span class="sxs-lookup"><span data-stu-id="31751-238">Signature updates</span></span> | <span data-ttu-id="31751-239">在安全智能更新后打开扫描</span><span class="sxs-lookup"><span data-stu-id="31751-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="31751-240">扫描将在下载新保护更新后立即发生</span><span class="sxs-lookup"><span data-stu-id="31751-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="31751-241">已启用</span><span class="sxs-lookup"><span data-stu-id="31751-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="31751-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31751-242">See also</span></span>
- [<span data-ttu-id="31751-243">阻止或允许用户在本地修改策略设置</span><span class="sxs-lookup"><span data-stu-id="31751-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31751-244">配置并运行按需 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="31751-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31751-245">配置 Microsoft Defender 防病毒软件扫描选项</span><span class="sxs-lookup"><span data-stu-id="31751-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31751-246">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="31751-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="31751-247">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="31751-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="31751-248">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="31751-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)