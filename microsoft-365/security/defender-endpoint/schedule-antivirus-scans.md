---
title: 使用Microsoft Defender 防病毒计划定期快速和完整扫描
description: 设置定期 (计划的) 扫描，包括应何时运行，以及它们是作为完整扫描还是快速扫描运行
keywords: 快速扫描， 完全扫描， 快速与完整， 计划扫描， 每天， 每周， 时间， 计划， 定期， 定期
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/22/2022
ms.reviewer: pauhijbr, ksarens, mkaminska
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: e7b854b2a4c9f4202296ed404d067182de8627bd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790254"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>配置计划的快速或完整的 Microsoft Defender 防病毒软件扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

除了始终打开、实时保护和 [按需防病毒](run-scan-microsoft-defender-antivirus.md) 扫描外，还可以设置定期的计划防病毒扫描。 可以配置扫描类型、何时应进行扫描，以及是否应在 [保护更新](manage-protection-updates-microsoft-defender-antivirus.md) 后或未使用终结点时进行扫描。 还可以设置特殊扫描，以根据需要完成修正操作。

## <a name="what-do-you-want-to-do"></a>要执行什么操作？

- [了解快速扫描、完全扫描和自定义扫描](#quick-scan-full-scan-and-custom-scan)
- [使用组策略计划防病毒扫描](schedule-antivirus-scans-group-policy.md)
- [使用Windows PowerShell计划防病毒扫描](schedule-antivirus-scans-powershell.md)
- [使用Windows管理检测计划防病毒扫描](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- 默认情况下，Microsoft Defender 防病毒在任何计划的扫描时间前 15 分钟检查更新。 可以 [管理应下载和应用保护更新以](manage-protection-update-schedule-microsoft-defender-antivirus.md) 重写此默认设置的计划。

- 如果设备在计划的完全扫描期间拔下电源并以电池方式运行，则计划的扫描将停止，事件 1002 会指示扫描在完成前停止。 Microsoft Defender 防病毒将在下一个计划时间运行完全扫描。

## <a name="quick-scan-full-scan-and-custom-scan"></a>快速扫描、完全扫描和自定义扫描

设置计划扫描时，可以指定扫描是完全扫描还是快速扫描。 在大多数情况下，建议进行快速扫描。

<br/><br/>

|快速扫描|完全扫描|自定义扫描|
|---|---|---|
| (建议) 快速扫描可查看注册恶意软件以从系统开始的所有位置，例如注册表项和已知Windows启动文件夹。 <br/><br/>结合始终打开的实时保护（在打开和关闭文件时对文件进行评审;每当用户导航到文件夹时，快速扫描可帮助提供对以系统和内核级恶意软件开头的恶意软件的有力保护。<br/><br/>在大多数情况下，快速扫描已足够，是计划扫描的建议选项。|完全扫描首先运行快速扫描，然后继续对所有已装载的固定磁盘和可移动/网络驱动器进行顺序文件扫描 (如果将完全扫描配置为执行此操作) 。<br/><br/>完全扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据量和类型。<br/><br/>完全扫描完成后，将提供新的安全智能，然后需要进行新的扫描，以确保没有使用新的安全智能检测到其他威胁。<br/><br/>由于完全扫描涉及的时间和资源，一般情况下，Microsoft 不建议计划完全扫描。|自定义扫描在指定的文件和文件夹上运行。 例如，可以选择扫描 USB 驱动器或设备本地驱动器上的特定文件夹。|

> [!NOTE]
> 默认情况下，快速扫描在已装载的可移动设备（如 USB 驱动器）上运行。

## <a name="how-do-i-know-which-scan-type-to-choose"></a>如何实现知道要选择哪种扫描类型？

使用下表选择扫描类型。
<br/><br/>

|应用场景|建议的扫描类型|
|---|---|
|你想要设置常规的计划扫描|快速扫描 <p> 快速扫描检查设备上的进程、内存、配置文件和某些位置。 快速扫描与 [始终可用的实时保护](configure-real-time-protection-microsoft-defender-antivirus.md)相结合，有助于为以系统和内核级恶意软件开头的恶意软件提供强大的覆盖范围。 实时保护会在打开和关闭文件时以及每当用户导航到文件夹时对其进行评审。|
|在单个设备上检测到威胁（如恶意软件）|快速扫描 <p> 在大多数情况下，快速扫描会捕获并清理检测到的恶意软件。|
|想要运行 [按需扫描](run-scan-microsoft-defender-antivirus.md)|快速扫描|
|你希望确保可移植设备（如 USB 驱动器）不包含恶意软件|自定义扫描 <p> 通过自定义扫描，可以选择特定位置、文件夹或文件，并运行快速扫描。|

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>关于快速和完整扫描，我还需要了解什么？

- 恶意文件可以存储在未包含在快速扫描中的位置。 但是，始终实时保护会评审打开和关闭的所有文件，以及用户访问的文件夹中的任何文件。 实时保护和快速扫描的组合有助于提供对恶意软件的有力保护。

- 通过 [云传递的保护](cloud-protection-microsoft-defender-antivirus.md) 进行访问保护有助于确保系统上访问的所有文件都使用最新的安全智能和云机器学习模型进行扫描。

- 当实时保护检测到恶意软件并且最初未确定受影响文件的范围时，Microsoft Defender 防病毒在修正过程中启动完全扫描。

- 完全扫描可以检测其他扫描未检测到的恶意文件，例如快速扫描。 但是，完全扫描可能需要一段时间，并使用宝贵的系统资源来完成。

- 如果设备长时间处于脱机状态，则完全扫描可能需要更长的时间才能完成。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)