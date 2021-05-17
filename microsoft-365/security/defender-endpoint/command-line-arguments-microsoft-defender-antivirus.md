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
ms.date: 03/19/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 85fb60d8d4504ba3a4aa8744c1183d094da01a9b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274744"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>使用 Microsoft Defender 防病毒命令行工具mpcmdrun.exe和管理应用程序

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

您可以使用专用的命令行Microsoft Defender 防病毒执行各种命令行 **mpcmdrun.exe。** 当您希望自动执行 Microsoft Defender 防病毒时，此实用工具非常有用。 可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 必须从命令提示符运行它。

> [!NOTE]
> 您可能需要打开命令提示符的管理员级别版本。 在"开始"菜单 **上** 搜索命令提示符时，选择"**以管理员角色运行"。**
> 如果你运行的是更新的 Microsoft Defender 平台版本，请 `**MpCmdRun**` 从以下位置运行 `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ：。

该实用工具具有以下命令：

```console
MpCmdRun.exe [command] [-options]
```
下面是一个示例：

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| 命令  | 说明   |
|:----|:----|
| `-?`**或**`-h`   | 显示此工具的所有可用选项 |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 扫描恶意软件。 **ScanType** 的值为 **：0** 默认值，根据你的配置 **，-1** 快速扫描 **，-2** 完全扫描 **，-3** 文件和目录自定义扫描。  CpuThrottling 将遵守策略中配置的 CPU 限制 |
| `-Trace [-Grouping #] [-Level #]` | 启动诊断跟踪 |
| `-GetFiles [-SupportLogLocation <path>]` | 收集支持信息。 请参阅'[收集诊断数据](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | 与 `-GetFiles` 相同，但输出到临时 DiagTrack 文件夹 |
| `-RemoveDefinitions [-All]` | 将安装的安全智能还原到以前的备份副本或原始默认集 |
| `-RemoveDefinitions [-DynamicSignatures]` | 仅删除动态下载的安全智能 |
| `-RemoveDefinitions [-Engine]` | 还原以前安装的引擎 |
| `-SignatureUpdate [-UNC \| -MMPC]` | 检查新的安全智能更新 |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | 还原或列出已隔离 (项)  |
| `-AddDynamicSignature [-Path]` | 加载动态安全智能 |
| `-ListAllDynamicSignatures` | 列出已加载的动态安全智能 |
| `-RemoveDynamicSignature [-SignatureSetID]` | 删除动态安全智能 |
| `-CheckExclusion -path <path>` | 检查路径是否被排除 |
| `-ValidateMapsConnection` | 验证你的网络能否与 Microsoft Defender 防病毒 云服务通信。 此命令仅适用于版本Windows 10版本 1703 或更高版本。|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>通过命令运行命令时出现mpcmdrun.exe 

|错误消息 | 可能的原因
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | 禁用Microsoft Defender 防病毒服务。 启用该服务，然后重试。 <br>   **注意：** 在 Windows 10 1909 或Windows Server 2019 或更旧版本中，该服务以前称为"Windows Defender 防病毒"服务。|
| `0x80070667` | 您运行的命令来自版本 `-ValidateMapsConnection` 1607 或Windows 10版本或版本Windows Server 2016版本的计算机。 从版本 1703 或Windows 10或更高版本或 Windows Server 2019 或更高版本运行命令。|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | 该工具需要从以下两者之一运行 (，其中可能会有所不同，因为除了 3 月之外，平台更新是每月) `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0`|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 权限不足。 以管理员 (cmd.exe) 命令提示符。|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | 防火墙阻止连接或执行 SSL 检查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 可能的网络相关问题，如名称解析问题|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | 防火墙阻止连接或执行 SSL 检查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | 防火墙阻止连接或执行 SSL 检查。 |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | 防火墙阻止连接或执行 SSL 检查。 |

## <a name="see-also"></a>另请参阅

- [配置 Microsoft Defender 防病毒软件功能](configure-microsoft-defender-antivirus-features.md)
- [管理Microsoft Defender 防病毒中的业务](configuration-management-reference-microsoft-defender-antivirus.md)
- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)