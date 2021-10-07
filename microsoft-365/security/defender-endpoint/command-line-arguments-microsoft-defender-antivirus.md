---
title: 使用命令行管理Microsoft Defender 防病毒
description: 运行Microsoft Defender 防病毒专用命令行实用工具扫描和配置下一代保护。
keywords: 运行 windows defender 扫描， 从命令行运行防病毒扫描， 从命令行运行 windows defender 扫描， mpcmdrun， defender
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: f377126eb56291f6ea0c43502f42916f8d64adee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213117"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>使用 Microsoft Defender 防病毒 命令行mpcmdrun.exe配置和管理应用程序

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

您可以使用专用的命令行工具Microsoft Defender 防病毒中执行各种 **mpcmdrun.exe。** 当您希望自动执行任务时，此实用工具Microsoft Defender 防病毒很有用。 可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 从命令提示符运行它。

> [!TIP]
> 您可能需要打开命令提示符的管理员级别版本。 当您在命令提示 **符** 上搜索命令"开始"菜单，选择以 **管理员角色运行**。 如果你运行的是更新的 Microsoft Defender 平台版本，请 `MpCmdRun` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` ：。 有关反恶意软件平台详细信息，请参阅Microsoft Defender 防病毒[更新和基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

MpCmdRun 实用工具使用下列语法：

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
|`-?` **或者** `-h`|显示 MpCmdRun 工具的所有可用选项|
|`-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]`|扫描恶意软件。 **ScanType 的值为**：<p>**0** 默认，根据你的配置<p>**1** 快速扫描<p>**2** 完全扫描<p>**3** 文件和目录自定义扫描。<p>CpuThrottling 根据策略配置运行|
|`-Trace [-Grouping #] [-Level #]`|启动诊断跟踪|
|`-GetFiles [-SupportLogLocation <path>]`|收集支持信息。 请参阅'[收集诊断数据](collect-diagnostic-data.md)'|
|`-GetFilesDiagTrack`|与 `-GetFiles` 相同，但输出到临时 DiagTrack 文件夹|
|`-RemoveDefinitions [-All]`|将安装的安全智能还原到以前的备份副本或原始默认集|
|`-RemoveDefinitions [-DynamicSignatures]`|仅删除动态下载的安全智能|
|`-RemoveDefinitions [-Engine]`|还原以前安装的引擎|
|`-SignatureUpdate [-UNC \|-MMPC]`|检查新的安全智能更新|
|`-Restore  [-ListAll \|[[-Name <name>] [-All] \|[-FilePath <filePath>]] [-Path <path>]]`|还原或列出已隔离 (项) |
|`-AddDynamicSignature [-Path]`|加载动态安全智能|
|`-ListAllDynamicSignatures`|列出已加载的动态安全智能|
|`-RemoveDynamicSignature [-SignatureSetID]`|删除动态安全智能|
|`-CheckExclusion -path <path>`|检查是否排除路径|
|`-ValidateMapsConnection`|验证你的网络能否与 Microsoft Defender 防病毒 云服务通信。 此命令仅适用于 Windows 10版本 1703 或更高版本。|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>通过命令运行命令的常见mpcmdrun.exe

下表列出了使用 MpCmdRun 工具时可能会发生的常见错误。

|错误消息|可能的原因|
|---|---|
|**ValidateMapsConnection (800106BA** **) 失败0x800106BA**|禁用Microsoft Defender 防病毒服务。 启用该服务，然后重试。 如果你需要有关重新启用Microsoft Defender 防病毒的帮助，请参阅[在终结点Microsoft Defender 防病毒/启用应用](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。<p> **提示**：在 Windows 10 1909 或较早版本，Windows Server 2019 或更旧版本中，该服务以前称为 *Windows Defender 防病毒。*|
|**0x80070667**|您运行的是版本 1607 或Windows 10版本，或版本或Windows Server 2016 `-ValidateMapsConnection` 的计算机。 从版本 1703 或Windows 10或更高版本或 Windows Server 2019 或更高版本运行命令。|
|**MpCmdRun 无法识别为内部或外部命令、可操作程序或批处理文件。**|该工具必须从任一或 (`%ProgramFiles%\Windows Defender` 运行，其中可能有所不同，因为除了 3 月之外，平台更新 `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 是每月) |
|**ValidateMapsConnection 未能建立与 MAPS (hr=80070005 httpcode=450)**|试图使用权限不足的命令。 以管理员 (cmd.exe) 命令提示符。|
|**ValidateMapsConnection 未能建立与 MAPS (hr=80070006 httpcode=451)**|防火墙阻止连接或执行 SSL 检查。|
|**ValidateMapsConnection 未能建立到 MAPS (hr=80004005 httpcode=450)**|可能的网络相关问题，如名称解析问题|
|**ValidateMapsConnection 未能建立与 MAPS (hr=0x80508015**|防火墙阻止连接或执行 SSL 检查。|
|**ValidateMapsConnection 未能建立与 MAPS (hr=800722F0D 的连接**|防火墙阻止连接或执行 SSL 检查。|
|**ValidateMapsConnection 未能建立与 MAPS (hr=80072EE7 httpcode=451)**|防火墙阻止连接或执行 SSL 检查。|

## <a name="see-also"></a>另请参阅

- [配置 Microsoft Defender 防病毒软件功能](configure-microsoft-defender-antivirus-features.md)
- [配置和验证 Microsoft Defender 防病毒软件网络连接](configure-network-connections-microsoft-defender-antivirus.md)
- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
