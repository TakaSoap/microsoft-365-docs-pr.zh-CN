---
title: 配置扫描选项进行Microsoft Defender 防病毒
description: 你可以将 Microsoft Defender AV 配置为扫描电子邮件存储文件、备份或重新分析点、网络文件和存档文件 (如.zip文件) 。
keywords: 高级扫描， 扫描， 电子邮件， 存档， zip， rar， 存档， 重新分析扫描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964893"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="f15bf-104">配置 Microsoft Defender 防病毒软件扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-104">Configure Microsoft Defender Antivirus scanning options</span></span>

<span data-ttu-id="f15bf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f15bf-105">**Applies to:**</span></span>

- [<span data-ttu-id="f15bf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f15bf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="f15bf-107">使用Microsoft Intune配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="f15bf-108">有关详细信息，[请参阅在](/intune/device-restrictions-configure)Intune 中Microsoft Intune配置Microsoft Defender 防病毒[设备限制Windows 10设置](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="f15bf-108">For more information, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span> 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="f15bf-109">使用Microsoft Endpoint Manager配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="f15bf-110">有关配置当前分支Microsoft Endpoint Manager (的详细信息，) 如何创建[和部署反恶意软件策略：扫描设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。</span><span class="sxs-lookup"><span data-stu-id="f15bf-110">For details on configuring Microsoft Endpoint Manager (current branch), see [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="f15bf-111">使用组策略配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-111">Use Group Policy to configure scanning options</span></span>

1. <span data-ttu-id="f15bf-112">在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="f15bf-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="f15bf-113">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="f15bf-113">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="f15bf-114">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="f15bf-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

4. <span data-ttu-id="f15bf-115">展开树以 **Windows** 组件Microsoft Defender 防病毒，然后选择一个位置 (请参阅本文中的设置  >  和) 。 [](#settings-and-locations)</span><span class="sxs-lookup"><span data-stu-id="f15bf-115">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**, and then select a location (refer to [Settings and locations](#settings-and-locations) in this article).</span></span>


5. <span data-ttu-id="f15bf-116">编辑策略对象。</span><span class="sxs-lookup"><span data-stu-id="f15bf-116">Edit the policy object.</span></span> 

6. <span data-ttu-id="f15bf-117">单击 **"确定**"，然后对任何其他设置重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="f15bf-117">Click **OK**, and repeat for any other settings.</span></span>

### <a name="settings-and-locations"></a><span data-ttu-id="f15bf-118">设置和位置</span><span class="sxs-lookup"><span data-stu-id="f15bf-118">Settings and locations</span></span>

| <span data-ttu-id="f15bf-119">策略项和位置</span><span class="sxs-lookup"><span data-stu-id="f15bf-119">Policy item and location</span></span> | <span data-ttu-id="f15bf-120">如果未 (默认设置) </span><span class="sxs-lookup"><span data-stu-id="f15bf-120">Default setting (if not configured)</span></span> | <span data-ttu-id="f15bf-121">类的 PowerShell `Set-MpPreference` 参数或 WMI `MSFT_MpPreference` 属性</span><span class="sxs-lookup"><span data-stu-id="f15bf-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span> |
|---|---|---|
| <span data-ttu-id="f15bf-122">电子邮件扫描</span><span class="sxs-lookup"><span data-stu-id="f15bf-122">Email scanning</span></span> <p> <span data-ttu-id="f15bf-123">**扫描**  > **打开电子邮件扫描**</span><span class="sxs-lookup"><span data-stu-id="f15bf-123">**Scan** > **Turn on e-mail scanning**</span></span><p><span data-ttu-id="f15bf-124">请参阅 [本文中的电子邮件](#email-scanning-limitations) (限制) </span><span class="sxs-lookup"><span data-stu-id="f15bf-124">See [Email scanning limitations](#email-scanning-limitations) (in this article)</span></span> | <span data-ttu-id="f15bf-125">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-125">Disabled</span></span> | `-DisableEmailScanning` |
|<span data-ttu-id="f15bf-126">扫描 [重新分析点](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="f15bf-126">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> <p> <span data-ttu-id="f15bf-127">**扫描**  > **打开重新分析点扫描**</span><span class="sxs-lookup"><span data-stu-id="f15bf-127">**Scan** > **Turn on reparse point scanning**</span></span> | <span data-ttu-id="f15bf-128">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-128">Disabled</span></span> | <span data-ttu-id="f15bf-129">不可用</span><span class="sxs-lookup"><span data-stu-id="f15bf-129">Not available</span></span> <p><span data-ttu-id="f15bf-130">请参阅 [重新分析点](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="f15bf-130">See [Reparse points](/windows/win32/fileio/reparse-points)</span></span>  |
| <span data-ttu-id="f15bf-131">扫描映射的网络驱动器</span><span class="sxs-lookup"><span data-stu-id="f15bf-131">Scan mapped network drives</span></span> <p> <span data-ttu-id="f15bf-132">**扫描**  > **在映射的网络驱动器上运行完全扫描**</span><span class="sxs-lookup"><span data-stu-id="f15bf-132">**Scan** > **Run full scan on mapped network drives**</span></span> | <span data-ttu-id="f15bf-133">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-133">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`|
| <span data-ttu-id="f15bf-134">扫描存档 (，如.zip或.rar文件) 。</span><span class="sxs-lookup"><span data-stu-id="f15bf-134">Scan archive files (such as .zip or .rar files).</span></span>  <p> <span data-ttu-id="f15bf-135">**扫描**  > **扫描存档文件**</span><span class="sxs-lookup"><span data-stu-id="f15bf-135">**Scan** > **Scan archive files**</span></span> | <span data-ttu-id="f15bf-136">已启用</span><span class="sxs-lookup"><span data-stu-id="f15bf-136">Enabled</span></span> | `-DisableArchiveScanning` <p><span data-ttu-id="f15bf-137">扩展 [名排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 将优先于此设置。</span><span class="sxs-lookup"><span data-stu-id="f15bf-137">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span>|
| <span data-ttu-id="f15bf-138">扫描网络文件</span><span class="sxs-lookup"><span data-stu-id="f15bf-138">Scan files on the network</span></span> <p> <span data-ttu-id="f15bf-139">**扫描**  > **扫描网络文件**</span><span class="sxs-lookup"><span data-stu-id="f15bf-139">**Scan** > **Scan network files**</span></span> | <span data-ttu-id="f15bf-140">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-140">Disabled</span></span> | `-DisableScanningNetworkFiles` |
| <span data-ttu-id="f15bf-141">扫描打包的可执行文件</span><span class="sxs-lookup"><span data-stu-id="f15bf-141">Scan packed executables</span></span> <p> <span data-ttu-id="f15bf-142">**扫描**  > **扫描打包的可执行文件**</span><span class="sxs-lookup"><span data-stu-id="f15bf-142">**Scan** > **Scan packed executables**</span></span> | <span data-ttu-id="f15bf-143">已启用</span><span class="sxs-lookup"><span data-stu-id="f15bf-143">Enabled</span></span> | <span data-ttu-id="f15bf-144">不可用</span><span class="sxs-lookup"><span data-stu-id="f15bf-144">Not available</span></span> |
| <span data-ttu-id="f15bf-145">仅在完全扫描期间扫描可移动驱动器</span><span class="sxs-lookup"><span data-stu-id="f15bf-145">Scan removable drives during full scans only</span></span> <p> <span data-ttu-id="f15bf-146">**扫描**  > **扫描可移动驱动器**</span><span class="sxs-lookup"><span data-stu-id="f15bf-146">**Scan** > **Scan removable drives**</span></span> | <span data-ttu-id="f15bf-147">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-147">Disabled</span></span> | `-DisableRemovableDriveScanning` |
| <span data-ttu-id="f15bf-148">指定要扫描的存档文件夹中的子文件夹级别</span><span class="sxs-lookup"><span data-stu-id="f15bf-148">Specify the level of subfolders within an archive folder to scan</span></span> <p><span data-ttu-id="f15bf-149">**扫描**  > **指定扫描存档文件的最大深度**</span><span class="sxs-lookup"><span data-stu-id="f15bf-149">**Scan** > **Specify the maximum depth to scan archive files**</span></span> | <span data-ttu-id="f15bf-150">0</span><span class="sxs-lookup"><span data-stu-id="f15bf-150">0</span></span> | <span data-ttu-id="f15bf-151">不可用</span><span class="sxs-lookup"><span data-stu-id="f15bf-151">Not available</span></span> |
| <span data-ttu-id="f15bf-152">指定最大 CPU 负载 (以扫描) 的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="f15bf-152">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <p> <span data-ttu-id="f15bf-153">**扫描**  > **指定扫描期间 CPU 使用率的最大百分比**</span><span class="sxs-lookup"><span data-stu-id="f15bf-153">**Scan** > **Specify the maximum percentage of CPU utilization during a scan**</span></span> | <span data-ttu-id="f15bf-154">50</span><span class="sxs-lookup"><span data-stu-id="f15bf-154">50</span></span> |  `-ScanAvgCPULoadFactor` <p><span data-ttu-id="f15bf-155">**注意**：最大 CPU 负载不是硬性限制，但指导扫描引擎平均不超过最大值。</span><span class="sxs-lookup"><span data-stu-id="f15bf-155">**NOTE**: The maximum CPU load is not a hard limit, but is guidance for the scanning engine to not exceed the maximum on average.</span></span> <span data-ttu-id="f15bf-156">手动运行扫描将忽略此设置，并且运行时没有任何 CPU 限制。</span><span class="sxs-lookup"><span data-stu-id="f15bf-156">Manually run scans will ignore this setting and run without any CPU limits.</span></span> |
| <span data-ttu-id="f15bf-157">指定应 (存档) 的最大大小（以 KB 为单位）。</span><span class="sxs-lookup"><span data-stu-id="f15bf-157">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <p> <span data-ttu-id="f15bf-158">**扫描**  > **指定要扫描的存档文件的最大大小**</span><span class="sxs-lookup"><span data-stu-id="f15bf-158">**Scan** > **Specify the maximum size of archive files to be scanned**</span></span> | <span data-ttu-id="f15bf-159">无限制</span><span class="sxs-lookup"><span data-stu-id="f15bf-159">No limit</span></span> | <span data-ttu-id="f15bf-160">不可用</span><span class="sxs-lookup"><span data-stu-id="f15bf-160">Not available</span></span> <p><span data-ttu-id="f15bf-161">默认值 0 没有限制</span><span class="sxs-lookup"><span data-stu-id="f15bf-161">The default value of 0 applies no limit</span></span> |
| <span data-ttu-id="f15bf-162">为计划扫描配置低 CPU 优先级</span><span class="sxs-lookup"><span data-stu-id="f15bf-162">Configure low CPU priority for scheduled scans</span></span> <p> <span data-ttu-id="f15bf-163">**扫描**  > **为计划扫描配置低 CPU 优先级**</span><span class="sxs-lookup"><span data-stu-id="f15bf-163">**Scan** > **Configure low CPU priority for scheduled scans**</span></span> | <span data-ttu-id="f15bf-164">禁用</span><span class="sxs-lookup"><span data-stu-id="f15bf-164">Disabled</span></span> | <span data-ttu-id="f15bf-165">不可用</span><span class="sxs-lookup"><span data-stu-id="f15bf-165">Not available</span></span> |

 
> [!NOTE]
> <span data-ttu-id="f15bf-166">如果启用实时保护，则先扫描文件，然后再访问和执行文件。</span><span class="sxs-lookup"><span data-stu-id="f15bf-166">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="f15bf-167">扫描范围包括所有文件，包括装载的可移动媒体（如 USB 驱动器）上的文件。</span><span class="sxs-lookup"><span data-stu-id="f15bf-167">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="f15bf-168">如果执行扫描的设备已打开实时保护或访问保护，则扫描还将包括网络共享。</span><span class="sxs-lookup"><span data-stu-id="f15bf-168">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="f15bf-169">使用 PowerShell 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-169">Use PowerShell to configure scanning options</span></span>


<span data-ttu-id="f15bf-170">若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一起使用，请参阅</span><span class="sxs-lookup"><span data-stu-id="f15bf-170">For more information on how to use PowerShell with Microsoft Defender Antivirus, see</span></span>

- [<span data-ttu-id="f15bf-171">使用 PowerShell cmdlet Microsoft Defender 防病毒管理配置</span><span class="sxs-lookup"><span data-stu-id="f15bf-171">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f15bf-172">Defender cmdlet</span><span class="sxs-lookup"><span data-stu-id="f15bf-172">Defender cmdlets</span></span>](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="f15bf-173">使用 WMI 配置扫描选项</span><span class="sxs-lookup"><span data-stu-id="f15bf-173">Use WMI to configure scanning options</span></span>

<span data-ttu-id="f15bf-174">请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f15bf-174">See [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="email-scanning-limitations"></a><span data-ttu-id="f15bf-175">电子邮件扫描限制</span><span class="sxs-lookup"><span data-stu-id="f15bf-175">Email scanning limitations</span></span>

<span data-ttu-id="f15bf-176">电子邮件扫描支持在按需扫描和计划Outlook客户端使用的电子邮件文件扫描。</span><span class="sxs-lookup"><span data-stu-id="f15bf-176">Email scanning enables scanning of email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="f15bf-177">电子邮件中的嵌入对象 (附件和存档文件) 扫描。</span><span class="sxs-lookup"><span data-stu-id="f15bf-177">Embedded objects within email (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="f15bf-178">可以扫描和修正以下文件格式类型：</span><span class="sxs-lookup"><span data-stu-id="f15bf-178">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="f15bf-179">DBX</span><span class="sxs-lookup"><span data-stu-id="f15bf-179">DBX</span></span>
- <span data-ttu-id="f15bf-180">MBX</span><span class="sxs-lookup"><span data-stu-id="f15bf-180">MBX</span></span>
- <span data-ttu-id="f15bf-181">MIME</span><span class="sxs-lookup"><span data-stu-id="f15bf-181">MIME</span></span>

<span data-ttu-id="f15bf-182">Outlook 2003 或 (其中存档类型设置为非 unicode) 的 PST 文件也会被扫描，但 Microsoft Defender 防病毒 无法修正在 PST 文件中检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="f15bf-182">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) are also scanned, but Microsoft Defender Antivirus cannot remediate threats that are detected inside PST files.</span></span>

<span data-ttu-id="f15bf-183">如果你Microsoft Defender 防病毒电子邮件内检测到威胁，它将显示以下信息来帮助你识别遭到入侵的电子邮件，以便你可以手动修正威胁：</span><span class="sxs-lookup"><span data-stu-id="f15bf-183">If Microsoft Defender Antivirus detects a threat inside an email message, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="f15bf-184">电子邮件主题</span><span class="sxs-lookup"><span data-stu-id="f15bf-184">Email subject</span></span>
- <span data-ttu-id="f15bf-185">附件名称</span><span class="sxs-lookup"><span data-stu-id="f15bf-185">Attachment name</span></span>


## <a name="scanning-mapped-network-drives"></a><span data-ttu-id="f15bf-186">扫描映射的网络驱动器</span><span class="sxs-lookup"><span data-stu-id="f15bf-186">Scanning mapped network drives</span></span>

<span data-ttu-id="f15bf-187">在任何操作系统上，仅扫描在系统级别映射的网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="f15bf-187">On any OS, only the network drives that are mapped at system level, are scanned.</span></span> <span data-ttu-id="f15bf-188">不扫描用户级别映射的网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="f15bf-188">User-level mapped network drives aren't scanned.</span></span> <span data-ttu-id="f15bf-189">用户级别的映射网络驱动器是用户手动使用自己的凭据在会话中映射的驱动器。</span><span class="sxs-lookup"><span data-stu-id="f15bf-189">User-level mapped network drives are those that a user maps in their session manually and using their own credentials.</span></span>

## <a name="see-also"></a><span data-ttu-id="f15bf-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f15bf-190">See also</span></span>


- [<span data-ttu-id="f15bf-191">自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果</span><span class="sxs-lookup"><span data-stu-id="f15bf-191">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f15bf-192">配置并运行按需 Microsoft Defender 防病毒软件扫描</span><span class="sxs-lookup"><span data-stu-id="f15bf-192">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f15bf-193">配置计划Microsoft Defender 防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="f15bf-193">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f15bf-194">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="f15bf-194">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
