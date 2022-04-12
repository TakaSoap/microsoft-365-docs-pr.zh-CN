---
title: 为 Microsoft Defender 防病毒检测配置修正
description: 配置Microsoft Defender 防病毒检测到威胁时应执行的操作，以及隔离文件应保留在隔离文件夹中的时间
keywords: 修正， 修复， 删除， 威胁， 隔离， 扫描， 还原
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 257a3bfc4fc9dcb6353bb158bc3cd4296891ae76
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790143"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>为 Microsoft Defender 防病毒检测配置修正


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒运行扫描时，它会尝试修正或删除检测到的威胁。 可以配置Microsoft Defender 防病毒应如何应对某些威胁、是否应在修正之前创建还原点，以及何时应删除威胁。

本文介绍如何使用组策略配置这些设置，但也可以使用[Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)和[Microsoft Intune](/intune/device-restrictions-configure)。

还可以使用 [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) 或 [`MSFT_MpPreference` WMI 类](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 来配置这些设置。

## <a name="configure-remediation-options"></a>配置修正选项

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 转到 **计算机配置** 并选择 **管理模板**。

3. 将树展开为 **Windows组件** \> **Microsoft Defender 防病毒**。

4. 使用下表，选择一个位置，然后根据需要编辑策略。

5. 选择“确定”。

<br/><br/>

|位置|设置|说明|默认设置 (（如果未配置）) |
|---|---|---|---|
|扫描|创建系统还原点|在尝试清理或扫描之前，每天将创建一个系统还原点|Disabled|
|扫描|打开从扫描历史记录文件夹中删除项|指定应在扫描历史记录中保留多少天项|30 天|
|根|关闭常规修正|可以指定Microsoft Defender 防病毒是否自动修正威胁，或者是否应询问终结点用户该怎么做。|禁用 (威胁会自动修正) |
|隔离|配置从隔离文件夹中删除项|指定在删除项目之前应在隔离区中保留多少天|90 天|
|威胁|指定检测到时不应执行默认操作的威胁警报级别|Microsoft Defender 防病毒检测到的每个威胁都分配为低、中、高或严重)  (威胁级别。 可以使用此设置来定义如何修正每个威胁级别的所有威胁 (隔离、删除或忽略) |不适用|
|威胁|指定检测到时不应对其执行默认操作的威胁|指定应如何修正使用其威胁 ID 的特定威胁 () 。 可以指定是否应隔离、删除或忽略特定威胁|不适用|

> [!IMPORTANT]
> Microsoft Defender 防病毒根据许多因素检测和修正文件。 有时，完成修正需要重新启动。 即使检测后来确定为误报，也必须完成重新启动，以确保已完成所有额外的修正步骤。
>
> 如果确定Microsoft Defender 防病毒基于误报隔离文件，则可以在设备重新启动后从隔离区还原文件。 请参阅[Microsoft Defender 防病毒中的还原隔离文件](restore-quarantined-files-microsoft-defender-antivirus.md)。
>
> 为了避免将来出现此问题，可以从扫描中排除文件。 请参阅[配置和验证Microsoft Defender 防病毒扫描的排除项](configure-exclusions-microsoft-defender-antivirus.md)。

另请参阅[配置所需修正计划的完整Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)，以获取更多与修正相关的设置。

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

- [配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [配置计划的Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
- [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
- [配置最终用户Microsoft Defender 防病毒交互](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
