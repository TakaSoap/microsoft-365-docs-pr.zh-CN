---
title: 计划Microsoft Defender 防病毒保护更新
description: 计划应下载保护更新的天数、时间和间隔
keywords: 更新、安全基线、计划更新
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: cca49b5bdcfae0f7c0ed910b6d0df9ec0448aff5
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789395"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>管理应下载和应用保护更新的时间日程安排

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒可让你确定何时应查找和下载更新。

可以通过以下方法计划终结点的更新：

- 指定要检查保护更新的一周中的日期
- 指定检查保护更新的时间间隔
- 指定检查保护更新的时间

还可以随机设置每个终结点检查和下载保护更新的时间。 有关详细信息，请参阅 [“计划扫描”](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主题。

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>使用Configuration Manager计划保护更新

1. 在Microsoft Endpoint Manager控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的 **“资产和符合性**”，然后将树展开为“**反恶意软件** 策略 **概述** \> **Endpoint Protection**\>) 

2. 转到 **“安全智能更新** ”部分。

3. 若要在特定时间检查和下载更新，请执行以下操作：
      1. 将 **特定时间间隔Endpoint Protection安全智能更新的检查设置** 为 **0**。
      2. 将 **每天Endpoint Protection安全智能更新的检查设置为** 应检查更新的时间。
      3
4. 若要按持续的时间间隔检查和下载更新，请将 **检查Endpoint Protection安全智能更新设置为特定间隔...**

5. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="use-group-policy-to-schedule-protection-updates"></a>使用组策略计划保护更新

> [!IMPORTANT]
> 默认情况下，“SignatureScheduleDay”设置为“8”，“SignatureUpdateInterval”设置为“0”，因此Microsoft Defender 防病毒不会计划保护更新。
启用这些设置将替代该默认设置。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒** \> **签名智能更新** 并配置以下设置：

    1. 双击“ **指定星期几”以检查安全智能更新** 设置，并将选项设置为 **“已启用**”。 输入一周中的一天来检查更新。 单击“确定”。
    2. 双击“ **指定时间间隔”以检查安全智能更新** 设置，并将选项设置为 **“已启用**”。 输入更新之间的小时数。 单击“确定”。
    3. 双击“ **指定检查安全智能更新设置的时间** ”，并将选项设置为 **“已启用**”。 输入应检查更新的时间。 时间基于终结点的本地时间。 单击“确定”。

## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>使用 PowerShell cmdlet 计划保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>使用Windows管理指令 (WMI) 来计划保护更新

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-articles"></a>相关文章

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
