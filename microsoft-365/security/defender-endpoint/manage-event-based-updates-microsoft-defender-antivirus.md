---
title: 在某些事件之后应用Microsoft Defender 防病毒更新
description: 管理Microsoft Defender 防病毒如何在启动或接收云传送的检测报告后应用安全智能更新。
keywords: 更新， 保护， 强制更新， 事件， 启动， 检查最新， 通知
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 8ad9a5c6cd1a79152640bb153f8a130ecdd29362
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789483"
---
# <a name="manage-event-based-forced-updates"></a>管理基于事件的强制更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒允许你确定更新是否应 (或不应在某些事件（例如启动时或从云传送的保护服务接收特定报告）后) 发生。

## <a name="check-for-protection-updates-before-running-a-scan"></a>运行扫描前检查保护更新

可以使用Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 和 WMI 强制Microsoft Defender 防病毒在运行计划扫描之前检查和下载保护更新。

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>在运行扫描之前，使用Configuration Manager检查保护更新

1. 在Microsoft Endpoint Manager控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的 **“资产和符合性**”，然后将树展开为“**反恶意软件** 策略 **概述** \> **Endpoint Protection**\>) 

2. 在将扫描运行到 **“是**”之前，请转到 **“计划扫描**”部分，并设置“**检查最新安全智能更新**”。

3. 单击“确定”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>使用组策略在运行扫描之前检查保护更新

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 将树展开到 **扫描** Microsoft Defender 防病毒 **Windows** \> **组件**\>。

5. 在运行计划扫描并将选项设置为 **“已启用**”之前，双击 **“检查最新的病毒和间谍软件定义**”。

6. 单击“确定”。

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>在运行扫描之前，使用 PowerShell cmdlet 检查保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

有关详细信息，请参阅[使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md)和 [Defender for Cloud cmdlet](/powershell/module/defender/index)。

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>使用Windows管理指令 (WMI) 在运行扫描之前检查保护更新

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
CheckForSignaturesBeforeRunningScan
```

有关详细信息，请参阅[Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="check-for-protection-updates-on-startup"></a>在启动时检查保护更新

可以使用组策略强制Microsoft Defender 防病毒在启动计算机时检查和下载保护更新。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 将树展开到安全 **智能更新****Microsoft Defender 防病毒Windows** \> **组件**\>。

5. 双击 **“在启动时检查最新的病毒和间谍软件定义** ”，并将选项设置为 **“已启用**”。

6. 单击“确定”。

还可以使用 组策略、PowerShell 或 WMI 配置Microsoft Defender 防病毒，以便在启动时检查更新（即使未运行）。

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>在不存在Microsoft Defender 防病毒时使用组策略下载更新

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器**，转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 将树展开到安全 **智能更新****Microsoft Defender 防病毒Windows** \> **组件**\>。

5. 双击 **启动时启动安全智能更新** ，并将选项设置为 **“已启用**”。

6. 单击“确定”。

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>如果不存在Microsoft Defender 防病毒，请使用 PowerShell cmdlet 下载更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

有关详细信息，请参阅[使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/index)，详细了解如何将 PowerShell 与Microsoft Defender 防病毒配合使用。

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>在不存在Microsoft Defender 防病毒时，使用 Windows 管理指令 (WMI) 下载更新

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

有关详细信息，请参阅[Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>允许基于云提供的保护对保护进行临时更改

Microsoft Defender AV 可以基于云提供的保护对其保护进行更改。 此类更改可能发生在正常或计划的保护更新之外。

如果已启用云传递的保护，Microsoft Defender AV 会将可疑的文件发送到Windows Defender云。 如果云服务报告该文件是恶意文件，并且在最近的保护更新中检测到该文件，则可以使用组策略将 Microsoft Defender AV 配置为自动接收该保护更新。 还可以应用其他重要的保护更新。

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>使用组策略基于云提供的保护自动下载最近的更新

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 将树展开到安全 **智能更新****Microsoft Defender 防病毒Windows** \> **组件**\>。

5. 双击 **“允许基于 Microsoft MAPS 报告的实时安全智能更新** ”，并将选项设置为 **“已启用**”。 单击" **确定**"。

6. **允许通知将基于定义的报表禁用到 Microsoft MAPS** ，并将选项设置为 **“已启用**”。 单击" **确定**"。

> [!NOTE]
> **允许通知禁用基于定义的报表** ，Microsoft MAPS 可以禁用已知会导致误报的定义。 必须将计算机配置为加入 Microsoft MAPS 才能使此函数正常工作。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
