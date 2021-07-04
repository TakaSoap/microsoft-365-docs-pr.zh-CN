---
title: Microsoft Defender 防病毒安全产品的兼容性
description: 了解Microsoft Defender 防病毒安全产品和操作系统的集成。
keywords: windows defender， defender for endpoint， 下一代， 防病毒， 兼容性， 被动模式
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: f03fab3f296f98b448693c6a5d0886f409201703
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288475"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 防病毒兼容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>摘要

Microsoft Defender 防病毒自动启用，并安装在运行 Windows 10 的终结点Windows 10。 但是，当使用 (非 Microsoft) /反恶意软件解决方案时会发生什么情况？ 这取决于你是否将 Microsoft Defender [for Endpoint](microsoft-defender-endpoint.md) 与防病毒保护一起使用。 本文介绍了当终结点载入到 Microsoft Defender for Endpoint 时，防病毒/反恶意软件解决方案会发生什么情况。

## <a name="keep-the-following-points-in-mind"></a>请记住以下几点

- 在活动模式下，Microsoft Defender 防病毒用作计算机上防病毒应用。 使用 Configuration Manager、组策略、Intune 或其他管理产品进行的所有配置都将适用。 将扫描文件并修正威胁，并且检测信息会报告在配置工具 (例如配置管理器或计算机本身上的 Microsoft Defender 防病毒 应用) 。

- 在被动模式下，Microsoft Defender 防病毒不会用作防病毒应用，威胁不会由 Microsoft Defender 防病毒。 将扫描文件，并针对与 Microsoft Defender for Endpoint 服务共享的威胁检测提供报告。 你可能会在安全中心看到警报，Microsoft Defender 防病毒作为源，即使Microsoft Defender 防病毒处于被动模式。 [](microsoft-defender-security-center.md)

- 当[EDR阻止模式时，如果](edr-in-block-mode.md)Microsoft Defender 防病毒不是主要的防病毒解决方案，它将检测和修正恶意项目。 EDR阻止模式要求Microsoft Defender 防病毒模式或被动模式启用阻止模式。

- 禁用后，Microsoft Defender 防病毒不用作防病毒应用。 不扫描文件，不修正威胁。 通常不建议Microsoft Defender 防病毒/卸载应用程序;如果可能，Microsoft Defender 防病毒 Microsoft 反恶意软件/防病毒解决方案，请保持处于被动模式。

- 如果你在适用于终结点的 Microsoft Defender 中注册，并且使用的是第三方反恶意软件产品，则启用被动模式。 该服务需要共享来自 Microsoft Defender 防病毒 服务的常见信息，以便正确监视设备和网络的入侵尝试和攻击。 若要了解的详细信息，请参阅[Microsoft Defender 防病毒 Microsoft Defender for Endpoint 的兼容性](defender-compatibility.md)。 

- 当Microsoft Defender 防病毒处于被动模式时，你仍可以[管理](manage-updates-baselines-microsoft-defender-antivirus.md)Microsoft Defender 防病毒;但是，如果你的设备具有提供实时恶意软件Microsoft Defender 防病毒最新的非 Microsoft 防病毒产品，则你无法将其移动到活动模式。 为了获得最佳安全分层防御和检测机制，请确保更新[Microsoft Defender 防病毒 保护 (](manage-updates-baselines-microsoft-defender-antivirus.md)安全智能更新、引擎和平台) 即使 Microsoft Defender 防病毒 在被动模式下运行。

- 自动Microsoft Defender 防病毒时，如果非 Microsoft 防病毒产品提供的保护过期或停止提供实时保护免受病毒、恶意软件或其他威胁，可自动重新启用它。 自动重新启用有助于确保在设备上维护防病毒保护。 它还允许你启用[有限定期](limited-periodic-scanning-microsoft-defender-antivirus.md)扫描，该扫描使用 Microsoft Defender 防病毒 引擎定期检查除主防病毒应用之外的威胁。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案

下表总结了当非 Microsoft 防病毒/反恶意软件解决方案Microsoft Defender 防病毒或没有 Microsoft Defender for Endpoint 时，将会发生什么情况。 

| Windows 版本   | 防病毒/反恶意软件解决方案  | 已载入 <br/> 适用于终结点的 Defender？ | Microsoft Defender 防病毒状态     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender 防病毒 | 是  | 活动模式 | 
| Windows 10  | Microsoft Defender 防病毒 | 否   | 活动模式 |
| Windows 10  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | 被动模式 (自动)  |
| Windows 10  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否   | 禁用模式 (自动)     |
| Windows服务器版本 1803 或更高版本 <p> Windows Server 2019 | Microsoft Defender 防病毒  | 是 |         活动模式  |
| Windows服务器版本 1803 或更高版本 <p> Windows Server 2019 | Microsoft Defender 防病毒 | 否  | 活动模式 |
| Windows服务器版本 1803 或更高版本 <p> Windows Server 2019 | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | Microsoft Defender 防病毒必须设置为被动模式， (手动) <sup> [[1](#fn1)]<sup>  | 
| Windows服务器版本 1803 或更高版本 <p> Windows Server 2019 | 非 Microsoft 防病毒/反恶意软件解决方案 | 否  | Microsoft Defender 防病毒手动禁用 (<sup> [[2]) 禁用该设置](#fn2)<sup></sup>  |
| Windows Server 2016 | Microsoft Defender 防病毒 | 是 | 活动模式 |
| Windows Server 2016 | Microsoft Defender 防病毒 | 否 | 活动模式 |
| Windows Server 2016 | 非 Microsoft 防病毒/反恶意软件解决方案 | 是 | Microsoft Defender 防病毒手动禁用 (<sup> [[2]) 禁用该设置](#fn2)<sup> |
| Windows Server 2016 | 非 Microsoft 防病毒/反恶意软件解决方案 | 否 | Microsoft Defender 防病毒手动禁用 (<sup> [[2]) 禁用该设置](#fn2)<sup> |

 (<a id="fn1">1</a>) 在 Windows Server 版本 1803 或更高版本或 Windows Server 2019 上，安装非 Microsoft 防病毒产品时，Microsoft Defender 防病毒 不会自动进入被动模式。 在这种情况下，将[Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode)设置为被动模式，以防止在服务器上安装多个防病毒产品导致的问题。 可以使用 PowerShell Microsoft Defender 防病毒组策略或注册表项将用户设置为被动模式。

如果使用的是 Windows Server、版本 1803 或更高版本或 Windows Server 2019，可以通过设置以下注册表项将 Microsoft Defender 防病毒 设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

> [!NOTE]
> 系统不支持被动Windows Server 2016。 注册表项可用于 Windows Server 版本 1803 或更高版本，或 `ForceDefenderPassiveMode` Windows Server 2019，但不能Windows Server 2016。 

 (<a id="fn2">2</a>) On Windows Server 2016，如果使用的是非 Microsoft 防病毒产品，则不能在被动Microsoft Defender 防病毒或主动模式下运行防病毒。 在这种情况下，手动[禁用/卸载](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016)Microsoft Defender 防病毒，以防止在服务器上安装多个防病毒产品导致的问题。

有关[Microsoft Defender 防病毒 Server Windows](microsoft-defender-antivirus-on-windows-server.md)的主要区别和管理选项，请参阅 Windows Server。

> [!IMPORTANT]
> Microsoft Defender 防病毒仅在运行 Windows 10、Windows Server 2016、Windows Server 版本 1803 或更高版本以及 Windows Server 2019 的设备上可用。
>
> 在 Windows 8.1 和 Windows Server 2012 中，企业级终结点防病毒保护作为 System Center Endpoint Protection 提供，它[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))通过 Microsoft Endpoint Configuration Manager 进行管理。
>
> Windows Defender还针对 Windows 8.1 和[Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)上的消费者设备提供，尽管它不提供企业级管理 (或 Windows Server 2012 Server Core) 上的接口。

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>更改Microsoft Defender 防病毒 Defender for Endpoint 功能的影响

本节中的表总结了每种状态中可用的特性和功能。 该表仅供参考。 它旨在根据 Microsoft Defender 防病毒 处于活动模式、处于被动模式还是处于禁用/卸载状态&描述当前是否正常工作的功能。 

> [!IMPORTANT]
> 如果你在被动模式下使用 Microsoft Defender 防病毒 或在阻止模式下使用 EDR，请不要关闭实时保护、云保护或有限定期扫描等功能。 

|Protection |活动模式 |被动模式 |阻止模式下的 EDR |已禁用或卸载 |
|:---|:---|:---|:---|:---|
| [实时保护和](configure-real-time-protection-microsoft-defender-antivirus.md)[云保护](enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 否 <sup> [[3](#fn3)]<sup> | 否 | 否 |
| [有限定期扫描可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 否 | 是 |
| [文件扫描和检测信息](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |
|  [威胁修正](configure-remediation-microsoft-defender-antivirus.md) | 是 | 请参阅注释 <sup> [[4](#fn4)]<sup> | 是 | 否 |
| [安全智能更新](manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 是 | 否 |

 (<a id="fn3">3</a>) 通常，当 Microsoft Defender 防病毒 处于被动模式时，实时保护不会提供任何阻止或强制，即使处于启用状态且处于被动模式。 

 (<a id="fn4">4</a>) 当Microsoft Defender 防病毒处于被动模式时，威胁修正功能仅在计划扫描或按需扫描期间处于活动状态。

> [!NOTE]
> [Microsoft 365处于主动或被动](/microsoft-365/compliance/endpoint-dlp-learn-about)模式时，Microsoft Defender 防病毒数据丢失防护继续正常运行。

## <a name="why-defender-for-endpoint-matters"></a>Defender for Endpoint 为什么很重要

考虑将终结点载入 Defender for Endpoint，即使你使用的是非 Microsoft 防病毒/反恶意软件解决方案。 在大多数情况下，当你将设备载入 Defender for Endpoint 时，你可以将Microsoft Defender 防病毒 Microsoft 防病毒解决方案一起用于添加保护。 例如，可以在阻止模式下EDR [](edr-in-block-mode.md)，以阻止和修正主防病毒解决方案可能错过的恶意项目。 

以下是相应的工作方式：

- 如果你组织的客户端设备受非 Microsoft 防病毒/反恶意软件解决方案保护，当这些设备载入 Defender for Endpoint 时，Microsoft Defender 防病毒自动进入被动模式。 在这种情况下，将发生威胁检测，但实时保护和威胁不会由 Microsoft Defender 防病毒。 **注意**：此特定方案不适用于运行 Windows Server 的终结点。

- 如果你组织的客户端设备受非 Microsoft 防病毒/反恶意软件解决方案保护，并且这些设备未载入到 Microsoft Defender for Endpoint，Microsoft Defender 防病毒将自动进入禁用模式。 在这种情况下，用户不会检测或修正威胁Microsoft Defender 防病毒。 **注意**：此特定方案不适用于运行 Windows Server 的终结点。

- 如果组织的终结点运行的是 Windows Server，并且这些终结点受非 Microsoft 防病毒/反恶意软件解决方案保护，当这些终结点载入到 Defender for Endpoint 时，Microsoft Defender 防病毒 不会自动进入被动模式或禁用模式。 在此特定方案中，必须相应地配置 Windows Server 终结点。 

   - 在 Windows Server 版本 1803 或更高版本以及 Windows Server 2019 上，可以将 Microsoft Defender 防病毒 设置为在被动模式下运行。 
   - 在Windows Server 2016上，Microsoft Defender 防病毒必须禁用 (被动模式不受支持Windows Server 2016) 。

- 如果组织的终结点受非 Microsoft 防病毒/反恶意软件解决方案保护，当这些设备载入启用[EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)且阻止模式下的 Defender for Endpoint 时，终结点的 Defender 将阻止并修正恶意项目。 **注意**：此特定方案不适用于Windows Server 2016。 EDR阻止模式要求Microsoft Defender 防病毒模式或被动模式启用阻止模式。


> [!WARNING]
> 不要禁用、停止或修改 Microsoft Defender for Endpoint 或 Microsoft Defender 防病毒 应用使用的任何Windows 安全中心服务。 此建议包括 wscsvc、SecurityHealthService、MsSense、Sense、WinDefend 或 *MsMpEng* 服务和进程。     手动修改这些服务可能会导致设备严重不稳定，并且可能会使网络易受攻击。 禁用、停止或修改这些服务在使用非 Microsoft 防病毒解决方案时，以及其信息在 Windows 安全中心 应用中的显示[方式也可能导致问题](microsoft-defender-security-center-antivirus.md)。


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防病毒软件](microsoft-defender-antivirus-on-windows-server.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [配置Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)
