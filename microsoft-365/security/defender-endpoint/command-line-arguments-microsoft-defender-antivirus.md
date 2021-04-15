---
title: 使用命令行管理 Microsoft Defender 防病毒
description: 运行 Microsoft Defender 防病毒扫描，然后使用专用的命令行实用工具配置下一代保护。
keywords: 运行 windows defender 扫描， 从命令行运行防病毒扫描， 从命令行运行 windows defender 扫描， mpcmdrun， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764623"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="712c3-104">使用命令行工具配置mpcmdrun.exe Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="712c3-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="712c3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="712c3-105">**Applies to:**</span></span>

- [<span data-ttu-id="712c3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="712c3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="712c3-107">可以使用专用的命令行工具执行各种 Microsoft Defender 防病毒 **mpcmdrun.exe。**</span><span class="sxs-lookup"><span data-stu-id="712c3-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="712c3-108">当你希望自动使用 Microsoft Defender 防病毒时，此实用工具非常有用。</span><span class="sxs-lookup"><span data-stu-id="712c3-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="712c3-109">可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="712c3-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="712c3-110">必须从命令提示符运行它。</span><span class="sxs-lookup"><span data-stu-id="712c3-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="712c3-111">您可能需要打开命令提示符的管理员级别版本。</span><span class="sxs-lookup"><span data-stu-id="712c3-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="712c3-112">在"开始"菜单 **上** 搜索命令提示符时，选择"**以管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="712c3-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="712c3-113">如果你运行的是更新的 Microsoft Defender 平台版本，请 `**MpCmdRun**` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ：。</span><span class="sxs-lookup"><span data-stu-id="712c3-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="712c3-114">该实用工具具有以下命令：</span><span class="sxs-lookup"><span data-stu-id="712c3-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="712c3-115">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="712c3-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="712c3-116">命令</span><span class="sxs-lookup"><span data-stu-id="712c3-116">Command</span></span>  | <span data-ttu-id="712c3-117">说明</span><span class="sxs-lookup"><span data-stu-id="712c3-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="712c3-118">`-?` **或** `-h`</span><span class="sxs-lookup"><span data-stu-id="712c3-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="712c3-119">显示此工具的所有可用选项</span><span class="sxs-lookup"><span data-stu-id="712c3-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="712c3-120">扫描恶意软件。</span><span class="sxs-lookup"><span data-stu-id="712c3-120">Scans for malicious software.</span></span> <span data-ttu-id="712c3-121">**ScanType** 的值为 **：0** 默认值，根据你的配置 **，-1** 快速扫描 **，-2** 完全扫描 **，-3** 文件和目录自定义扫描。</span><span class="sxs-lookup"><span data-stu-id="712c3-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="712c3-122">CpuThrottling 将遵守策略中配置的 CPU 限制</span><span class="sxs-lookup"><span data-stu-id="712c3-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="712c3-123">启动诊断跟踪</span><span class="sxs-lookup"><span data-stu-id="712c3-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="712c3-124">收集支持信息。</span><span class="sxs-lookup"><span data-stu-id="712c3-124">Collects support information.</span></span> <span data-ttu-id="712c3-125">请参阅'[收集诊断数据](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="712c3-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="712c3-126">与 `-GetFiles` 相同，但输出到临时 DiagTrack 文件夹</span><span class="sxs-lookup"><span data-stu-id="712c3-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="712c3-127">将安装的安全智能还原到以前的备份副本或原始默认集</span><span class="sxs-lookup"><span data-stu-id="712c3-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="712c3-128">仅删除动态下载的安全智能</span><span class="sxs-lookup"><span data-stu-id="712c3-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="712c3-129">还原以前安装的引擎</span><span class="sxs-lookup"><span data-stu-id="712c3-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="712c3-130">检查新的安全智能更新</span><span class="sxs-lookup"><span data-stu-id="712c3-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="712c3-131">还原或列出已隔离 (项) </span><span class="sxs-lookup"><span data-stu-id="712c3-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="712c3-132">加载动态安全智能</span><span class="sxs-lookup"><span data-stu-id="712c3-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="712c3-133">列出已加载的动态安全智能</span><span class="sxs-lookup"><span data-stu-id="712c3-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="712c3-134">删除动态安全智能</span><span class="sxs-lookup"><span data-stu-id="712c3-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="712c3-135">检查路径是否被排除</span><span class="sxs-lookup"><span data-stu-id="712c3-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="712c3-136">验证网络能否与 Microsoft Defender 防病毒云服务通信。</span><span class="sxs-lookup"><span data-stu-id="712c3-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="712c3-137">此命令仅适用于 Windows 10 版本 1703 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="712c3-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="712c3-138">通过命令运行命令时出现mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="712c3-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="712c3-139">错误消息</span><span class="sxs-lookup"><span data-stu-id="712c3-139">Error message</span></span> | <span data-ttu-id="712c3-140">可能的原因</span><span class="sxs-lookup"><span data-stu-id="712c3-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="712c3-141">Microsoft Defender 防病毒服务已禁用。</span><span class="sxs-lookup"><span data-stu-id="712c3-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="712c3-142">启用该服务，然后重试。</span><span class="sxs-lookup"><span data-stu-id="712c3-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="712c3-143">**注意：**  在 Windows 10 1909 或较早版本以及 Windows Server 2019 或较早版本中，该服务以前称为"Windows Defender防病毒"服务。</span><span class="sxs-lookup"><span data-stu-id="712c3-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="712c3-144">你正在从 Windows 10 版本 1607 或较早版本或 `-ValidateMapsConnection` Windows Server 2016 或较旧版本的计算机运行命令。</span><span class="sxs-lookup"><span data-stu-id="712c3-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="712c3-145">从 Windows 10 版本 1703 或更高版本、Windows Server 2019 或更高版本计算机运行命令。</span><span class="sxs-lookup"><span data-stu-id="712c3-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="712c3-146">该工具需要从以下两者之一运行 (，其中可能会有所不同，因为除了 3 月之外，平台更新是每月) `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0`</span><span class="sxs-lookup"><span data-stu-id="712c3-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="712c3-147">权限不足。</span><span class="sxs-lookup"><span data-stu-id="712c3-147">Not enough privileges.</span></span> <span data-ttu-id="712c3-148">以管理员 (cmd.exe) 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="712c3-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="712c3-149">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="712c3-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="712c3-150">可能的网络相关问题，如名称解析问题</span><span class="sxs-lookup"><span data-stu-id="712c3-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="712c3-151">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="712c3-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="712c3-152">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="712c3-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="712c3-153">防火墙阻止连接或执行 SSL 检查。</span><span class="sxs-lookup"><span data-stu-id="712c3-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="712c3-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="712c3-154">See also</span></span>

- [<span data-ttu-id="712c3-155">配置 Microsoft Defender 防病毒软件功能</span><span class="sxs-lookup"><span data-stu-id="712c3-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="712c3-156">管理企业中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="712c3-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="712c3-157">有关管理和配置工具的参考主题</span><span class="sxs-lookup"><span data-stu-id="712c3-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="712c3-158">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="712c3-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)