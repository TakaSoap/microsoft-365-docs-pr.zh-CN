---
title: Microsoft Defender 防病毒安全产品的兼容性
description: 了解Microsoft Defender 防病毒安全产品和操作系统的集成。
keywords: windows defender， defender for endpoint， 下一代， 防病毒， 兼容性， 被动模式
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 09/14/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: baf8114372d86a995483c61802462bd94597f147
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240076"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender 防病毒安全产品的兼容性

**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Microsoft Defender 防病毒自动安装在运行以下版本的 Windows：

- Windows 10或更高版本
- Windows Server 2016
- Windows服务器、版本 1803 或更高版本
- Windows Server 2019
- Windows Server 2022

当使用另一个非 Microsoft 防病毒/反恶意软件解决方案时，会发生什么情况？ 能否将Microsoft Defender 防病毒防病毒产品一起运行？ 答案取决于多种因素，例如操作系统以及是否将 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) 与防病毒保护一起使用。

本文介绍使用或不带 Defender for Endpoint Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案会发生什么情况。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>没有适用于终结点的 Defender 的防病毒保护

本部分介绍未载入Microsoft Defender 防病毒 Defender for Endpoint 的终结点上的非 Microsoft 防病毒/反恶意软件产品会发生什么情况。 下表总结了预期内容：

<br/><br/>

|Windows 版本|主防病毒/反恶意软件解决方案|Microsoft Defender 防病毒状态|
|---|---|---|---|
|Windows 10|Microsoft Defender 防病毒|主动模式|
|Windows 10|非 Microsoft 防病毒/反恶意软件解决方案|禁用模式 (自动) |
|Windows Server 2016 <p> Windows服务器、版本 1803 或更高版本 <p> WindowsServer 2019 或 Windows Server 2022|Microsoft Defender 防病毒|主动模式|
|Windows Server 2016 <p> Windows服务器、版本 1803 或更高版本 <p> WindowsServer 2019 或 Windows Server 2022|非 Microsoft 防病毒/反恶意软件解决方案|禁用 (设置) <sup>[[1](#fn1)]</sup>|


 (<a id="fn1">1</a>) 在 Windows 服务器上，如果运行的是非 Microsoft 防病毒产品，可以使用组策略禁用 Microsoft Defender 防病毒，或者使用[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)注册表项禁用 Microsoft Defender 防病毒。 若要使用注册表项，请导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` ，并设置或创建名为 的 DWORD 项 `DisableAntiSpyware` 。 将其值设置为 (将注册表项的值设置为 true) ，并选择 `1` **十** 六进制作为其基础。

> [!TIP]
> 有关[Microsoft Defender 防病毒 Server Windows](microsoft-defender-antivirus-on-windows-server.md)的主要区别和管理选项，请参阅 Windows Server。 在Windows Server 2016上，*你可能会看到Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒。*

## <a name="antivirus-protection-with-defender-for-endpoint"></a>使用 Defender for Endpoint 进行防病毒保护

如果你的组织将非 Microsoft 防病毒/反恶意软件解决方案与 Defender for Endpoint 一Microsoft Defender 防病毒，则根据你的操作系统，它可以在被动模式下运行。

<br/><br/>

|Windows 版本|主防病毒/反恶意软件解决方案|Microsoft Defender 防病毒状态|
|---|---|---|---|
|Windows 10或更高版本|Microsoft Defender 防病毒|主动模式|
|Windows 10或更高版本|非 Microsoft 防病毒/反恶意软件解决方案|被动模式 (自动) |
|Windows Server 2016 <p> Windows服务器、版本 1803 或更高版本 <p> WindowsServer 2019 或 Windows Server 2022|Microsoft Defender 防病毒|主动模式|
|Windows服务器、版本 1803 或更高版本 <p> WindowsServer 2019 或 Windows Server 2022|非 Microsoft 防病毒/反恶意软件解决方案|被动模式 (手动设置) <sup> [[2](#fn2)]<sup></sup>|
|Windows Server 2016|非 Microsoft 防病毒/反恶意软件解决方案|禁用 (设置) <sup>[[3](#fn3)]</sup>|

 (<a id="fn2">2</a>) 在 Windows Server、版本 1803 或更高版本、Windows Server 2019 或 Windows Server 2022 上，安装非 Microsoft 防病毒产品时，手动将 Microsoft Defender 防病毒 设置为被动模式。 可以使用 **ForceDefenderPassiveMode** 注册表项执行此任务。 若要使用注册表项，请导航到 `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` ，并设置或创建名为 的 DWORD 项 `ForceDefenderPassiveMode` 。 将其值设置为 (将注册表项的值设置为 true) ，并选择 `1` **十** 六进制作为其基础。 有关详细信息，请参阅被动[模式和Windows服务器](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)。

 (<a id="fn3">3</a>) 在 Windows Server 2016 上，可以使用组策略禁用 Microsoft Defender 防病毒 以禁用 Windows Defender 防病毒，或者使用[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)注册表项禁用。 若要使用注册表项，请导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` ，并设置或创建名为 的 DWORD 项 `DisableAntiSpyware` 。 将其值设置为 (将注册表项的值设置为 true) ，并选择 `1` **十** 六进制作为其基础。

> [!TIP]
> 有关[Microsoft Defender 防病毒 Server Windows](microsoft-defender-antivirus-on-windows-server.md)的主要区别和管理选项，请参阅 Windows Server。 在Windows Server 2016上，*你可能会看到Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒。*

> [!IMPORTANT]
> Microsoft Defender 防病毒仅在运行 Windows 10、Windows Server 2012 R2、Windows Server 2016、Windows Server 版本 1803 或更高版本以及 Windows Server 2019 的设备上可用。
>
> 在 Windows 8.1 中，企业级终结点防病毒保护作为[System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))提供，它通过 Microsoft Endpoint Configuration Manager。
>
> Windows Defender还针对 Windows 8.1[上的消费者](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)设备提供，尽管它不提供企业级管理。

Defender for Endpoint 包括进一步扩展安装在终结点上的防病毒保护的功能。 您可以与另一Microsoft Defender 防病毒一起运行防病毒解决方案。

例如，在阻止[模式下 (EDR) ](edr-in-block-mode.md)终结点检测和响应功能可提供对恶意项目的更多保护，即使Microsoft Defender 防病毒不是主要的防病毒产品。 这些功能要求Microsoft Defender 防病毒被动模式或主动模式安装并运行这些功能。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>在被动Microsoft Defender 防病毒运行要求

为了使 Microsoft Defender 防病毒在被动模式下运行，终结点必须满足以下要求：

- 操作系统：Windows 10或更高版本;Windows服务器、版本 1803 或更高版本;或 Windows Server 2019 或 Windows Server 2022
- Microsoft Defender 防病毒必须安装
- 必须安装另一个非 Microsoft 防病毒/反恶意软件产品，并用作主要的防病毒解决方案
- 终结点必须载入到适用于终结点的 Defender

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>更改Microsoft Defender 防病毒 Defender for Endpoint 功能的影响

Defender for Endpoint 影响 Microsoft Defender 防病毒是否可以在被动模式下运行。 Microsoft Defender 防病毒 Defender for Endpoint 中的某些功能。 例如，实时保护在用户处于Microsoft Defender 防病毒或被动模式时有效，但在禁用Microsoft Defender 防病毒卸载时则不能。

本节中的表总结了根据 Microsoft Defender 防病毒 处于主动模式、被动模式还是禁用/卸载状态而主动运行的特性和功能。

> [!IMPORTANT]
> 下表设计为仅供参考。 如果你在被动模式下使用 Microsoft Defender 防病毒 或在阻止模式下使用[EDR，](edr-in-block-mode.md)请不要关闭功能，例如实时保护、云提供的保护或有限定期扫描，这将在后台检测和修正在泄露后检测到的恶意项目。

<br/><br/>

|Protection|Microsoft Defender 防病毒 <br/><br/> 主动模式|Microsoft Defender 防病毒 <br/><br/> 被动模式|Microsoft Defender 防病毒 <br/><br/> 已禁用或卸载|[块模式下的 EDR](edr-in-block-mode.md)|
|---|---|---|---|---|
|[实时保护和](configure-real-time-protection-microsoft-defender-antivirus.md)[云保护](enable-cloud-protection-microsoft-defender-antivirus.md)|是|否 <sup>[[5](#fn5)]</sup>|否|否|
|[有限定期扫描可用性](limited-periodic-scanning-microsoft-defender-antivirus.md)|否|否|是|否|
|[文件扫描和检测信息](review-scan-results-microsoft-defender-antivirus.md)|是|是|否|是|
|[威胁修正](configure-remediation-microsoft-defender-antivirus.md)|是|请参阅注释 <sup>[[6](#fn6)]</sup>|否|是|
|[安全智能更新](manage-updates-baselines-microsoft-defender-antivirus.md)|是|是|否|是|

 (<a id="fn5">5</a>) 通常，当 Microsoft Defender 防病毒 处于被动模式时，实时保护不会提供任何阻止或强制，即使处于启用状态且处于被动模式。

 (<a id="fn6">6</a>) 当 Microsoft Defender 防病毒 处于被动模式时，威胁修正功能仅在计划扫描或按需扫描期间处于活动状态。

> [!NOTE]
> [Microsoft 365处于主动或被动](/microsoft-365/compliance/endpoint-dlp-learn-about)模式时，Microsoft Defender 防病毒数据丢失防护继续正常运行。

## <a name="important-notes"></a>重要说明

- 不要禁用、停止或修改由 Microsoft Defender 防病毒、Defender for Endpoint 或 Windows 安全中心 使用的任何关联服务。 此建议包括 wscsvc、SecurityHealthService、MsSense、Sense、WinDefend 或 *MsMpEng* 服务和进程。     手动修改这些服务可能会导致设备严重不稳定，并且可能会使网络易受攻击。 在使用非 Microsoft 防病毒解决方案时，禁用、停止或修改这些服务也可能导致问题，以及这些解决方案的信息在 Windows 安全中心[应用程序中的显示方式](microsoft-defender-security-center-antivirus.md)。

- 在 Defender for Endpoint 中，EDR以阻止模式打开，即使Microsoft Defender 防病毒不是你的主要防病毒解决方案。 EDR阻止模式时检测并修正在设备中发现的恶意项目， (泄露后) 。 若要了解更多信息，请参阅EDR[阻止模式。](edr-in-block-mode.md)

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>如何确认Microsoft Defender 防病毒

可以使用多种方法之一来确认Microsoft Defender 防病毒状态，如下表所述：

<br/><br/>

|方法|Procedure|
|---|---|
|Windows 安全中心应用| 1.在Windows上，打开Windows 安全中心应用。<br/>2. 选择 **病毒&威胁防护。**<br/>3. **Who保护我？选择** 管理 **提供程序**。<br/>4. 在"**安全提供程序"** 页上的"**防病毒**"下 **，Microsoft Defender 防病毒"已打开"。**|
|任务管理器| 1. 在Windows上，打开"任务管理器"应用。<br/>2. 选择" **详细信息"** 选项卡。<br/>3. 在 **MsMpEng.exe** 查找列表。|
|Windows PowerShell <br/><br/>  (确认Microsoft Defender 防病毒运行) | 1.在Windows上，打开Windows PowerShell。 <br/>2. 运行以下 PowerShell cmdlet：。 `Get-Process`<br/>3. 查看结果。 如果启用 **MsMpEng.exe，Microsoft Defender 防病毒** 看到" 设置"。|
|Windows PowerShell <br/><br/>  (确认防病毒保护已就位) | 可以使用 [Get-MpComputerStatus PowerShell cmdlet](/powershell/module/defender/get-mpcomputerstatus)。 <br/><br/>1.在Windows上，打开Windows PowerShell。<br/>2. 运行以下 PowerShell cmdlet：。 `Get-MpComputerStatus|select AMRunningMode`<br/>3. 查看结果。 如果在 **终结点上启用了** 常规或 **被动** Microsoft Defender 防病毒，则应该会看到"正常"或"被动"。 |
|命令提示符| 1. 在 Windows上，打开命令提示符。<br/>2. 键入 `sc query windefend` ，然后按 Enter。<br/>3. 查看结果以确认Microsoft Defender 防病毒处于被动模式。 |

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>有关状态Microsoft Defender 防病毒详细信息

本节中的表介绍了你可能在管理时看到的各种Microsoft Defender 防病毒。

<br/><br/>

| 状态 | 发生的情况 |
|---|---|
| 主动模式 | 在活动模式下，Microsoft Defender 防病毒用作计算机上防病毒应用。 设置配置管理器、组策略、Microsoft Intune或其他管理产品进行配置。 将扫描文件、修正威胁，并且检测信息会报告在配置工具 (如配置管理器或终结点本身上的 Microsoft Defender 防病毒 应用) 。 |
| 被动模式 | 在被动模式下，Microsoft Defender 防病毒不会用作防病毒应用，并且威胁 *不会* 由 Microsoft Defender 防病毒。 但是，威胁可通过终结点[检测和响应 (EDR) 阻止模式](edr-in-block-mode.md)进行修正。 <br/><br/> 将扫描文件，并针对与 Defender for Endpoint 服务共享的威胁检测提供报告。 你可能会在安全中心看到警报，Microsoft Defender 防病毒作为源，即使Microsoft Defender 防病毒处于被动模式。 [](microsoft-defender-security-center.md) <br/><br/> 当Microsoft Defender 防病毒处于被动模式时，你仍可以[管理](manage-updates-baselines-microsoft-defender-antivirus.md)Microsoft Defender 防病毒;但是，如果你的设备具有可提供实时恶意软件Microsoft Defender 防病毒非 Microsoft 防病毒产品，则你无法将其移动到活动模式。 <br/><br/> 为获得最佳安全分层防御和检测，请确保获取防病毒和反恶意软件更新，即使 Microsoft Defender 防病毒处于被动模式。 请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。 <br/><br/> **注意**：被动模式在用户上Windows Server 2016。 |
| 禁用 <br/><br/> 或 <br/><br/> 已卸载 | 禁用或卸载后，Microsoft Defender 防病毒应用不会用作防病毒应用。 不扫描文件，不修正威胁。 <br/><br/> 通常不建议禁用Microsoft Defender 防病毒卸载应用程序;如果可能，Microsoft Defender 防病毒 Microsoft 反恶意软件/防病毒解决方案，请保持处于被动模式。 <br/><br/> 如果自动Microsoft Defender 防病毒，当非 Microsoft 防病毒/反恶意软件产品过期或停止提供实时保护免受病毒、恶意软件或其他威胁时，可自动重新启用它。 自动重新启用Microsoft Defender 防病毒有助于确保在终结点上维护防病毒保护。 <br/><br/> 如果你使用的是[非](limited-periodic-scanning-microsoft-defender-antivirus.md)Microsoft 防病毒应用，则你可能还使用有限定期扫描Microsoft Defender 防病毒引擎定期检查威胁。 |


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防病毒软件](microsoft-defender-antivirus-on-windows-server.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)
