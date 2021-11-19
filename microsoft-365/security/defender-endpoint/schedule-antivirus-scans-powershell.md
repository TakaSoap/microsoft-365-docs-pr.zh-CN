---
title: 使用 PowerShell 安排防病毒扫描
description: 使用 PowerShell 安排防病毒扫描
keywords: 快速扫描， 完全扫描， 防病毒， 计划， PowerShell
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
ms.openlocfilehash: 03978feb5a9d0ca98d432fbec91e0fd5ce83724e
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111251"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>使用 PowerShell 安排防病毒扫描

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

本文介绍如何使用 PowerShell cmdlet 配置计划扫描。 若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell cmdlet 计划扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

有关详细信息，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender for Cloud cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>在终结点不使用时用于计划扫描的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

有关详细信息，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender for Cloud cmdlet。](/powershell/module/defender/)

> [!NOTE]
> 在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>用于计划扫描以完成修正的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

请参阅[使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender for Cloud cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>用于计划每日扫描的 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和 Defender [for Cloud cmdlet。](/powershell/module/defender/)
