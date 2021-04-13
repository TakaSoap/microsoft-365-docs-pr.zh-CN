---
title: 配置 Microsoft Defender AV 的扫描选项
description: 你可以将 Microsoft Defender AV 配置为扫描电子邮件存储文件、备份或重新分析点、网络文件和存档文件 (.zip 文件) 。
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
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689951"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>配置 Microsoft Defender 防病毒扫描选项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>使用 Microsoft Intune 配置扫描选项

有关详细信息 [，请参阅在 Microsoft Intune 中](/intune/device-restrictions-configure) 配置设备限制设置和 Intune 中 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 的 Microsoft Defender 防病毒设备限制设置。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>使用 Microsoft Endpoint Manager 配置扫描选项

请参阅 [如何创建和部署反恶意软件](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) 策略：扫描设置，了解有关配置 Microsoft Endpoint Manager (当前分支) 。

## <a name="use-group-policy-to-configure-scanning-options"></a>使用组策略配置扫描选项

配置下表中所述的组策略设置：

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。

3. 将树展开到 **Microsoft Defender > Windows** 组件，然后展开下表中指定的位置。 

4. 双击 **下表中指定的** 策略设置，将选项设置为所需的配置。 单击 **"确定**"，然后对任何其他设置重复上述操作。

说明 | 位置和设置 | 如果未 (默认设置)  | 类的 PowerShell `Set-MpPreference` 参数或 WMI `MSFT_MpPreference` 属性
---|---|---|---
电子邮件扫描 请参阅 [电子邮件扫描限制](#ref1)| 扫描>打开电子邮件扫描 | 已禁用 | `-DisableEmailScanning`
扫描 [重新分析点](/windows/win32/fileio/reparse-points) | 扫描>打开重新分析点扫描 | 已禁用 | 不可用
扫描映射的网络驱动器 | 扫描>映射的网络驱动器上运行完全扫描 | 已禁用 | `-DisableScanningMappedNetworkDrivesForFullScan`
 扫描存档文件 (.zip 或 .rar 文件) 。 扩展 [名排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 将优先于此设置。 | 扫描>扫描存档文件 | 已启用 | `-DisableArchiveScanning`
扫描网络文件 | 扫描>扫描网络文件 | 已禁用 | `-DisableScanningNetworkFiles`
扫描打包的可执行文件 | 扫描>扫描打包的可执行文件 | 已启用 | 不可用
仅在完全扫描期间扫描可移动驱动器 | 扫描>扫描可移动驱动器 | 已禁用 | `-DisableRemovableDriveScanning`
指定要扫描的存档文件夹中的子文件夹级别 | 扫描>指定扫描存档文件的最大深度 | 0 | 不可用
 指定最大 CPU 负载 (以扫描) 的百分比表示。 注意：这不是硬性限制，而是指导扫描引擎平均不超过此最大值。 | 扫描>指定扫描期间 CPU 使用率的最大百分比 | 50 |  `-ScanAvgCPULoadFactor`
 指定应 (存档) 的最大大小（以 KB 为单位）。 默认值 **0** 没有限制 | 扫描>指定要扫描的存档文件的最大大小 | 无限制 | 不可用
 为计划扫描配置低 CPU 优先级 | 扫描>配置计划扫描的低 CPU 优先级 | 已禁用 | 不可用
 
> [!NOTE]
> 如果启用实时保护，则先扫描文件，然后再访问和执行文件。 扫描范围包括所有文件，包括装载的可移动媒体（如 USB 驱动器）上的文件。 如果执行扫描的设备已打开实时保护或访问保护，则扫描还将包括网络共享。

## <a name="use-powershell-to-configure-scanning-options"></a>使用 PowerShell 配置扫描选项

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 Defender [cmdlet](/powershell/module/defender/) 管理 Microsoft Defender 防病毒，详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

## <a name="use-wmi-to-configure-scanning-options"></a>使用 WMI 配置扫描选项

有关使用 WMI 类，请参阅[Windows Defender WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>电子邮件扫描限制

电子邮件扫描支持在按需扫描和计划扫描期间扫描 Outlook 和其他邮件客户端使用的电子邮件文件。 电子邮件文件中嵌入的对象 (附件和存档文件) 扫描。 可以扫描和修正以下文件格式类型：

- DBX
- MBX
- MIME

Outlook 2003 或较旧版本使用的 PST 文件 (其中存档类型设置为非 unicode) 也将进行扫描，但 Windows Defender 无法修正在 PST 文件内检测到的威胁。

如果 Microsoft Defender 防病毒检测到电子邮件内的威胁，它将显示以下信息来帮助你识别遭到入侵的电子邮件，以便你可以手动修正威胁：

- 电子邮件主题
- 附件名称

## <a name="related-topics"></a>相关主题

- [自定义、启动和查看 Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒扫描](run-scan-microsoft-defender-antivirus.md)
- [配置计划的 Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)