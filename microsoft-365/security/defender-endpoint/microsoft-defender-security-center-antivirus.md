---
title: Microsoft Defender 防病毒应用中Windows 安全中心
description: 现在Microsoft Defender 防病毒应用程序中包含的Windows 安全中心，你可以查看、比较和执行常见任务。
keywords: wdav， 防病毒， 防火墙， 安全， windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 48ab72e9700e45cd4eab520a43d6f3d9ef18e227
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926519"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="bd328-104">Microsoft Defender 防病毒应用中Windows 安全中心</span><span class="sxs-lookup"><span data-stu-id="bd328-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bd328-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bd328-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd328-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd328-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd328-107">在 Windows 10 版本 1703 及更高版本中，Windows Defender应用是 Windows 安全中心。</span><span class="sxs-lookup"><span data-stu-id="bd328-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="bd328-108">设置以前属于 Windows Defender 客户端和主 Windows 设置 的客户端已组合并移动到新应用，该应用默认作为 Windows 10 版本 1703 的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="bd328-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd328-109">禁用 Windows 安全中心 中心服务不会禁用Microsoft Defender 防病毒或[Windows Defender 防火墙。](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="bd328-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="bd328-110">当安装第三方防病毒或防火墙产品并保持最新时，将自动禁用这些功能。</span><span class="sxs-lookup"><span data-stu-id="bd328-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="bd328-111">如果禁用 Windows 安全中心 中心服务，或将其关联的组策略设置配置为阻止其启动或运行，Windows 安全中心 应用可能会显示有关设备上安装的任何防病毒或防火墙产品的过时或不准确信息。</span><span class="sxs-lookup"><span data-stu-id="bd328-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="bd328-112">如果具有Microsoft Defender 防病毒或过时的第三方防病毒程序，或者卸载之前可能安装的任何第三方防病毒产品，它也可能阻止用户自行启用。</span><span class="sxs-lookup"><span data-stu-id="bd328-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="bd328-113">这将显著降低设备的保护，并可能导致恶意软件感染。</span><span class="sxs-lookup"><span data-stu-id="bd328-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="bd328-114">有关[可在Windows 安全中心](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)监视的其他 Windows 安全功能，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="bd328-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="bd328-115">Windows 安全中心应用是 Windows 10 版本 1703 及更高版本上的客户端接口。</span><span class="sxs-lookup"><span data-stu-id="bd328-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="bd328-116">这不是用于Microsoft Defender 安全中心 Microsoft [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)的 Web 门户。</span><span class="sxs-lookup"><span data-stu-id="bd328-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="bd328-117">查看应用程序应用中的病毒和威胁Windows 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="bd328-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Windows 安全应用中病毒和威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="bd328-119">通过Windows 安全中心任务栏中的防护图标或搜索 Defender 的"开始"菜单打开"开始 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="bd328-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="bd328-120">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="bd328-121">以下各节介绍如何在查看或与应用中的 Microsoft Defender 防病毒 所提供的威胁防护交互时执行一些最常见的Windows 安全中心任务。</span><span class="sxs-lookup"><span data-stu-id="bd328-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="bd328-122">如果使用组策略配置和部署这些设置，本部分中所述的设置将灰出，并且无法用于各个终结点。</span><span class="sxs-lookup"><span data-stu-id="bd328-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="bd328-123">通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。</span><span class="sxs-lookup"><span data-stu-id="bd328-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="bd328-124">Configure [end-user interaction with Microsoft Defender 防病毒](configure-end-user-interaction-microsoft-defender-antivirus.md)主题介绍了如何配置本地策略覆盖设置。</span><span class="sxs-lookup"><span data-stu-id="bd328-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="bd328-125">使用应用运行Windows 安全中心扫描</span><span class="sxs-lookup"><span data-stu-id="bd328-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="bd328-126">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-127">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-128">选择 **快速扫描**。</span><span class="sxs-lookup"><span data-stu-id="bd328-128">Select **Quick scan**.</span></span> <span data-ttu-id="bd328-129">或者，若要运行完全扫描，请选择"扫描选项"，然后选择一个选项，例如"**完全扫描"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="bd328-130">查看安全智能更新版本，并下载 Windows 安全中心 应用中的最新更新</span><span class="sxs-lookup"><span data-stu-id="bd328-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![安全智能版本号信息](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="bd328-132">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-133">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-134">选择 **病毒&威胁防护更新**。</span><span class="sxs-lookup"><span data-stu-id="bd328-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="bd328-135">将显示当前安装的版本以及一些有关下载时间的信息。</span><span class="sxs-lookup"><span data-stu-id="bd328-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="bd328-136">你可以根据可供手动下载的最新版本检查当前版本，或查看该版本的更改日志。</span><span class="sxs-lookup"><span data-stu-id="bd328-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="bd328-137">请参阅[安全智能更新，Microsoft Defender 防病毒 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="bd328-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="bd328-138">选择 **"检查更新"，** 以下载 (保护更新（如果有) ）。</span><span class="sxs-lookup"><span data-stu-id="bd328-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="bd328-139">确保Microsoft Defender 防病毒应用中启用了Windows 安全中心功能</span><span class="sxs-lookup"><span data-stu-id="bd328-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="bd328-140">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-141">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-142">选择 **病毒&威胁防护设置**。</span><span class="sxs-lookup"><span data-stu-id="bd328-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="bd328-143">将 **"实时保护"开关切换** 为 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd328-144">如果关闭 **实时保护，** 它将在短暂延迟后自动重新启用。</span><span class="sxs-lookup"><span data-stu-id="bd328-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="bd328-145">这是为了确保你免受恶意软件和威胁的侵害。</span><span class="sxs-lookup"><span data-stu-id="bd328-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="bd328-146">如果安装另一个防病毒产品，Microsoft Defender 防病毒自动禁用自身，并会在 Windows 安全中心 应用中指示。</span><span class="sxs-lookup"><span data-stu-id="bd328-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="bd328-147">将显示一个设置，允许您启用 [有限定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bd328-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="bd328-148">在应用Microsoft Defender 防病毒添加Windows 安全中心项</span><span class="sxs-lookup"><span data-stu-id="bd328-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="bd328-149">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-150">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-151">在"**管理设置"下**，选择 **"病毒&威胁防护设置"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="bd328-152">在"**排除项"** 设置下，选择 **"添加或删除排除项"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="bd328-153">Select the plus icon () **+** to choose the type and set the options for each exclusion.</span><span class="sxs-lookup"><span data-stu-id="bd328-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="bd328-154">下表汇总了排除类型以及发生的情况：</span><span class="sxs-lookup"><span data-stu-id="bd328-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="bd328-155">排除类型</span><span class="sxs-lookup"><span data-stu-id="bd328-155">Exclusion type</span></span>  |<span data-ttu-id="bd328-156">定义者</span><span class="sxs-lookup"><span data-stu-id="bd328-156">Defined by</span></span>  |<span data-ttu-id="bd328-157">发生的情况</span><span class="sxs-lookup"><span data-stu-id="bd328-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bd328-158">**文件**</span><span class="sxs-lookup"><span data-stu-id="bd328-158">**File**</span></span> |<span data-ttu-id="bd328-159">位置</span><span class="sxs-lookup"><span data-stu-id="bd328-159">Location</span></span> <br/><span data-ttu-id="bd328-160">例如：`c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="bd328-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="bd328-161">特定文件将被用户跳过Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bd328-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="bd328-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="bd328-162">**Folder**</span></span>    |<span data-ttu-id="bd328-163">位置</span><span class="sxs-lookup"><span data-stu-id="bd328-163">Location</span></span> <br/><span data-ttu-id="bd328-164">例如：`c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="bd328-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="bd328-165">指定文件夹中的所有项目都将被用户跳过Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bd328-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="bd328-166">**文件类型**</span><span class="sxs-lookup"><span data-stu-id="bd328-166">**File type**</span></span>   |<span data-ttu-id="bd328-167">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="bd328-167">File extension</span></span> <br/><span data-ttu-id="bd328-168">例如：`.test`</span><span class="sxs-lookup"><span data-stu-id="bd328-168">Example: `.test`</span></span> |<span data-ttu-id="bd328-169">设备上任意位置 `.test` 具有扩展名的所有文件都将被用户跳过Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bd328-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="bd328-170">**进程**</span><span class="sxs-lookup"><span data-stu-id="bd328-170">**Process**</span></span>     |<span data-ttu-id="bd328-171">可执行文件路径</span><span class="sxs-lookup"><span data-stu-id="bd328-171">Executable file path</span></span> <br><span data-ttu-id="bd328-172">例如：`c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="bd328-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="bd328-173">特定进程以及该流程打开的任何文件都将被用户跳过Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bd328-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="bd328-174">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="bd328-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="bd328-175">根据文件扩展名和文件夹位置配置和验证排除项</span><span class="sxs-lookup"><span data-stu-id="bd328-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="bd328-176">为进程打开的文件配置排除项</span><span class="sxs-lookup"><span data-stu-id="bd328-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="bd328-177">查看安全中心应用中Windows Defender检测历史记录</span><span class="sxs-lookup"><span data-stu-id="bd328-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="bd328-178">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-179">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-180">选择 **"保护历史记录"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-180">Select **Protection history**.</span></span> <span data-ttu-id="bd328-181">将列出任何最近的项目。</span><span class="sxs-lookup"><span data-stu-id="bd328-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="bd328-182">设置勒索软件保护和恢复选项</span><span class="sxs-lookup"><span data-stu-id="bd328-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="bd328-183">通过Windows 安全中心"安全"的"开始"菜单，然后选择"开始"菜单，打开 **"Windows 安全中心"。**</span><span class="sxs-lookup"><span data-stu-id="bd328-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="bd328-184">选择病毒 **&威胁** 防护磁贴 (或左侧菜单栏上的防护) 。</span><span class="sxs-lookup"><span data-stu-id="bd328-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="bd328-185">在 **勒索软件保护下**，选择 **管理勒索软件保护**。</span><span class="sxs-lookup"><span data-stu-id="bd328-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="bd328-186">若要更改 **受控文件夹访问权限** 设置，请参阅使用受控 [文件夹访问权限保护重要文件夹](/microsoft-365/security/defender-endpoint/controlled-folders)。</span><span class="sxs-lookup"><span data-stu-id="bd328-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="bd328-187">若要设置勒索软件恢复选项，请选择勒索软件数据恢复下的"设置"，并按照链接或设置 OneDrive 帐户的说明操作，以便你可以轻松从勒索软件攻击中恢复。</span><span class="sxs-lookup"><span data-stu-id="bd328-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd328-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd328-188">See also</span></span>
- [<span data-ttu-id="bd328-189">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bd328-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)