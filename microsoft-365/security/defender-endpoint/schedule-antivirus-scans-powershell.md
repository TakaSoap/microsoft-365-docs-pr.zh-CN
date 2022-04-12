---
title: 使用 PowerShell 安排防病毒扫描
description: 使用 PowerShell 安排防病毒扫描
keywords: 快速扫描，完全扫描，防病毒，计划，PowerShell
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 8961428acee5d166b0cdad4982aa5f9ed48020af
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788823"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>使用 PowerShell 安排防病毒扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

本文介绍如何使用 PowerShell cmdlet 配置计划扫描。 若要详细了解计划扫描和扫描类型，请参阅[配置计划的快速或完整Microsoft Defender 防病毒扫描](schedule-antivirus-scans.md)。 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell cmdlet 计划扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

有关详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)，详细了解如何将 PowerShell 用于Microsoft Defender 防病毒。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>当终结点未使用时用于计划扫描的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/)。

> [!NOTE]
> 在计划扫描终结点未使用的时间时，扫描不遵循 CPU 限制配置，并且会充分利用可用的资源，以尽可能快地完成扫描。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>用于计划扫描以完成修正的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>用于计划每日扫描的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)