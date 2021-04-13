---
title: 配置 Microsoft Defender AV 的扫描选项
description: 你可以将 Microsoft Defender AV 配置为扫描电子邮件存储文件、备份或重新分析点、网络文件和存档文件 (.zip 文件) 。
keywords: 高级扫描， 扫描， 电子邮件， 存档， zip， rar， 存档， 重新分析扫描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689951"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="6c6ed-104">配置 Microsoft Defender 防病毒扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-104">Configure Microsoft Defender Antivirus scanning options</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c6ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c6ed-105">**Applies to:**</span></span>

- [<span data-ttu-id="6c6ed-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c6ed-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="6c6ed-107">使用 Microsoft Intune 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="6c6ed-108">有关详细信息 [，请参阅在 Microsoft Intune 中](/intune/device-restrictions-configure) 配置设备限制设置和 Intune 中 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 的 Microsoft Defender 防病毒设备限制设置。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-108">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="6c6ed-109">使用 Microsoft Endpoint Manager 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="6c6ed-110">请参阅 [如何创建和部署反恶意软件](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) 策略：扫描设置，了解有关配置 Microsoft Endpoint Manager (当前分支) 。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-110">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="6c6ed-111">使用组策略配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-111">Use Group Policy to configure scanning options</span></span>

<span data-ttu-id="6c6ed-112">配置下表中所述的组策略设置：</span><span class="sxs-lookup"><span data-stu-id="6c6ed-112">To configure the Group Policy settings described in the following table:</span></span>

1. <span data-ttu-id="6c6ed-113">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="6c6ed-113">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6c6ed-114">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="6c6ed-115">将树展开到 **Microsoft Defender > Windows** 组件，然后展开下表中指定的位置。 </span><span class="sxs-lookup"><span data-stu-id="6c6ed-115">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="6c6ed-116">双击 **下表中指定的** 策略设置，将选项设置为所需的配置。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-116">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="6c6ed-117">单击 **"确定**"，然后对任何其他设置重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-117">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="6c6ed-118">说明</span><span class="sxs-lookup"><span data-stu-id="6c6ed-118">Description</span></span> | <span data-ttu-id="6c6ed-119">位置和设置</span><span class="sxs-lookup"><span data-stu-id="6c6ed-119">Location and setting</span></span> | <span data-ttu-id="6c6ed-120">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="6c6ed-120">Default setting (if not configured)</span></span> | <span data-ttu-id="6c6ed-121">类的 PowerShell `Set-MpPreference` 参数或 WMI `MSFT_MpPreference` 属性</span><span class="sxs-lookup"><span data-stu-id="6c6ed-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span>
---|---|---|---
<span data-ttu-id="6c6ed-122">电子邮件扫描 请参阅 [电子邮件扫描限制](#ref1)</span><span class="sxs-lookup"><span data-stu-id="6c6ed-122">Email scanning See [Email scanning limitations](#ref1)</span></span>| <span data-ttu-id="6c6ed-123">扫描>打开电子邮件扫描</span><span class="sxs-lookup"><span data-stu-id="6c6ed-123">Scan > Turn on e-mail scanning</span></span> | <span data-ttu-id="6c6ed-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-124">Disabled</span></span> | `-DisableEmailScanning`
<span data-ttu-id="6c6ed-125">扫描 [重新分析点](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="6c6ed-125">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> | <span data-ttu-id="6c6ed-126">扫描>打开重新分析点扫描</span><span class="sxs-lookup"><span data-stu-id="6c6ed-126">Scan > Turn on reparse point scanning</span></span> | <span data-ttu-id="6c6ed-127">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-127">Disabled</span></span> | <span data-ttu-id="6c6ed-128">不可用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-128">Not available</span></span>
<span data-ttu-id="6c6ed-129">扫描映射的网络驱动器</span><span class="sxs-lookup"><span data-stu-id="6c6ed-129">Scan mapped network drives</span></span> | <span data-ttu-id="6c6ed-130">扫描>映射的网络驱动器上运行完全扫描</span><span class="sxs-lookup"><span data-stu-id="6c6ed-130">Scan > Run full scan on mapped network drives</span></span> | <span data-ttu-id="6c6ed-131">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-131">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`
 <span data-ttu-id="6c6ed-132">扫描存档文件 (.zip 或 .rar 文件) 。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-132">Scan archive files (such as .zip or .rar files).</span></span> <span data-ttu-id="6c6ed-133">扩展 [名排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 将优先于此设置。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-133">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span> | <span data-ttu-id="6c6ed-134">扫描>扫描存档文件</span><span class="sxs-lookup"><span data-stu-id="6c6ed-134">Scan > Scan archive files</span></span> | <span data-ttu-id="6c6ed-135">已启用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-135">Enabled</span></span> | `-DisableArchiveScanning`
<span data-ttu-id="6c6ed-136">扫描网络文件</span><span class="sxs-lookup"><span data-stu-id="6c6ed-136">Scan files on the network</span></span> | <span data-ttu-id="6c6ed-137">扫描>扫描网络文件</span><span class="sxs-lookup"><span data-stu-id="6c6ed-137">Scan > Scan network files</span></span> | <span data-ttu-id="6c6ed-138">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-138">Disabled</span></span> | `-DisableScanningNetworkFiles`
<span data-ttu-id="6c6ed-139">扫描打包的可执行文件</span><span class="sxs-lookup"><span data-stu-id="6c6ed-139">Scan packed executables</span></span> | <span data-ttu-id="6c6ed-140">扫描>扫描打包的可执行文件</span><span class="sxs-lookup"><span data-stu-id="6c6ed-140">Scan > Scan packed executables</span></span> | <span data-ttu-id="6c6ed-141">已启用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-141">Enabled</span></span> | <span data-ttu-id="6c6ed-142">不可用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-142">Not available</span></span>
<span data-ttu-id="6c6ed-143">仅在完全扫描期间扫描可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="6c6ed-143">Scan removable drives during full scans only</span></span> | <span data-ttu-id="6c6ed-144">扫描>扫描可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="6c6ed-144">Scan > Scan removable drives</span></span> | <span data-ttu-id="6c6ed-145">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-145">Disabled</span></span> | `-DisableRemovableDriveScanning`
<span data-ttu-id="6c6ed-146">指定要扫描的存档文件夹中的子文件夹级别</span><span class="sxs-lookup"><span data-stu-id="6c6ed-146">Specify the level of subfolders within an archive folder to scan</span></span> | <span data-ttu-id="6c6ed-147">扫描>指定扫描存档文件的最大深度</span><span class="sxs-lookup"><span data-stu-id="6c6ed-147">Scan > Specify the maximum depth to scan archive files</span></span> | <span data-ttu-id="6c6ed-148">0</span><span class="sxs-lookup"><span data-stu-id="6c6ed-148">0</span></span> | <span data-ttu-id="6c6ed-149">不可用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-149">Not available</span></span>
 <span data-ttu-id="6c6ed-150">指定最大 CPU 负载 (以扫描) 的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-150">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <span data-ttu-id="6c6ed-151">注意：这不是硬性限制，而是指导扫描引擎平均不超过此最大值。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-151">Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average.</span></span> | <span data-ttu-id="6c6ed-152">扫描>指定扫描期间 CPU 使用率的最大百分比</span><span class="sxs-lookup"><span data-stu-id="6c6ed-152">Scan > Specify the maximum percentage of CPU utilization during a scan</span></span> | <span data-ttu-id="6c6ed-153">50</span><span class="sxs-lookup"><span data-stu-id="6c6ed-153">50</span></span> |  `-ScanAvgCPULoadFactor`
 <span data-ttu-id="6c6ed-154">指定应 (存档) 的最大大小（以 KB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-154">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <span data-ttu-id="6c6ed-155">默认值 **0** 没有限制</span><span class="sxs-lookup"><span data-stu-id="6c6ed-155">The default, **0**, applies no limit</span></span> | <span data-ttu-id="6c6ed-156">扫描>指定要扫描的存档文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="6c6ed-156">Scan > Specify the maximum size of archive files to be scanned</span></span> | <span data-ttu-id="6c6ed-157">无限制</span><span class="sxs-lookup"><span data-stu-id="6c6ed-157">No limit</span></span> | <span data-ttu-id="6c6ed-158">不可用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-158">Not available</span></span>
 <span data-ttu-id="6c6ed-159">为计划扫描配置低 CPU 优先级</span><span class="sxs-lookup"><span data-stu-id="6c6ed-159">Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="6c6ed-160">扫描>配置计划扫描的低 CPU 优先级</span><span class="sxs-lookup"><span data-stu-id="6c6ed-160">Scan > Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="6c6ed-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-161">Disabled</span></span> | <span data-ttu-id="6c6ed-162">不可用</span><span class="sxs-lookup"><span data-stu-id="6c6ed-162">Not available</span></span>
 
> [!NOTE]
> <span data-ttu-id="6c6ed-163">如果启用实时保护，则先扫描文件，然后再访问和执行文件。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-163">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="6c6ed-164">扫描范围包括所有文件，包括装载的可移动媒体（如 USB 驱动器）上的文件。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-164">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="6c6ed-165">如果执行扫描的设备已打开实时保护或访问保护，则扫描还将包括网络共享。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-165">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="6c6ed-166">使用 PowerShell 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-166">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="6c6ed-167">请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 Defender [cmdlet](/powershell/module/defender/) 管理 Microsoft Defender 防病毒，详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-167">See [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="6c6ed-168">使用 WMI 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="6c6ed-168">Use WMI to configure scanning options</span></span>

<span data-ttu-id="6c6ed-169">有关使用 WMI 类，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="6c6ed-169">For using WMI classes, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a><span data-ttu-id="6c6ed-170">电子邮件扫描限制</span><span class="sxs-lookup"><span data-stu-id="6c6ed-170">Email scanning limitations</span></span>

<span data-ttu-id="6c6ed-171">电子邮件扫描支持在按需扫描和计划扫描期间扫描 Outlook 和其他邮件客户端使用的电子邮件文件。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-171">Email scanning enables scanning of  email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="6c6ed-172">电子邮件文件中嵌入的对象 (附件和存档文件) 扫描。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-172">Embedded objects within an email file (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="6c6ed-173">可以扫描和修正以下文件格式类型：</span><span class="sxs-lookup"><span data-stu-id="6c6ed-173">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="6c6ed-174">DBX</span><span class="sxs-lookup"><span data-stu-id="6c6ed-174">DBX</span></span>
- <span data-ttu-id="6c6ed-175">MBX</span><span class="sxs-lookup"><span data-stu-id="6c6ed-175">MBX</span></span>
- <span data-ttu-id="6c6ed-176">MIME</span><span class="sxs-lookup"><span data-stu-id="6c6ed-176">MIME</span></span>

<span data-ttu-id="6c6ed-177">Outlook 2003 或较旧版本使用的 PST 文件 (其中存档类型设置为非 unicode) 也将进行扫描，但 Windows Defender 无法修正在 PST 文件内检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="6c6ed-177">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) will also be scanned, but Windows Defender cannot remediate threats detected inside PST files.</span></span>

<span data-ttu-id="6c6ed-178">如果 Microsoft Defender 防病毒检测到电子邮件内的威胁，它将显示以下信息来帮助你识别遭到入侵的电子邮件，以便你可以手动修正威胁：</span><span class="sxs-lookup"><span data-stu-id="6c6ed-178">If Microsoft Defender Antivirus detects a threat inside an email, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="6c6ed-179">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="6c6ed-179">Email subject</span></span>
- <span data-ttu-id="6c6ed-180">附件名称</span><span class="sxs-lookup"><span data-stu-id="6c6ed-180">Attachment name</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c6ed-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="6c6ed-181">Related topics</span></span>

- [<span data-ttu-id="6c6ed-182">自定义、启动和查看 Microsoft Defender 防病毒扫描和修正的结果</span><span class="sxs-lookup"><span data-stu-id="6c6ed-182">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6c6ed-183">配置并运行按需 Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="6c6ed-183">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6c6ed-184">配置计划的 Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="6c6ed-184">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6c6ed-185">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="6c6ed-185">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)