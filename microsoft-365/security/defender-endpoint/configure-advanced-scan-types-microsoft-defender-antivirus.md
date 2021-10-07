---
title: 配置扫描选项以Microsoft Defender 防病毒
description: 你可以将 Microsoft Defender AV 配置为扫描电子邮件存储文件、备份或重新分析点、网络文件和存档文件 (如.zip文件) 。
keywords: 高级扫描， 扫描， 电子邮件， 存档， zip， rar， 存档， 重新分析扫描
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.date: 09/14/2021
ms.collection: M365-security-compliance
ms.topic: how-to
ms.openlocfilehash: 3ce0945fc687623c5f5fd7ba26e57ad191ec3ecb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207961"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>配置 Microsoft Defender 防病毒软件扫描选项

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>使用Microsoft Intune配置扫描选项

有关详细信息，[请参阅在](/intune/device-restrictions-configure)[Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)中Microsoft Intune配置Microsoft Defender 防病毒设备Windows 10设置。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>使用Microsoft Endpoint Manager配置扫描选项

有关配置当前分支Microsoft Endpoint Manager (的详细信息，) 如何创建[和部署反恶意软件策略：扫描设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。

## <a name="use-group-policy-to-configure-scanning-options"></a>使用组策略配置扫描选项

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象， **然后选择编辑**。

3. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。

4. 展开树以 **Windows** 组件Microsoft Defender 防病毒，然后选择一个位置 (请参阅本文中的设置 \> 和) 。 [](#settings-and-locations)

5. 编辑策略对象。

6. 单击 **"确定**"，然后对任何其他设置重复上述操作。

### <a name="settings-and-locations"></a>设置和位置

|策略项和位置|如果未配置 (默认设置) |类的 PowerShell `Set-MpPreference` 参数或 WMI `MSFT_MpPreference` 属性|
|---|---|---|
|电子邮件扫描 <p> **扫描** \>**打开电子邮件扫描**<p>请参阅 [本文中介绍](#email-scanning-limitations) (扫描限制) |Disabled|`-DisableEmailScanning`|
|扫描 [重新分析点](/windows/win32/fileio/reparse-points) <p> **扫描** \>**打开重新分析点扫描**|Disabled|不可用 <p>请参阅 [重新分析点](/windows/win32/fileio/reparse-points)|
|扫描映射的网络驱动器 <p> **扫描** \>**在映射的网络驱动器上运行完全扫描**|Disabled|`-DisableScanningMappedNetworkDrivesForFullScan`|
|扫描存档 (，例如.zip或.rar文件) 。 <p> **扫描** \>**扫描存档文件**|已启用|`-DisableArchiveScanning` <p>扩展 [名排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 将优先于此设置。|
|扫描网络文件 <p> **扫描** \>**扫描网络文件**|Disabled|`-DisableScanningNetworkFiles`|
|扫描打包的可执行文件 <p> **扫描** \>**扫描打包的可执行文件**|已启用|不适用|
|仅在完全扫描期间扫描可移动驱动器 <p> **扫描** \>**扫描可移动驱动器**|Disabled|`-DisableRemovableDriveScanning`|
|指定要扫描的存档文件夹中的子文件夹级别 <p>**扫描** \>**指定扫描存档文件的最大深度**|0|不可用|
|指定最大 CPU 负载 (以扫描期间) 百分比表示。 <p> **扫描** \>**指定扫描期间 CPU 使用率的最大百分比**|50|`-ScanAvgCPULoadFactor` <p>**注意**：最大 CPU 负载不是硬性限制，但指导扫描引擎平均不超过最大值。 手动运行扫描将忽略此设置，并且运行时没有任何 CPU 限制。|
|指定应 (存档) 的最大大小（以 KB 为单位）。 <p> **扫描** \>**指定要扫描的存档文件的最大大小**|无限制|不适用 <p>默认值 0 没有限制|
|为计划扫描配置低 CPU 优先级 <p> **扫描** \>**为计划扫描配置低 CPU 优先级**|Disabled|不适用|

> [!NOTE]
> 如果启用实时保护，则先扫描文件，然后再访问和执行文件。 扫描范围包括所有文件，包括装载的可移动媒体（如 USB 驱动器）上的文件。 如果执行扫描的设备已打开实时保护或访问保护，则扫描还将包括网络共享。

## <a name="use-powershell-to-configure-scanning-options"></a>使用 PowerShell 配置扫描选项

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一起使用，请参阅

- [使用 PowerShell cmdlet Microsoft Defender 防病毒管理服务](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender cmdlet](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>使用 WMI 配置扫描选项

请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="email-scanning-limitations"></a>电子邮件扫描限制

电子邮件扫描支持在按需扫描和计划Outlook客户端使用的电子邮件文件扫描。 还会扫描电子邮件 (嵌入对象，如附件) 存档文件。 可以扫描和修正以下文件格式类型：

- DBX
- MBX
- MIME

Outlook 2003 或 (（其中存档类型设置为非 unicode) ）使用的 PST 文件也会被扫描，但 Microsoft Defender 防病毒 无法修正在 PST 文件内检测到的威胁。

如果你Microsoft Defender 防病毒电子邮件内检测到威胁，它将显示以下信息来帮助你识别遭到入侵的电子邮件，以便你可以手动修正威胁：

- 电子邮件主题
- 附件名称

## <a name="scanning-mapped-network-drives"></a>扫描映射的网络驱动器

在任何操作系统上，仅扫描在系统级别映射的网络驱动器。 不扫描用户级别映射的网络驱动器。 用户级别的映射网络驱动器是用户在会话中手动使用自己的凭据映射的驱动器。

## <a name="see-also"></a>另请参阅

- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
- [配置计划Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
