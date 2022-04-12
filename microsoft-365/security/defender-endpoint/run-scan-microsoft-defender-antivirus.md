---
title: 在Microsoft Defender 防病毒中运行和自定义按需扫描
description: 使用 PowerShell、Windows Management Instrumentation 或使用Windows 安全中心应用在终结点上单独运行和配置按需扫描
keywords: 扫描，按需，dos，intune，即时扫描
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/22/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: bca0e953b759f447e8274e8766cbcada273eb614
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788867"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>配置并运行按需 Microsoft Defender 防病毒软件扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以对单个终结点运行按需扫描。 这些扫描将立即开始，你可以定义扫描的参数，例如位置或类型。 运行扫描时，可以选择三种类型：快速扫描、完全扫描和自定义扫描。 在大多数情况下，请使用快速扫描。 快速扫描会查看注册恶意软件以从系统开始的所有位置，例如注册表项和已知Windows启动文件夹。

结合始终打开的实时保护（在打开和关闭文件时对文件进行评审;每当用户导航到文件夹时，快速扫描可帮助提供对以系统和内核级恶意软件开头的恶意软件的有力保护。 在大多数情况下，快速扫描已足够，是计划扫描或按需扫描的建议选项。 [详细了解扫描类型](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。

> [!IMPORTANT]
> 执行本地扫描时，Microsoft Defender 防病毒在 [LocalSystem](/windows/win32/services/localsystem-account) 帐户的上下文中运行。 对于网络扫描，它使用设备帐户的上下文。 如果域设备帐户没有访问共享的适当权限，则扫描将不起作用。 确保设备具有访问网络共享的权限。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>使用Microsoft Endpoint Manager运行扫描

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 在选项卡列表中，选择 **Windows 10不正常的终结点** 或 **Windows 11不正常的终结点**。

4. 从提供的操作列表中，选择 **“快速扫描** ” (建议的) 或 **“完全扫描**”。

   [![“Windows 10不正常的终结点”选项卡上的扫描选项。](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> 有关使用Microsoft Endpoint Manager运行扫描的详细信息，请参阅[反恶意软件和防火墙任务：如何执行按需扫描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>使用mpcmdrun.exe命令行实用工具运行扫描

使用以下 `-scan` 参数：

```console
mpcmdrun.exe -scan -scantype 1
```

有关如何使用该工具和其他参数的详细信息，包括启动完整扫描或定义路径，请参阅[使用mpcmdrun.exe命令行工具来配置和管理Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)。

## <a name="use-microsoft-intune-to-run-a-scan"></a>使用Microsoft Intune运行扫描

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 在边栏中，选择 **“****设备所有设备**\>”，然后选择要扫描的设备。

3. 选择 **...更多**。 在选项中，选择 **“快速扫描** (建议的) 或 **完全扫描**。

## <a name="use-the-windows-security-app-to-run-a-scan"></a>使用Windows 安全中心应用运行扫描

有关在各个终结点上运行扫描的说明，请参阅[Windows 安全中心应用中运行扫描](microsoft-defender-security-center-antivirus.md)。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>使用 PowerShell cmdlet 运行扫描

使用以下 cmdlet：

```PowerShell
Start-MpScan
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>使用 Windows 管理指令 (WMI) 运行扫描

使用 **MSFT_MpScan** 类的 [**Start** 方法](/previous-versions/windows/desktop/defender/start-msft-mpscan)。

有关允许哪些参数的详细信息，请[参阅 Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)