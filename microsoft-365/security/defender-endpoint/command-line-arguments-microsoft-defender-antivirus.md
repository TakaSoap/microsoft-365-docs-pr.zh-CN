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
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538899"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="db555-104">使用 Microsoft Defender 防病毒命令行工具mpcmdrun.exe和管理应用程序</span><span class="sxs-lookup"><span data-stu-id="db555-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="db555-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="db555-105">**Applies to:**</span></span>

- [<span data-ttu-id="db555-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="db555-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="db555-107">您可以使用专用的命令行Microsoft Defender 防病毒执行各种命令行 **mpcmdrun.exe。**</span><span class="sxs-lookup"><span data-stu-id="db555-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="db555-108">当您希望自动执行 Microsoft Defender 防病毒时，此实用工具非常有用。</span><span class="sxs-lookup"><span data-stu-id="db555-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="db555-109">可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="db555-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="db555-110">必须从命令提示符运行它。</span><span class="sxs-lookup"><span data-stu-id="db555-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="db555-111">您可能需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="db555-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="db555-112">在"开始"菜单 **上** 搜索命令提示符时，选择"**以管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="db555-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="db555-113">如果你运行的是更新的 Microsoft Defender 平台版本，请 `**MpCmdRun**` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` ：。</span><span class="sxs-lookup"><span data-stu-id="db555-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="db555-114">有关反恶意软件平台详细信息，请参阅Microsoft Defender 防病毒[更新和基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="db555-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="db555-115">MpCmdRun 实用工具使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="db555-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="db555-116">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="db555-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="db555-117">命令</span><span class="sxs-lookup"><span data-stu-id="db555-117">Command</span></span>  | <span data-ttu-id="db555-118">说明</span><span class="sxs-lookup"><span data-stu-id="db555-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="db555-119">`-?`**或**`-h`</span><span class="sxs-lookup"><span data-stu-id="db555-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="db555-120">显示此工具的所有可用选项</span><span class="sxs-lookup"><span data-stu-id="db555-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="db555-121">扫描恶意软件。</span><span class="sxs-lookup"><span data-stu-id="db555-121">Scans for malicious software.</span></span> <span data-ttu-id="db555-122">**ScanType 的值为**：</span><span class="sxs-lookup"><span data-stu-id="db555-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="db555-123">**0** 默认，根据你的配置</span><span class="sxs-lookup"><span data-stu-id="db555-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="db555-124">**-1** 快速扫描</span><span class="sxs-lookup"><span data-stu-id="db555-124">**-1** Quick scan</span></span><p><span data-ttu-id="db555-125">**-2** 完全扫描</span><span class="sxs-lookup"><span data-stu-id="db555-125">**-2** Full scan</span></span><p><span data-ttu-id="db555-126">**-3** 文件和目录自定义扫描。</span><span class="sxs-lookup"><span data-stu-id="db555-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="db555-127">CpuThrottling 将遵守策略中配置的 CPU 限制</span><span class="sxs-lookup"><span data-stu-id="db555-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="db555-128">启动诊断跟踪</span><span class="sxs-lookup"><span data-stu-id="db555-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="db555-129">收集支持信息。</span><span class="sxs-lookup"><span data-stu-id="db555-129">Collects support information.</span></span> <span data-ttu-id="db555-130">请参阅'[收集诊断数据](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="db555-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="db555-131">与 `-GetFiles` 相同，但输出到临时 DiagTrack 文件夹</span><span class="sxs-lookup"><span data-stu-id="db555-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="db555-132">将安装的安全智能还原到以前的备份副本或原始默认集</span><span class="sxs-lookup"><span data-stu-id="db555-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="db555-133">仅删除动态下载的安全智能</span><span class="sxs-lookup"><span data-stu-id="db555-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="db555-134">还原以前安装的引擎</span><span class="sxs-lookup"><span data-stu-id="db555-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="db555-135">检查新的安全智能更新</span><span class="sxs-lookup"><span data-stu-id="db555-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="db555-136">还原或列出已隔离 (项) </span><span class="sxs-lookup"><span data-stu-id="db555-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="db555-137">加载动态安全智能</span><span class="sxs-lookup"><span data-stu-id="db555-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="db555-138">列出已加载的动态安全智能</span><span class="sxs-lookup"><span data-stu-id="db555-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="db555-139">删除动态安全智能</span><span class="sxs-lookup"><span data-stu-id="db555-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="db555-140">检查路径是否被排除</span><span class="sxs-lookup"><span data-stu-id="db555-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="db555-141">验证你的网络能否与 Microsoft Defender 防病毒 云服务通信。</span><span class="sxs-lookup"><span data-stu-id="db555-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="db555-142">此命令仅适用于版本Windows 10版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="db555-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="db555-143">通过命令运行命令时出现mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="db555-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="db555-144">错误消息</span><span class="sxs-lookup"><span data-stu-id="db555-144">Error message</span></span> | <span data-ttu-id="db555-145">可能的原因</span><span class="sxs-lookup"><span data-stu-id="db555-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="db555-146">禁用Microsoft Defender 防病毒服务。</span><span class="sxs-lookup"><span data-stu-id="db555-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="db555-147">启用该服务，然后重试。</span><span class="sxs-lookup"><span data-stu-id="db555-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="db555-148">**注意：** 在 Windows 10 1909 或 1909 或Windows Server 2019 或更旧版本中，该服务以前称为 *Windows Defender 防病毒* 服务。</span><span class="sxs-lookup"><span data-stu-id="db555-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="db555-149">您运行的命令来自版本 `-ValidateMapsConnection` 1607 或Windows 10版本或版本Windows Server 2016版本的计算机。</span><span class="sxs-lookup"><span data-stu-id="db555-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="db555-150">从版本 1703 或Windows 10或更高版本或 Windows Server 2019 或更高版本运行命令。</span><span class="sxs-lookup"><span data-stu-id="db555-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="db555-151">该工具需要从以下两者之一运行 (，其中可能会有所不同，因为除了 3 月之外，平台更新是每月) `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0`</span><span class="sxs-lookup"><span data-stu-id="db555-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="db555-152">权限不足。</span><span class="sxs-lookup"><span data-stu-id="db555-152">Not enough privileges.</span></span> <span data-ttu-id="db555-153">以管理员 (cmd.exe) 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="db555-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="db555-154">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="db555-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="db555-155">可能的网络相关问题，如名称解析问题</span><span class="sxs-lookup"><span data-stu-id="db555-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="db555-156">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="db555-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="db555-157">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="db555-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="db555-158">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="db555-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="db555-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db555-159">See also</span></span>

- [<span data-ttu-id="db555-160">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="db555-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="db555-161">管理Microsoft Defender 防病毒中的业务</span><span class="sxs-lookup"><span data-stu-id="db555-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="db555-162">有关管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="db555-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="db555-163">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="db555-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)