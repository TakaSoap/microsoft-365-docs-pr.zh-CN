---
title: 使用 Management Instrumentation 计划Windows扫描
description: 使用 WMI 计划防病毒扫描
keywords: 快速扫描， 完全扫描， WMI， 计划， 防病毒
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
ms.openlocfilehash: be22e59f6d2be30ead354099f2cc168868959752
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61160278"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>使用 Windows Management Instrumentation (WMI) 安排防病毒扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

本文介绍如何使用 WMI 配置计划扫描。 若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows Management Instruction (WMI) 计划扫描

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>不使用终结点时用于计划扫描的 WMI

对 [下列属性使用 MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类的 Set 方法：

```WMI
ScanOnlyIfIdleEnabled
```

有关 API 和允许的参数详细信息，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!NOTE]
> 在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>用于计划扫描以完成修正的 WMI

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-daily-scans"></a>用于计划每日扫描的 WMI

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanScheduleQuickScanTime
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

