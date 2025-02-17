---
title: 用于在 Windows 上进行高级故障排除的数据收集
description: 了解如何使用客户端分析器收集复杂疑难解答方案的数据
keywords: analzyer， 收集数据， 疑难解答 mdeclientanalyzer， 高级疑难解答
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2825bc87750dc9bb130e35f9a4997283e470f869
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469880"
---
# <a name="data-collection-for-advanced-troubleshooting-on-windows"></a>用于在 Windows 上进行高级故障排除的数据收集

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

与 Microsoft 支持专业人员协作时，系统可能会要求您使用客户端分析器收集数据，以排查更复杂的方案。 分析器脚本支持用于此目的的其他参数，并可以基于需要调查的观察到症状收集特定日志集。

运行"**MDEClientAnalyzer.cmd /？**" 查看可用参数的列表及其说明：

:::image type="content" source="images/d89a1c04cf8441e4df72005879871bd0.png" alt-text="MDEClientAnalyzer.cmd 的参数" lightbox="images/d89a1c04cf8441e4df72005879871bd0.png":::

> [!NOTE]
> 使用任何高级疑难解答参数时，分析器还会调用MpCmdRun.exe[ ](/microsoft-365/security/defender-endpoint/command-line-arguments-microsoft-defender-antivirus)以收集Microsoft Defender 防病毒支持日志。

**-h** - [调用Windows记录](/windows-hardware/test/wpt/wpr-command-line-options)器以收集详细的常规性能跟踪以及标准日志集。

**-l** - 调用内置性能 [Windows](/windows-server/remote/remote-desktop-services/rds-rdsh-performance-counters)以收集轻型 perfmon 跟踪。 在诊断随着时间的推移而难以按需重现的缓慢性能降低问题时，这可能很有用。

**-c** - 调用 [进程监视器](/sysinternals/downloads/procmon) 以对实时文件系统、注册表和进程/线程活动进行高级监视。 当对各种应用程序兼容性方案进行疑难解答时，这尤其有用。

**-i** - 调用内置netsh.exe命令以 [](/windows/win32/winsock/netsh-exe)启动网络和 Windows 防火墙跟踪，这些跟踪在排查各种网络相关问题时很有用。

**-b** - 与"-c"相同，但进程监视器跟踪将在下次启动期间启动，并且仅在再次使用 -b 时停止。

**-a** - [调用Windows](/windows-hardware/test/wpt/wpr-command-line-options)记录器以收集特定于与防病毒进程 (MsMpEng.exe) 相关的高 CPU 问题分析的具体性能跟踪。

**-v** - 使用MpCmdRun.exe [ 最详细 -](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus) trace 标志的命令行参数。

**-t** - 启动与 Endpoint DLP 相关的所有客户端组件详细跟踪。 这适用于 [DLP](/microsoft-365/compliance/endpoint-dlp-learn-about#endpoint-activities-you-can-monitor-and-take-action-on) 操作未如预期发生的文件方案。

**-q** - 从验证 Endpoint DLP DLPDiagnose.ps1配置和要求的分析器"工具"目录中调用脚本。

**-d** - 收集 MsSenseS 的内存转储，.exe (或较旧的操作系统Windows Server 2016及相关) 进程上的传感器进程。

- \* 此标志可与上述标志结合使用。
- \*\* 目前，分析器不支持捕获 [受 PPL](/windows-hardware/drivers/install/early-launch-antimalware) MsSense.exe或 MsMpEng.exe 进程的内存转储。

**-z** - 配置计算机上注册表项，以通过 [CrashOnCtrlScroll](/windows-hardware/drivers/debugger/forcing-a-system-crash-from-the-keyboard) 准备用于完整的计算机内存转储集合。 这对分析计算机冻结问题非常有用。

\* 按住最右边的 Ctrl 键，然后按 SCROLL LOCK 键两次。

**-k** - 使用 [NotMyFault](/sysinternals/downloads/notmyfault) 工具强制系统崩溃并生成计算机内存转储。 这对分析各种操作系统稳定性问题非常有用。

分析器以及上述所有方案标志可通过运行"RemoteMDEClientAnalyzer.cmd"远程启动，"RemoteMDEClientAnalyzer.cmd"也会捆绑到分析工具集：

:::image type="content" source="images/57cab9d82d08f672a92bf9e748ac9572.png" alt-text="RemoteMDEClientAnalyzer.cmd 的参数" lightbox="images/57cab9d82d08f672a92bf9e748ac9572.png":::

> [!NOTE]
>
> - 使用 RemoteMDEClientAnalyzer.cmd 时，它会调用 psexec 以从配置的文件共享下载该工具，然后通过 PsExec.exe 本地运行它。
    CMD 脚本使用"-r"标志指定它在 SYSTEM 上下文中远程运行，因此不会向用户显示任何提示。
> - 该标志可以与 MDEClientAnalyzer.cmd 一同使用，以避免提示用户请求指定数据收集的分钟数。 例如：
>
>    **MDEClientAnalyzer.cmd -r -i -m 5**
>
>   - **-r** - 指示工具正在从远程环境或非交互 (运行) 
>   - **-i** - 用于收集网络跟踪以及其他相关日志的方案标志
>   - **-m** \# - 上述示例中运行 (5 分钟的分钟数) 
