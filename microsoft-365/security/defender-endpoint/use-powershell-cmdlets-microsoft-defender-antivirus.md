---
title: 使用 PowerShell cmdlet 配置和运行Microsoft Defender 防病毒
description: 在Windows 10和Windows 11中，可以使用 PowerShell cmdlet 在Microsoft Defender 防病毒中运行扫描、更新安全智能和更改设置。
keywords: scan， 命令行， mpcmdrun， defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 1cd19ff6010badd7386e937dfddb4420e76335b0
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790303"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 PowerShell cmdlet 配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用 PowerShell 在Windows Defender中执行各种函数。 与命令提示符或命令行类似，PowerShell 是一种基于任务的命令行 shell 和脚本语言，专为系统管理而设计。 可以在 [MSDN 上的 PowerShell 中心](/previous-versions/msdn10/mt173057(v=msdn.10))阅读有关它的详细信息。

有关 cmdlet 及其函数和可用参数的列表，请参阅 [Defender 防病毒 cmdlet](/powershell/module/defender) 主题。

PowerShell cmdlet 在不依赖于图形用户界面 (GUI) 来配置软件Windows服务器环境中最有用。

> [!NOTE]
> 不应将 PowerShell cmdlet 用作完整网络策略管理基础结构的替代，例如[Microsoft Endpoint Configuration Manager](/configmgr)、[组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))或[Microsoft Defender 防病毒 组策略 ADMX 模板](https://www.microsoft.com/download/101445).

使用 PowerShell 所做的更改将影响部署或进行更改的终结点上的本地设置。 这意味着，使用组策略、Microsoft Endpoint Configuration Manager或Microsoft Intune部署策略可以覆盖使用 PowerShell 所做的更改。

可以 [使用本地策略重写来配置可在本地重写哪些设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

PowerShell 通常安装在文件夹 `%SystemRoot%\system32\WindowsPowerShell`下。

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>使用 Microsoft Defender 防病毒 PowerShell cmdlet

1. 在Windows搜索栏中，键入 **powershell**。
2. 从结果中选择 **Windows PowerShell** 以打开接口。
3. 输入 PowerShell 命令和任何参数。

> [!NOTE]
> 可能需要在管理员模式下打开 PowerShell。 右键单击"开始"菜单中的项，单击 **“以管理员身份运行”**，并在权限提示处单击 **“是**”。

若要为任何 cmdlet 打开联机帮助，请键入以下内容：

```PowerShell
Get-Help <cmdlet> -Online
```

省略 `-online` 参数以获取本地缓存的帮助。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-topics"></a>相关主题

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防病毒 Cmdlet](/powershell/module/defender)
