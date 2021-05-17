---
title: 使用扫描计划定期快速和完全Microsoft Defender 防病毒
description: 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 常规
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274684"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 默认情况下，Microsoft Defender 防病毒扫描前 15 分钟检查更新。 你可以 [管理何时应](manage-protection-update-schedule-microsoft-defender-antivirus.md) 下载和应用保护更新以覆盖此默认值的计划。 

除了始终打开实时保护和按需扫描之外，还可以设置[](run-scan-microsoft-defender-antivirus.md)定期计划扫描。 

可以配置扫描类型、应何时进行扫描，以及扫描应在保护更新后发生还是使用终结点。 [](manage-protection-updates-microsoft-defender-antivirus.md) 还可以指定应何时进行特殊扫描以完成修正。

本文介绍如何使用组策略、PowerShell cmdlet 和 WMI 配置计划扫描。 还可以配置计划[扫描，Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)[或](/mem/intune/configuration/device-restrictions-windows-10)Microsoft Intune。

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>配置本文中所述的组策略设置

1. 在组策略管理计算机上，在组策略编辑器中，转到计算机配置管理模板 Windows 组件 Microsoft Defender 防病毒  >    >    >    >  **扫描**。

2. 右键单击要配置的组策略对象， **然后选择编辑**。

3. 指定组策略对象的设置，**然后选择确定。** 

4. 对要配置的每个设置重复步骤 1-4。

5. 像平常一样部署组策略对象。 如果需要有关组策略对象的帮助，请参阅 [创建组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

另请参阅 [管理何时应下载](manage-protection-update-schedule-microsoft-defender-antivirus.md) 和应用保护更新和阻止或允许用户 [在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>快速扫描与完全扫描和自定义扫描

设置计划扫描时，可以设置扫描应为完全扫描还是快速扫描。


|快速扫描  |完全扫描  | 自定义扫描 |
|---------|---------|---------|
|快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。 <p>在大多数情况下，快速扫描已足够，建议用于计划扫描。 |完整扫描首先运行快速扫描，然后继续针对所有已装载的固定磁盘和可移动/网络驱动器进行连续文件扫描 (如果完全扫描配置为) 。 <p>完整扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据的数量和类型。<p>完成完整扫描后，新的安全智能可用，并且需要新扫描以确保新安全智能不会检测到任何其他威胁。   | 自定义扫描是在指定的文件和文件夹上运行的快速扫描。 例如，你可以选择扫描 USB 驱动器或设备本地驱动器上的特定文件夹。 <p> | 

>[!NOTE]
>默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。

### <a name="how-do-i-know-which-scan-type-to-choose"></a>我如何知道要选择哪个扫描类型？

使用下表选择扫描类型。


|应用场景  |推荐的扫描类型  |
|---------|---------|
|想要设置定期计划扫描     | 快速扫描 <p>快速扫描检查设备上的过程、内存、配置文件和特定位置。 与 [始终开启的](configure-real-time-protection-microsoft-defender-antivirus.md)实时保护相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。 实时保护在打开和关闭文件时以及用户导航到文件夹时检查文件。         |
|在设备上检测到恶意软件等威胁     | 完全扫描 <p>完全扫描可帮助确定是否有需要更彻底清理的非活动组件。         |
|想要运行 [按需扫描](run-scan-microsoft-defender-antivirus.md)     | 完全扫描  <p>完全扫描将查看设备磁盘上的所有文件，包括已过时、已存档且每日未访问的文件。      |
| 你想要确保便携式设备（如 USB 驱动器）不包含恶意软件 | 自定义扫描 <p>通过自定义扫描，可以选择特定位置、文件夹或文件，并运行快速扫描。 |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>关于快速和完整扫描，我还需要了解哪些信息？

- 恶意文件可以存储在快速扫描中未包含的位置。 但是，始终启用实时保护会检查所有打开和关闭的文件，以及用户访问的文件夹中的任何文件。 实时保护和快速扫描相结合有助于提供强大的恶意软件防护。

- 具有云保护的 [On-access Protection](cloud-protection-microsoft-defender-antivirus.md) 有助于确保使用最新的安全智能和云机器学习模型扫描系统上访问的所有文件。

- 当实时保护检测到恶意软件并且最初未确定受影响文件的范围时，Microsoft Defender 防病毒在修正过程中启动完全扫描。

- 完全扫描可以检测其他扫描未检测到的恶意文件，例如快速扫描。 但是，完整扫描可能需要一段时间，并使用有价值的系统资源来完成。

- 如果设备长时间处于脱机状态，则完整扫描可能需要更长时间才能完成。 

## <a name="set-up-scheduled-scans"></a>设置计划扫描

计划的扫描将在你指定的日期和时间运行。 可以使用组策略、PowerShell 和 WMI 配置计划扫描。

> [!NOTE]
> 如果在计划的完全扫描期间设备已拔下并运行在电池上，计划的扫描将在事件 1002 中停止，该事件指出扫描在完成之前已停止。 Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。

### <a name="use-group-policy-to-schedule-scans"></a>使用组策略计划扫描

|位置 | 设置 | 说明 | 如果未 (默认设置)  |
|:---|:---|:---|:---|
|扫描 | 指定用于计划扫描的扫描类型 | 快速扫描 |
|扫描 | 指定一周中的哪些天运行计划扫描 | 指定运行 () 或从不运行扫描的日。 | 永不 |
|扫描 | 指定运行计划扫描的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示上午 1 点) 。 | 2 a.m. |
|根 | 随机化计划任务时间 |在Microsoft Defender 防病毒中，将扫描的开始时间随机化为 0 到 4 小时之间的任意间隔。 <p>在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，将扫描随机化为任意间隔加减 30 分钟。 这可在虚拟机或 VDI 部署中非常有用。 | 已启用 |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>使用 PowerShell cmdlet 计划扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

有关详细信息，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>使用 Windows Management Instruction (WMI) 计划扫描

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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

有关详细信息，请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management Instruction (WMI) 

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanOnlyIfIdleEnabled
```

有关 API 和允许的参数详细信息，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>配置应何时运行完全扫描以完成修正

某些威胁可能需要完全扫描才能完成删除和修正。 可以使用组策略、PowerShell 或 WMI 指定何时应进行这些扫描。

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>使用组策略计划修正所需的扫描

| 位置 | 设置 | 说明 | 如果未 (默认设置)  |
|---|---|---|---|
|修正 | 指定一周中的哪些天运行计划的完全扫描以完成修正 | 指定运行 () 或从不运行扫描的日。 | 永不 |
|修正 | 指定一天中运行计划完整扫描以完成修正的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

### <a name="use-powershell-cmdlets"></a>使用 PowerShell cmdlet

使用以下 cmdlet：

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。

### <a name="use-windows-management-instruction-wmi"></a>使用 Windows Management Instruction (WMI) 

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-up-daily-quick-scans"></a>设置每日快速扫描

除了使用组策略、PowerShell 或 WMI 进行其他计划扫描外，还可以启用每日快速扫描。

### <a name="use-group-policy-to-schedule-daily-scans"></a>使用组策略计划每日扫描

|位置 | 设置 | 说明 | 如果未 (默认设置)  |
|:---|:---|:---|:---|
|扫描 | 指定每天运行快速扫描的间隔 | 指定下一次快速扫描之前应经过的小时数。 例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。 输入 **0** 从不运行每日快速扫描。 | 永不 |
|扫描 | 指定每日快速扫描的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>使用 PowerShell cmdlet 计划每日扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和 Defender [cmdlet。](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>使用 Windows Management Instruction (WMI) 安排每日扫描

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
ScanScheduleQuickScanTime
```

有关详细信息和允许的参数，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


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
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)