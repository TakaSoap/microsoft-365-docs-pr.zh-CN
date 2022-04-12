---
title: 使用Windows管理检测计划防病毒扫描
description: 使用 WMI 计划防病毒扫描
keywords: 快速扫描，完全扫描，WMI，计划，防病毒
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
ms.openlocfilehash: 2b25876a43dea3b1598d4bdfa89cf4724c0fca14
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788911"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>使用 Windows Management Instrumentation (WMI) 安排防病毒扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

本文介绍如何使用 WMI 配置计划扫描。 若要详细了解计划扫描和扫描类型，请参阅[配置计划的快速或完整Microsoft Defender 防病毒扫描](schedule-antivirus-scans.md)。 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows 管理指令 (WMI) 来计划扫描

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

有关详细信息和允许的参数，请[参阅 Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>未使用终结点时计划扫描的 WMI

对以下属性使用 [MSFT_MpPreference 类的 Set 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
ScanOnlyIfIdleEnabled
```

有关 API 和允许的参数的详细信息，请[参阅 Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

> [!NOTE]
> 在计划扫描终结点未使用的时间时，扫描不遵循 CPU 限制配置，并且会充分利用可用的资源，以尽可能快地完成扫描。


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>用于计划扫描以完成修正的 WMI

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

有关详细信息和允许的参数，请[参阅Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="wmi-for-scheduling-daily-scans"></a>用于计划每日扫描的 WMI

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
ScanScheduleQuickScanTime
```

有关详细信息和允许的参数，请[参阅Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)