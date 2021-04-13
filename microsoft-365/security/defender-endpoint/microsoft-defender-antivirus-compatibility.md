---
title: Microsoft Defender 防病毒与其他安全产品的兼容性
description: Microsoft Defender 防病毒与其他安全产品和你使用的操作系统一起预期的结果。
keywords: windows defender， 下一代， 防病毒， 兼容性， 被动模式
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8eb52e277f7987477114db9333c3f90bb581ebb5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689932"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 防病毒兼容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>概述

Microsoft Defender 防病毒将自动启用，并安装在运行 Windows 10 的终结点和设备上。 但是，当使用另一个防病毒/反恶意软件解决方案时会发生什么情况？ 这取决于你是否将 Microsoft Defender [for Endpoint](microsoft-defender-endpoint.md) 与防病毒保护一起使用。
- 如果你组织的终结点和设备受非 Microsoft 防病毒/反恶意软件解决方案保护，并且未使用 Microsoft Defender for Endpoint，则 Microsoft Defender 防病毒将自动进入禁用模式。
- 如果你的组织将 Microsoft Defender for Endpoint 与非 Microsoft 防病毒/反恶意软件解决方案一同使用，则 Microsoft Defender 防病毒将自动进入被动模式。  (Microsoft Defender 防病毒.) 
- 如果你的组织将 Microsoft Defender for Endpoint 与非 Microsoft 防病毒/反恶意软件解决方案一同使用，并且你已启用阻止模式下的 [EDR，](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 那么每当检测到恶意项目时，Microsoft Defender for Endpoint 将采取措施来阻止和修正项目。

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>防病毒和 Microsoft Defender for Endpoint

下表总结了当第三方防病毒产品一起使用或不使用 Microsoft Defender for Endpoint 时，Microsoft Defender 防病毒会发生什么情况。 


| Windows 版本   | 反恶意软件保护  | Microsoft Defender for Endpoint 注册 | Microsoft Defender 防病毒状态     |
|------|------|-------|-------|
| Windows 10  | Microsoft 不提供或开发的第三方产品 | 是  | 被动模式  |
| Windows 10  | Microsoft 不提供或开发的第三方产品 | 否   | 自动禁用模式     |
| Windows 10  | Microsoft Defender 防病毒 | 是  | 活动模式 | 
| Windows 10  | Microsoft Defender 防病毒 | 否   | 活动模式 |
| Windows Server 版本 1803 或更高版本，或 Windows Server 2019 | Microsoft 不提供或开发的第三方产品 | 是  | 必须设置为被动模式， (手动) <sup> [[1](#fn1)]<sup>  | 
| Windows Server 版本 1803 或更高版本，或 Windows Server 2019 | Microsoft 不提供或开发的第三方产品 | 否  | 必须禁用 (手动) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 版本 1803 或更高版本，或 Windows Server 2019 | Microsoft Defender 防病毒  | 是 |         活动模式  |
| Windows Server 版本 1803 或更高版本，或 Windows Server 2019 | Microsoft Defender 防病毒 | 否  | 活动模式 |
| Windows Server 2016 | Microsoft Defender 防病毒 | 是 | 活动模式 |
| Windows Server 2016 | Microsoft Defender 防病毒 | 否 | 活动模式 |
| Windows Server 2016 | Microsoft 不提供或开发的第三方产品 | 是 | 必须禁用 (手动) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft 不提供或开发的第三方产品 | 否 | 必须禁用 (手动) <sup> [[2](#fn2)]<sup> |

 (<a id="fn1">1</a>) Windows Server 版本 1803 或更高版本或 Windows Server 2019 上，安装非 Microsoft 防病毒产品时，Microsoft Defender 防病毒不会自动进入被动模式。 在这种情况下，将 [Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) 设置为被动模式，以防止在服务器上安装多个防病毒产品导致的问题。

如果你使用的是 Windows Server 版本 1803 或更高版本或 Windows Server 2019，可以通过设置以下注册表项将 Microsoft Defender 防病毒设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForcePassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

> [!NOTE]
> `ForcePassiveMode`Windows Server 2016 不支持注册表项。

 (<a id="fn2">2</a>) Windows Server 2016 上，安装非 Microsoft 防病毒产品时，Microsoft Defender 防病毒不会自动进入被动模式。 此外，Microsoft Defender 防病毒在被动模式下不受支持。 在这种情况下，手动 [禁用/卸载 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) ，以防止在服务器上安装多个防病毒产品导致的问题。

有关 [Windows Server 安装的关键](microsoft-defender-antivirus-on-windows-server.md) 差异和管理选项，请参阅 Windows Server 上的 Microsoft Defender 防病毒。

> [!IMPORTANT]
> Microsoft Defender 防病毒仅适用于运行 Windows 10、Windows Server 2016、Windows Server 版本 1803 或更高版本以及 Windows Server 2019 的设备。
>
> 在 Windows 8.1 和 Windows Server 2012 中，企业级终结点防病毒保护作为 [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))提供，它通过 Microsoft Endpoint Configuration Manager 进行管理。
>
> Windows Defender Windows [8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)和 Windows Server 2012 上的消费者设备也提供，尽管它不在 Windows Server 2012 Server Core 安装上提供企业级管理 (或接口) 。

## <a name="functionality-and-features-available-in-each-state"></a>每种状态中可用的功能和特性

本节中的表总结了每种状态中可用的特性和功能。 该表仅供参考。 它旨在根据 Microsoft Defender 防病毒是处于活动模式、处于被动模式还是处于禁用/卸载状态&主动工作的功能描述这些功能。 

> [!IMPORTANT]
> 如果你在被动模式下使用 Microsoft Defender 防病毒或在阻止模式下使用 EDR，请不要关闭诸如实时保护、云提供的保护或有限定期扫描等功能。 

|Protection |活动模式 |被动模式 |块模式下的 EDR |已禁用或卸载 |
|:---|:---|:---|:---|:---|
| [实时保护和](./configure-real-time-protection-microsoft-defender-antivirus.md)[云保护](./enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 否 <sup> [[3](#fn3)]<sup> | 否 | 否 |
| [有限定期扫描可用性](./limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 否 | 是 |
| [文件扫描和检测信息](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |
|  [威胁修正](./configure-remediation-microsoft-defender-antivirus.md) | 是 | 请参阅注释 <sup> [[4](#fn4)]<sup> | 是 | 否 |
| [安全智能更新](./manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |

 (<a id="fn3">3</a>) 通常，当 Microsoft Defender 防病毒处于被动模式时，实时保护不会提供任何阻止或强制，即使处于启用状态且处于被动模式。 

 (<a id="fn4">4</a>) 当 Microsoft Defender 防病毒处于被动模式时，威胁修正功能仅在计划扫描或按需扫描期间处于活动状态。

> [!NOTE]
> 当 Microsoft Defender 防病毒处于主动或被动模式时[，Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)终结点数据丢失防护将继续正常运行。

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- 在活动模式下，Microsoft Defender 防病毒将用作计算机上防病毒应用。 使用 Configuration Manager、组策略、Intune 或其他管理产品进行的所有配置都将适用。 将扫描文件并修复威胁，并且检测信息会报告在配置工具中 (例如配置管理器或计算机本身上的 Microsoft Defender 防病毒) 。

- 在被动模式下，Microsoft Defender 防病毒不会用作防病毒应用，并且 Microsoft Defender 防病毒不会修正威胁。 将扫描文件，并针对与 Microsoft Defender for Endpoint 服务共享的威胁检测提供报告。 因此，你可能会在安全中心控制台中遇到警报，将 Microsoft Defender 防病毒作为源，即使 Microsoft Defender 防病毒处于被动模式。

- 当 [阻止模式下的 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 处于打开状态并且 Microsoft Defender 防病毒不是主要的防病毒解决方案时，它仍可检测和修正恶意项目。

- 禁用后，Microsoft Defender 防病毒不会用作防病毒应用。 不扫描文件，不修正威胁。 通常不建议禁用/卸载 Microsoft Defender 防病毒;如果可能，如果你使用的是非 Microsoft 反恶意软件/防病毒解决方案，请让 Microsoft Defender 防病毒处于被动模式。

- 如果你在适用于终结点的 Microsoft Defender 中注册，并且使用的是第三方反恶意软件产品，则启用被动模式。 [该服务需要 Microsoft Defender](/microsoft-365/security/defender-endpoint/defender-compatibility) 防病毒服务中的常见信息共享，以便正确监视设备和网络的入侵尝试和攻击。

- 自动禁用 Microsoft Defender 防病毒后，如果非 Microsoft 防病毒产品提供的保护过期或停止提供实时保护免受病毒、恶意软件或其他威胁，可自动重新启用它。 自动重新启用有助于确保在设备上维护防病毒保护。 它还允许你启用 [有限定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)，这将使用 Microsoft Defender 防病毒引擎定期检查除主防病毒应用之外的威胁。

- 当 Microsoft Defender 防病毒处于被动模式时，你仍可以 [管理 Microsoft Defender 防病毒的更新](manage-updates-baselines-microsoft-defender-antivirus.md);但是，如果你的设备具有最新的非 Microsoft 防病毒产品，可提供实时恶意软件防护，则你无法将 Microsoft Defender 防病毒移动到活动模式。 为获得最佳安全分层防御和检测检测机制，请确保更新 [Microsoft Defender ](./manage-updates-baselines-microsoft-defender-antivirus.md) 防病毒保护 (安全智能更新、引擎和平台) 即使 Microsoft Defender 防病毒在被动模式下运行。

   如果你卸载非 Microsoft 防病毒产品，并使用 Microsoft Defender 防病毒为设备提供保护，Microsoft Defender 防病毒将自动返回到其正常活动模式。

> [!WARNING]
> 不要禁用、停止或修改 Microsoft Defender 防病毒、适用于终结点的 Microsoft Defender 或 Windows 安全中心应用使用的任何关联服务。 此建议包括 wscsvc、SecurityHealthService、MsSense、Sense、WinDefend 或 *MsMpEng* 服务和进程。     手动修改这些服务可能会导致设备严重不稳定，并且可能会使网络易受攻击。 在使用非 Microsoft 防病毒解决方案及其信息在 Windows 安全应用中的显示方式时，禁用、停止或修改这些服务也 [可能导致问题](microsoft-defender-security-center-antivirus.md)。


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [配置 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [解决 Microsoft Defender for终结点的误报/负数](defender-endpoint-false-positives-negatives.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)