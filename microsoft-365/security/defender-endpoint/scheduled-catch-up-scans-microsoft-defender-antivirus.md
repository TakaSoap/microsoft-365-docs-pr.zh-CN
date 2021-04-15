---
title: 使用 Microsoft Defender 防病毒计划定期快速和完整扫描
description: 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 常规
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bfa616423fc0c097b9909df8abf5b9c414490383
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764083"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 默认情况下，Microsoft Defender 防病毒会在任何计划扫描前 15 分钟检查更新。 你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。 

除了始终打开实时保护和按需扫描之外，还可以设置[](run-scan-microsoft-defender-antivirus.md)定期计划扫描。 

可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后发生还是使用终结点。 [](manage-protection-updates-microsoft-defender-antivirus.md) 还可以指定应何时进行特殊扫描以完成修正。

本文介绍如何使用组策略、PowerShell cmdlet 和 WMI 配置计划扫描。 还可使用 Microsoft Endpoint [Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) 或 [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10)配置计划扫描。

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>配置本文中所述的组策略设置

1.  在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

3.  在组 **策略管理编辑器中** ，转到计算机 **配置**。

4.  单击 **"管理模板"。**

5.  将树展开到 **Microsoft Defender > Windows** 组件，然后展开下表中指定的位置。 

6. 双击 **下表中指定的** 策略设置，将选项设置为所需的配置。 

7. 单击 **"确定**"，然后对任何其他设置重复上述操作。

另请参阅 [管理何时应下载](manage-protection-update-schedule-microsoft-defender-antivirus.md) 和应用保护更新和阻止或允许用户 [在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>快速扫描与完全扫描和自定义扫描

设置计划扫描时，可以设置扫描应为完全扫描还是快速扫描。

快速扫描会查看所有可能注册了恶意软件以从系统启动的位置，例如注册表项和已知的 Windows 启动文件夹。 

与 [始终启用](configure-real-time-protection-microsoft-defender-antivirus.md) 实时保护功能（在打开和关闭文件时以及用户导航到文件夹时查看文件）相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。  

在大多数情况下，这意味着快速扫描足以找到未通过实时保护选取的恶意软件。

完全扫描在遇到恶意软件威胁的终结点上非常有用，可用于标识是否有需要更彻底清理的非活动组件。 在这种情况下，你可能想要在运行按需扫描时使用 [完全扫描](run-scan-microsoft-defender-antivirus.md)。

自定义扫描允许你指定要扫描的文件和文件夹，例如 USB 驱动器。 

>[!NOTE]
>默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。

## <a name="set-up-scheduled-scans"></a>设置计划扫描

计划的扫描将在你指定的日期和时间运行。 可以使用组策略、PowerShell 和 WMI 配置计划扫描。

>[!NOTE]
>如果在计划的完整扫描期间计算机已拔下并按电池运行，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。 Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。

### <a name="use-group-policy-to-schedule-scans"></a>使用组策略计划扫描

|位置 | 设置 | 说明 | 如果未 (默认设置)  |
|:---|:---|:---|:---|
|扫描 | 指定用于计划扫描的扫描类型 | 快速扫描 |
|扫描 | 指定一周中的哪些天运行计划扫描 | 指定运行 () 或从不运行扫描的日。 | 从不 |
|扫描 | 指定运行计划扫描的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示上午 1 点) 。 | 2 a.m. |
|根 | 随机化计划任务时间 |在 Microsoft Defender 防病毒中：将扫描的开始时间随机化为 0 到 4 小时之间的任意间隔。 <br>在 FEP/SCEP 中：随机化为任意间隔加减 30 分钟。 这可在 VM 或 VDI 部署中非常有用。 | 已启用 |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell cmdlet 计划扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows Management Instruction (WMI) 计划扫描

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

有关详细信息和允许的参数，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>仅在终结点不使用时启动计划扫描

可以将计划扫描设置为仅在终结点打开时发生，但不与组策略、PowerShell 或 WMI 一同使用。

> [!NOTE]
> 这些扫描不会接受 CPU 限制配置，并充分利用可用资源尽快完成扫描。

### <a name="use-group-policy-to-schedule-scans"></a>使用组策略计划扫描

|位置 | 设置 | 说明 | 如果未 (默认设置)  |
|:---|:---|:---|:---|
|扫描 | 仅在计算机打开但没有使用时启动计划扫描 | 计划的扫描将不会运行，除非计算机已打开但没有使用 | 已启用 |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management Instruction (WMI) 

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanOnlyIfIdleEnabled
```

有关详细信息和允许的参数，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>配置应何时运行完全扫描以完成修正

某些威胁可能需要完全扫描才能完成删除和修正。 可以使用组策略、PowerShell 或 WMI 计划这些扫描应发生的时间。

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>使用组策略计划修正所需的扫描

| 位置 | 设置 | 说明 | 如果未 (默认设置)  |
|---|---|---|---|
|修正 | 指定一周中的哪些天运行计划的完全扫描以完成修正 | 指定运行 () 或从不运行扫描的日。 | 从不 |
|修正 | 指定一天中运行计划完整扫描以完成修正的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management Instruction (WMI) 

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

有关详细信息和允许的参数，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>设置每日快速扫描

除了使用组策略、PowerShell 或 WMI 进行其他计划扫描外，还可以启用每日快速扫描。


### <a name="use-group-policy-to-schedule-daily-scans"></a>使用组策略计划每日扫描


|位置 | 设置 | 说明 | 如果未 (默认设置)  |
|:---|:---|:---|:---|
|扫描 | 指定每天运行快速扫描的间隔 | 指定下一次快速扫描之前应经过的小时数。 例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。 输入 **0** 从不运行每日快速扫描。 | 从不 |
|扫描 | 指定每日快速扫描的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>使用 PowerShell cmdlet 计划每日扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>使用 Windows Management Instruction (WMI) 安排每日扫描

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanScheduleQuickScanTime
```

有关详细信息和允许的参数，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>在保护更新后启用扫描

可以使用组策略强制每次保护 [更新后](manage-protection-updates-microsoft-defender-antivirus.md) 执行扫描。

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>使用组策略计划保护更新后的扫描

|位置 | 设置 | 说明 | 如果未 (默认设置) |
|:---|:---|:---|:---|
|签名更新 | 在安全智能更新后打开扫描 | 扫描将在下载新保护更新后立即发生 | 已启用 |

## <a name="see-also"></a>另请参阅
- [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
- [配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)