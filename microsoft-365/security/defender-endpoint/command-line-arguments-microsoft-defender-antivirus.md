---
title: 使用命令行管理Microsoft Defender 防病毒
description: 运行Microsoft Defender 防病毒扫描并使用专用命令行实用工具配置下一代保护。
keywords: 运行 Windows Defender 扫描，从命令行运行防病毒扫描，从命令行、mpcmdrun、defender 运行 Windows Defender 扫描
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 97f818469f9da2616ca5ca2839ddf29ea227b85f
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789725"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>使用mpcmdrun.exe命令行工具配置和管理Microsoft Defender 防病毒

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒 

**平台**
- Windows

可以使用专用命令行工具mpcmdrun.exe在Microsoft Defender 防病毒中执行各种 **函数**。 当你想要自动执行Microsoft Defender 防病毒任务时，此实用工具非常有用。 你可以在 `%ProgramFiles%\Windows Defender\MpCmdRun.exe`其中找到实用工具。 从命令提示符运行它。

> [!TIP]
> 可能需要打开命令提示符的管理员级版本。 在"开始"菜单上搜索 **命令提示符** 时，选择 **“以管理员身份运行**”。 如果正在运行更新的 Microsoft Defender 反恶意软件平台版本，请从以下位置运行`MpCmdRun`： `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 有关反恶意软件平台的详细信息，请参阅[Microsoft Defender 防病毒更新和基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

MpCmdRun 实用工具使用以下语法：

```console
MpCmdRun.exe [command] [-options]
```

下面是一个示例：

```console
MpCmdRun.exe -Scan -ScanType 2
```

在我们的示例中，MpCmdRun 实用工具在设备上启动完全防病毒扫描。

## <a name="commands"></a>命令

|命令|说明|
|---|---|
|`-?` **或** `-h`|显示 MpCmdRun 工具的所有可用选项|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|扫描恶意软件。 **ScanType** 的值为：<p>**0** 默认值，根据配置<p>**1** 快速扫描<p>**2** 完全扫描<p>**3** 文件和目录自定义扫描。<p>CpuThrottling 根据策略配置运行|
|`-Trace [-Grouping #] [-Level #]`|开始诊断跟踪|
|`-GetFiles [-SupportLogLocation <path>]`|收集支持信息。 请参阅“[收集诊断数据](collect-diagnostic-data.md)”|
|`-GetFilesDiagTrack`|与此相同 `-GetFiles`，但输出到临时 DiagTrack 文件夹|
|`-RemoveDefinitions [-All]`|将已安装的安全智能还原到以前的备份副本或原始默认集|
|`-RemoveDefinitions [-DynamicSignatures]`|仅删除动态下载的安全智能|
|`-RemoveDefinitions [-Engine]`|还原以前安装的引擎|
|`-SignatureUpdate [-UNC \|-MMPC]`|检查新的安全智能更新|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|还原或列出隔离项 () |
|`-AddDynamicSignature [-Path]`|加载动态安全智能|
|`-ListAllDynamicSignatures`|列出加载的动态安全智能|
|`-RemoveDynamicSignature [-SignatureSetID]`|删除动态安全智能|
|`-CheckExclusion -path <path>`|检查是否排除路径|
|`-ValidateMapsConnection`|验证网络是否可以与Microsoft Defender 防病毒云服务通信。 此命令仅适用于Windows 10版本 1703 或更高版本。|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>通过mpcmdrun.exe运行命令时出现的常见错误

下表列出了使用 MpCmdRun 工具时可能发生的常见错误。

|错误消息|可能的原因|
|---|---|
|**validateMapsConnection 失败 (800106BA)** 或 **0x800106BA**|禁用Microsoft Defender 防病毒服务。 启用服务，然后重试。 如果需要帮助重新启用Microsoft Defender 防病毒，请参阅[终结点上的重新安装/启用Microsoft Defender 防病毒](switch-to-mde-phase-2.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。<p> **提示**：在 1909 Windows 10或更早版本，Windows服务器 2019 或更早版本，该服务以前称为 *Windows Defender 防病毒*。|
|**0x80070667**|你正在从Windows 10版本 1607 或更早版本或Windows Server 2016或更早版本的计算机运行`-ValidateMapsConnection`该命令。 从Windows 10版本 1703 或更高版本的计算机或Windows服务器 2019 或更高版本运行命令。|
|**不将 MpCmdRun 识别为内部或外部命令、可操作程序或批处理文件。**|该工具必须从任何一个 `%ProgramFiles%\Windows Defender` 或 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (运行，因为 `2012.4-0` 平台更新是每月的，但 3 月) |
|**ValidateMapsConnection 未能与 MAPS 建立连接 (hr=80070005 httpcode=450)**|尝试使用权限不足的命令。 以管理员身份使用命令提示符 (cmd.exe) 。|
|**ValidateMapsConnection 未能与 MAPS 建立连接 (hr=80070006 httpcode=451)**|防火墙正在阻止连接或进行 SSL 检查。|
|**ValidateMapsConnection 未能与 MAPS 建立连接 (hr=80004005 httpcode=450)**|可能的网络相关问题，例如名称解析问题|
|**ValidateMapsConnection 未能与 MAPS 建立连接 (hr=0x80508015**|防火墙正在阻止连接或进行 SSL 检查。|
|**ValidateMapsConnection 未能建立到 MAPS (hr=800722F0D 的连接**|防火墙正在阻止连接或进行 SSL 检查。|
|**ValidateMapsConnection 未能建立到 MAPS (hr=80072EE7 httpcode=451)**|防火墙正在阻止连接或进行 SSL 检查。|

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [配置 Microsoft Defender 防病毒软件功能](configure-microsoft-defender-antivirus-features.md)
- [配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md)
- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
