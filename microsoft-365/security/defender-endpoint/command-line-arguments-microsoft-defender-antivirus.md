---
title: 使用命令行管理Microsoft Defender 防病毒
description: 运行Microsoft Defender 防病毒专用命令行实用工具扫描和配置下一代保护。
keywords: 运行 windows defender 扫描， 从命令行运行防病毒扫描， 从命令行运行 windows defender 扫描， mpcmdrun， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289411"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="c823a-104">使用 Microsoft Defender 防病毒命令行工具mpcmdrun.exe和管理应用程序</span><span class="sxs-lookup"><span data-stu-id="c823a-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="c823a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c823a-105">**Applies to:**</span></span>

- [<span data-ttu-id="c823a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c823a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c823a-107">您可以使用专用的命令行工具Microsoft Defender 防病毒中执行各种 **mpcmdrun.exe。**</span><span class="sxs-lookup"><span data-stu-id="c823a-107">You can perform various functions in Microsoft Defender Antivirus using the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="c823a-108">当您希望自动执行任务时，此实用工具Microsoft Defender 防病毒很有用。</span><span class="sxs-lookup"><span data-stu-id="c823a-108">This utility is useful when you want to automate Microsoft Defender Antivirus tasks.</span></span> <span data-ttu-id="c823a-109">可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="c823a-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="c823a-110">从命令提示符运行它。</span><span class="sxs-lookup"><span data-stu-id="c823a-110">Run it from a command prompt.</span></span>

> [!TIP]
> <span data-ttu-id="c823a-111">您可能需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="c823a-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="c823a-112">当你在命令提示 **符** 上搜索命令"开始"菜单，选择以 **管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="c823a-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span> <span data-ttu-id="c823a-113">如果你运行的是更新的 Microsoft Defender 平台版本，请 `MpCmdRun` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` ：。</span><span class="sxs-lookup"><span data-stu-id="c823a-113">If you're running an updated Microsoft Defender Platform version, run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span> <span data-ttu-id="c823a-114">有关反恶意软件平台详细信息，请参阅Microsoft Defender 防病毒[更新和基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="c823a-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c823a-115">MpCmdRun 实用工具使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="c823a-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="c823a-116">示例如下：</span><span class="sxs-lookup"><span data-stu-id="c823a-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

<span data-ttu-id="c823a-117">在我们的示例中，MpCmdRun 实用工具在设备上启动完全防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="c823a-117">In our example, the MpCmdRun utility starts a full antivirus scan on the device.</span></span>

## <a name="commands"></a><span data-ttu-id="c823a-118">命令</span><span class="sxs-lookup"><span data-stu-id="c823a-118">Commands</span></span>

| <span data-ttu-id="c823a-119">命令</span><span class="sxs-lookup"><span data-stu-id="c823a-119">Command</span></span>  | <span data-ttu-id="c823a-120">说明</span><span class="sxs-lookup"><span data-stu-id="c823a-120">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="c823a-121">`-?` **或** `-h`</span><span class="sxs-lookup"><span data-stu-id="c823a-121">`-?` **or** `-h`</span></span>   | <span data-ttu-id="c823a-122">显示 MpCmdRun 工具的所有可用选项</span><span class="sxs-lookup"><span data-stu-id="c823a-122">Displays all available options for the MpCmdRun tool</span></span> |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="c823a-123">扫描恶意软件。</span><span class="sxs-lookup"><span data-stu-id="c823a-123">Scans for malicious software.</span></span> <span data-ttu-id="c823a-124">**ScanType 的值为**：</span><span class="sxs-lookup"><span data-stu-id="c823a-124">Values for **ScanType** are:</span></span><p><span data-ttu-id="c823a-125">**0** 默认，根据你的配置</span><span class="sxs-lookup"><span data-stu-id="c823a-125">**0** Default, according to your configuration</span></span><p><span data-ttu-id="c823a-126">**1** 快速扫描</span><span class="sxs-lookup"><span data-stu-id="c823a-126">**1** Quick scan</span></span><p><span data-ttu-id="c823a-127">**2** 完全扫描</span><span class="sxs-lookup"><span data-stu-id="c823a-127">**2** Full scan</span></span><p><span data-ttu-id="c823a-128">**3** 文件和目录自定义扫描。</span><span class="sxs-lookup"><span data-stu-id="c823a-128">**3** File and directory custom scan.</span></span><p><span data-ttu-id="c823a-129">CpuThrottling 根据策略配置运行</span><span class="sxs-lookup"><span data-stu-id="c823a-129">CpuThrottling runs according to policy configurations</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="c823a-130">启动诊断跟踪</span><span class="sxs-lookup"><span data-stu-id="c823a-130">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="c823a-131">收集支持信息。</span><span class="sxs-lookup"><span data-stu-id="c823a-131">Collects support information.</span></span> <span data-ttu-id="c823a-132">请参阅'[收集诊断数据](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="c823a-132">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="c823a-133">与 `-GetFiles` 相同，但输出到临时 DiagTrack 文件夹</span><span class="sxs-lookup"><span data-stu-id="c823a-133">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="c823a-134">将安装的安全智能还原到以前的备份副本或原始默认集</span><span class="sxs-lookup"><span data-stu-id="c823a-134">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="c823a-135">仅删除动态下载的安全智能</span><span class="sxs-lookup"><span data-stu-id="c823a-135">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="c823a-136">还原以前安装的引擎</span><span class="sxs-lookup"><span data-stu-id="c823a-136">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="c823a-137">检查新的安全智能更新</span><span class="sxs-lookup"><span data-stu-id="c823a-137">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="c823a-138">还原或列出已隔离 (项) </span><span class="sxs-lookup"><span data-stu-id="c823a-138">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="c823a-139">加载动态安全智能</span><span class="sxs-lookup"><span data-stu-id="c823a-139">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="c823a-140">列出已加载的动态安全智能</span><span class="sxs-lookup"><span data-stu-id="c823a-140">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="c823a-141">删除动态安全智能</span><span class="sxs-lookup"><span data-stu-id="c823a-141">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="c823a-142">检查路径是否被排除</span><span class="sxs-lookup"><span data-stu-id="c823a-142">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="c823a-143">验证你的网络能否与 Microsoft Defender 防病毒 云服务通信。</span><span class="sxs-lookup"><span data-stu-id="c823a-143">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="c823a-144">此命令仅适用于版本Windows 10版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c823a-144">This command will only work on Windows 10, version 1703 or higher.</span></span>|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="c823a-145">通过命令运行命令时出现mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="c823a-145">Common errors in running commands via mpcmdrun.exe</span></span> 

<span data-ttu-id="c823a-146">下表列出了使用 MpCmdRun 工具时可能会发生的常见错误。</span><span class="sxs-lookup"><span data-stu-id="c823a-146">The following table lists common errors that can occur while using the MpCmdRun tool.</span></span>

|<span data-ttu-id="c823a-147">错误消息</span><span class="sxs-lookup"><span data-stu-id="c823a-147">Error message</span></span> | <span data-ttu-id="c823a-148">可能的原因</span><span class="sxs-lookup"><span data-stu-id="c823a-148">Possible reason</span></span> |
|:----|:----|
| <span data-ttu-id="c823a-149">**ValidateMapsConnection (800106BA** **) 失败0x800106BA**</span><span class="sxs-lookup"><span data-stu-id="c823a-149">**ValidateMapsConnection failed (800106BA)** or **0x800106BA**</span></span> | <span data-ttu-id="c823a-150">禁用Microsoft Defender 防病毒服务。</span><span class="sxs-lookup"><span data-stu-id="c823a-150">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="c823a-151">启用该服务，然后重试。</span><span class="sxs-lookup"><span data-stu-id="c823a-151">Enable the service and try again.</span></span> <span data-ttu-id="c823a-152">如果需要有关重新启用Microsoft Defender 防病毒的帮助，请参阅[在终结点Microsoft Defender 防病毒/启用策略](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="c823a-152">If you need help re-enabling Microsoft Defender Antivirus, see [Reinstall/enable Microsoft Defender Antivirus on your endpoints](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).</span></span><p> <span data-ttu-id="c823a-153">**提示**：在 Windows 10 1909 或更旧版本，Windows Server 2019 或更旧版本中，该服务以前称为 *Windows Defender 防病毒。*</span><span class="sxs-lookup"><span data-stu-id="c823a-153">**TIP**: In Windows 10 1909 or older, and Windows Server 2019 or older, the service was formerly called *Windows Defender Antivirus*.</span></span> |
| <span data-ttu-id="c823a-154">**0x80070667**</span><span class="sxs-lookup"><span data-stu-id="c823a-154">**0x80070667**</span></span> | <span data-ttu-id="c823a-155">您运行的命令来自版本 `-ValidateMapsConnection` 1607 或Windows 10版本或版本Windows Server 2016版本的计算机。</span><span class="sxs-lookup"><span data-stu-id="c823a-155">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="c823a-156">从版本 1703 或Windows 10或更高版本或 Windows Server 2019 或更高版本运行命令。</span><span class="sxs-lookup"><span data-stu-id="c823a-156">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| <span data-ttu-id="c823a-157">**MpCmdRun 无法识别为内部或外部命令、可操作程序或批处理文件。**</span><span class="sxs-lookup"><span data-stu-id="c823a-157">**MpCmdRun is not recognized as an internal or external command, operable program, or batch file.**</span></span> | <span data-ttu-id="c823a-158">该工具必须从任一或 (`%ProgramFiles%\Windows Defender` 运行，其中 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 可能有所不同，因为平台更新是每月更新，但 3 月除外) </span><span class="sxs-lookup"><span data-stu-id="c823a-158">The tool must be run from either `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| <span data-ttu-id="c823a-159">**ValidateMapsConnection 未能建立与 MAPS (hr=80070005 httpcode=450)**</span><span class="sxs-lookup"><span data-stu-id="c823a-159">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)**</span></span> | <span data-ttu-id="c823a-160">试图使用权限不足的命令。</span><span class="sxs-lookup"><span data-stu-id="c823a-160">The command was attempted using insufficient privileges.</span></span> <span data-ttu-id="c823a-161">以管理员 (cmd.exe) 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c823a-161">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| <span data-ttu-id="c823a-162">**ValidateMapsConnection 未能建立与 MAPS (hr=80070006 httpcode=451)**</span><span class="sxs-lookup"><span data-stu-id="c823a-162">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)**</span></span> | <span data-ttu-id="c823a-163">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="c823a-163">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="c823a-164">**ValidateMapsConnection 未能建立与 MAPS (hr=80004005 httpcode=450)**</span><span class="sxs-lookup"><span data-stu-id="c823a-164">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)**</span></span> | <span data-ttu-id="c823a-165">可能的网络相关问题，如名称解析问题</span><span class="sxs-lookup"><span data-stu-id="c823a-165">Possible network-related issues, like name resolution problems</span></span>|
| <span data-ttu-id="c823a-166">**ValidateMapsConnection 未能建立与 MAPS (hr=0x80508015**</span><span class="sxs-lookup"><span data-stu-id="c823a-166">**ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015**</span></span> | <span data-ttu-id="c823a-167">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="c823a-167">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="c823a-168">**ValidateMapsConnection 未能建立与 MAPS (hr=800722F0D 的连接**</span><span class="sxs-lookup"><span data-stu-id="c823a-168">**ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D**</span></span> | <span data-ttu-id="c823a-169">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="c823a-169">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="c823a-170">**ValidateMapsConnection 未能建立与 MAPS (hr=80072EE7 httpcode=451)**</span><span class="sxs-lookup"><span data-stu-id="c823a-170">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)**</span></span> | <span data-ttu-id="c823a-171">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="c823a-171">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c823a-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c823a-172">See also</span></span>

- [<span data-ttu-id="c823a-173">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="c823a-173">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="c823a-174">配置和验证 Microsoft Defender 防病毒软件网络连接</span><span class="sxs-lookup"><span data-stu-id="c823a-174">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c823a-175">有关管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="c823a-175">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
