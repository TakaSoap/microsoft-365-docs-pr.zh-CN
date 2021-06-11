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
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879660"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="9ff96-104">配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="9ff96-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9ff96-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ff96-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ff96-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9ff96-107">除了始终打开、实时保护和按需防病毒扫描之外，还可以[](run-scan-microsoft-defender-antivirus.md)设置定期计划防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-107">In addition to always-on, real-time protection and [on-demand antivirus](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled antivirus scans.</span></span> <span data-ttu-id="9ff96-108">可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后或终结点未使用时发生[](manage-protection-updates-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9ff96-108">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or when an endpoint is not being used.</span></span> <span data-ttu-id="9ff96-109">如果需要，还可以设置特殊扫描以完成修正操作。</span><span class="sxs-lookup"><span data-stu-id="9ff96-109">You can also set up special scans to complete remediation actions if needed.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="9ff96-110">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="9ff96-110">What do you want to do?</span></span>

- [<span data-ttu-id="9ff96-111">了解快速扫描、完整扫描和自定义扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-111">Learn about quick scans, full scans, and custom scans</span></span>](#quick-scan-full-scan-and-custom-scan)
- [<span data-ttu-id="9ff96-112">使用组策略计划防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-112">Use Group Policy to schedule antivirus scans</span></span>](schedule-antivirus-scans-group-policy.md)
- [<span data-ttu-id="9ff96-113">使用Windows PowerShell计划防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-113">Use Windows PowerShell to Schedule antivirus scans</span></span>](schedule-antivirus-scans-powershell.md)
- [<span data-ttu-id="9ff96-114">使用 Windows Management Instrumentation 计划防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-114">Use Windows Management Instrumentation to schedule antivirus scans</span></span>](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="9ff96-115">请记住以下几点</span><span class="sxs-lookup"><span data-stu-id="9ff96-115">Keep the following points in mind</span></span>

- <span data-ttu-id="9ff96-116">默认情况下，Microsoft Defender 防病毒扫描前 15 分钟检查更新。</span><span class="sxs-lookup"><span data-stu-id="9ff96-116">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="9ff96-117">你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。</span><span class="sxs-lookup"><span data-stu-id="9ff96-117">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

- <span data-ttu-id="9ff96-118">如果在计划的完全扫描期间设备已拔下并运行在电池上，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。</span><span class="sxs-lookup"><span data-stu-id="9ff96-118">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="9ff96-119">Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-119">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

## <a name="quick-scan-full-scan-and-custom-scan"></a><span data-ttu-id="9ff96-120">快速扫描、完全扫描和自定义扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-120">Quick scan, full scan, and custom scan</span></span>

<span data-ttu-id="9ff96-121">设置计划扫描时，可以指定扫描应为完全扫描还是快速扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-121">When you set up scheduled scans, you can specify whether the scan should be a full or quick scan.</span></span> <span data-ttu-id="9ff96-122">在大多数情况下，建议使用快速扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-122">In most cases, a quick scan is recommended.</span></span> 

| <span data-ttu-id="9ff96-123">快速扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-123">Quick scan</span></span>  | <span data-ttu-id="9ff96-124">完全扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-124">Full scan</span></span>  | <span data-ttu-id="9ff96-125">自定义扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-125">Custom scan</span></span> |
|---------|---------|---------|
| <span data-ttu-id="9ff96-126"> (推荐) 快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ff96-126">(Recommended) A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="9ff96-127">与始终启用实时保护相结合，可在打开和关闭文件时以及用户导航到文件夹时查看文件，快速扫描可帮助提供强大的保护，防止因系统和内核级别恶意软件而启动的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="9ff96-127">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <p><span data-ttu-id="9ff96-128">在大多数情况下，快速扫描已足够，是计划扫描的推荐选项。</span><span class="sxs-lookup"><span data-stu-id="9ff96-128">In most cases, a quick scan is sufficient and is the recommended option for scheduled scans.</span></span> | <span data-ttu-id="9ff96-129">完整扫描首先运行快速扫描，然后继续针对所有已装载的固定磁盘和可移动/网络驱动器进行连续文件扫描 (如果完全扫描配置为) 。</span><span class="sxs-lookup"><span data-stu-id="9ff96-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="9ff96-130">完整扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据的数量和类型。</span><span class="sxs-lookup"><span data-stu-id="9ff96-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="9ff96-131">完全扫描完成后，新的安全智能可用，然后需要新的扫描以确保新安全智能不会检测到任何其他威胁。</span><span class="sxs-lookup"><span data-stu-id="9ff96-131">When the full scan is complete, new security intelligence is available, and a new scan is then required to make sure that no other threats are detected with the new security intelligence.</span></span> <p><span data-ttu-id="9ff96-132">由于完全扫描所涉及的时间和资源，Microsoft 通常不建议安排完全扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-132">Because of the time and resources involved in a full scan, in general, Microsoft does not recommend scheduling full scans.</span></span>  | <span data-ttu-id="9ff96-133">自定义扫描是在指定的文件和文件夹上运行的快速扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-133">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="9ff96-134">例如，你可以选择扫描 USB 驱动器或设备本地驱动器上的特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ff96-134">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

> [!NOTE]
> <span data-ttu-id="9ff96-135">默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。</span><span class="sxs-lookup"><span data-stu-id="9ff96-135">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="9ff96-136">我如何知道要选择哪个扫描类型？</span><span class="sxs-lookup"><span data-stu-id="9ff96-136">How do I know which scan type to choose?</span></span>

<span data-ttu-id="9ff96-137">使用下表选择扫描类型。</span><span class="sxs-lookup"><span data-stu-id="9ff96-137">Use the following table to choose a scan type.</span></span>

| <span data-ttu-id="9ff96-138">应用场景</span><span class="sxs-lookup"><span data-stu-id="9ff96-138">Scenario</span></span>  | <span data-ttu-id="9ff96-139">推荐的扫描类型</span><span class="sxs-lookup"><span data-stu-id="9ff96-139">Recommended scan type</span></span>  |
|---------|---------|
| <span data-ttu-id="9ff96-140">想要设置定期计划扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-140">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="9ff96-141">快速扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-141">Quick scan</span></span> <p><span data-ttu-id="9ff96-142">快速扫描检查设备上的过程、内存、配置文件和特定位置。</span><span class="sxs-lookup"><span data-stu-id="9ff96-142">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="9ff96-143">与 [始终开启的](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="9ff96-143">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="9ff96-144">实时保护在打开和关闭文件时以及用户导航到文件夹时检查文件。</span><span class="sxs-lookup"><span data-stu-id="9ff96-144">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
| <span data-ttu-id="9ff96-145">在单个设备上检测到恶意软件等威胁</span><span class="sxs-lookup"><span data-stu-id="9ff96-145">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="9ff96-146">快速扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-146">Quick scan</span></span> <p><span data-ttu-id="9ff96-147">在大多数情况下，快速扫描将捕获并清理检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="9ff96-147">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
| <span data-ttu-id="9ff96-148">想要运行 [按需扫描](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9ff96-148">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="9ff96-149">快速扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-149">Quick scan</span></span>       |
| <span data-ttu-id="9ff96-150">你想要确保便携式设备（如 USB 驱动器）不包含恶意软件</span><span class="sxs-lookup"><span data-stu-id="9ff96-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="9ff96-151">自定义扫描</span><span class="sxs-lookup"><span data-stu-id="9ff96-151">Custom scan</span></span> <p><span data-ttu-id="9ff96-152">自定义扫描使你能够选择特定位置、文件夹或文件，并运行快速扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-152">A custom scan enables you to select specific locations, folders, or files, and runs a quick scan.</span></span> |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="9ff96-153">关于快速和完整扫描，我还需要了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="9ff96-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="9ff96-154">恶意文件可以存储在快速扫描中未包含的位置。</span><span class="sxs-lookup"><span data-stu-id="9ff96-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="9ff96-155">但是，始终启用实时保护会检查所有打开和关闭的文件，以及用户访问的文件夹中的任何文件。</span><span class="sxs-lookup"><span data-stu-id="9ff96-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="9ff96-156">实时保护和快速扫描相结合有助于提供强大的恶意软件防护。</span><span class="sxs-lookup"><span data-stu-id="9ff96-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="9ff96-157">具有云保护的 [On-access Protection](cloud-protection-microsoft-defender-antivirus.md) 有助于确保使用最新的安全智能和云机器学习模型扫描系统上访问的所有文件。</span><span class="sxs-lookup"><span data-stu-id="9ff96-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="9ff96-158">当实时保护检测到恶意软件并且最初未确定受影响文件的范围时，Microsoft Defender 防病毒在修正过程中启动完全扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="9ff96-159">完全扫描可以检测其他扫描未检测到的恶意文件，例如快速扫描。</span><span class="sxs-lookup"><span data-stu-id="9ff96-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="9ff96-160">但是，完整扫描可能需要一段时间，并使用有价值的系统资源来完成。</span><span class="sxs-lookup"><span data-stu-id="9ff96-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="9ff96-161">如果设备长时间处于脱机状态，则完整扫描可能需要更长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="9ff96-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

