---
title: 为Microsoft Defender 防病毒配置扫描选项
description: 可以将 Microsoft Defender AV 配置为扫描电子邮件存储文件、备份或重新分析点、网络文件和存档文件 (，例如.zip文件) 。
keywords: 高级扫描，扫描，电子邮件，存档，zip，rar，存档，重新分析扫描
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
ms.date: 12/03/2021
ms.collection: M365-security-compliance
ms.topic: how-to
ms.openlocfilehash: a2eaeb2de0a7caf502130bef788c17e515657d7a
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788955"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>配置 Microsoft Defender 防病毒软件扫描选项

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows 

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>使用Microsoft Intune配置扫描选项

有关详细信息，请参阅[Microsoft Intune中配置设备限制设置](/intune/device-restrictions-configure)，[Microsoft Defender 防病毒Intune中Windows 10的设备限制设置](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>使用Microsoft Endpoint Manager配置扫描选项

有关配置Microsoft Endpoint Manager (当前分支) 的详细信息，[请参阅如何创建和部署反恶意软件策略：扫描设置](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。

## <a name="use-group-policy-to-configure-scanning-options"></a>使用组策略配置扫描选项

> [!TIP]
> 下载组策略参考电子表格，其中列出了用于Windows随附的管理模板文件中包含的计算机和用户配置的策略设置。 编辑组策略对象时，可以配置引用电子表格。 <br/><br/> 以下是最新版本：
> - [组策略 设置 2020 年 5 月更新 (2004 年 5 月Windows 10参考电子表格) ](https://www.microsoft.com/download/details.aspx?id=101451)
> - [组策略 设置 2021 年 10 月 Windows 11 日更新 (21H2) 参考电子表格](https://www.microsoft.com/download/details.aspx?id=103506)

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中转到 **“计算机配置**”，然后单击 **“管理模板**”。

4. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒**，然后选择一个位置 (引用 [设置和](#settings-and-locations)本文中的位置) 。

5. 编辑策略对象。

6. 单击 **“确定**”，并重复任何其他设置。

### <a name="settings-and-locations"></a>设置和位置

|策略项和位置|默认设置 (（如果未配置）) |类的 `MSFT_MpPreference` PowerShell `Set-MpPreference` 参数或 WMI 属性|
|---|---|---|
|电子邮件扫描 <p> **扫描** \>**启用电子邮件扫描**<p>请参阅本文 (的电子邮件 [扫描限制](#email-scanning-limitations)) |Disabled|`-DisableEmailScanning`|
| 脚本扫描 | 已启用  | 此策略设置允许配置脚本扫描。 如果启用或未配置此设置，则将启用脚本扫描。 <p>请参阅 [Defender/AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender)  | 
|扫描 [重新分析点](/windows/win32/fileio/reparse-points) <p> **扫描** \>**启用重新分析点扫描**|Disabled|不可用 <p>请参阅[“重新分析点](/windows/win32/fileio/reparse-points)”|
|扫描映射的网络驱动器 <p> **扫描** \>**在映射的网络驱动器上运行完全扫描**|Disabled|`-DisableScanningMappedNetworkDrivesForFullScan`|
|扫描存档文件 (，例如.zip或.rar文件) 。 <p> **扫描** \>**扫描存档文件**|已启用|`-DisableArchiveScanning` <p>[扩展排除列表](configure-extension-file-exclusions-microsoft-defender-antivirus.md)将优先于此设置。|
|扫描网络上的文件 <p> **扫描** \>**扫描网络文件**|Disabled|`-DisableScanningNetworkFiles`|
|扫描打包的可执行文件 <p> **扫描** \>**扫描打包的可执行文件**|已启用|不可用|
|仅在完全扫描期间扫描可移动驱动器 <p> **扫描** \>**扫描可移动驱动器**|Disabled|`-DisableRemovableDriveScanning`|
|指定要扫描的存档文件夹中的子文件夹级别 <p>**扫描** \>**指定扫描存档文件的最大深度**|0|不可用|
|将扫描期间的最大 CPU 负载 (指定为百分比) 。 <p> **扫描** \>**指定扫描期间 CPU 利用率的最大百分比**|50|`-ScanAvgCPULoadFactor` <p>**注意**：最大 CPU 负载不是硬性限制，而是扫描引擎平均不超过最大值的指导。 手动运行扫描将忽略此设置，并且运行时没有任何 CPU 限制。|
|指定应扫描的存档文件的最大大小 (为千字节) 。 <p> **扫描** \>**指定要扫描的存档文件的最大大小**|无限制|不可用 <p>默认值 0 不适用任何限制|
|为计划扫描配置低 CPU 优先级 <p> **扫描** \>**为计划扫描配置低 CPU 优先级**|Disabled|不可用|

> [!NOTE]
> 如果启用了实时保护，则会在访问和执行文件之前对其进行扫描。 扫描范围包括所有文件，包括装载的可移动介质上的文件，如 USB 驱动器。 如果执行扫描的设备已启用实时保护或访问保护，则扫描还将包括网络共享。

## <a name="use-powershell-to-configure-scanning-options"></a>使用 PowerShell 配置扫描选项

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅

- [使用 PowerShell cmdlet 管理Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Defender 防病毒 cmdlet](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>使用 WMI 配置扫描选项

请参阅[Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="email-scanning-limitations"></a>电子邮件扫描限制

通过电子邮件扫描，可以扫描Outlook和其他邮件客户端在按需扫描和计划扫描期间使用的电子邮件文件。 此外，还会扫描电子邮件 (中的嵌入对象，例如附件和存档的文件) 。 可以扫描和修正以下文件格式类型：

- DBX
- MBX
- MIME

Outlook 2003 或更早版本 (使用的 PST 文件，其中存档类型设置为非 unicode) 也已扫描，但Microsoft Defender 防病毒无法修正在 PST 文件中检测到的威胁。

如果Microsoft Defender 防病毒检测到电子邮件中的威胁，它将向你显示以下信息，以帮助你识别泄露的电子邮件，以便你可以手动修正威胁：

- 电子邮件主题
- 附件名称

## <a name="scanning-mapped-network-drives"></a>扫描映射的网络驱动器

在任何 OS 上，仅扫描在系统级别映射的网络驱动器。 不会扫描用户级映射网络驱动器。 用户级映射网络驱动器是用户在会话中手动映射并使用自己的凭据映射的网络驱动器。

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

- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
- [配置计划的Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
