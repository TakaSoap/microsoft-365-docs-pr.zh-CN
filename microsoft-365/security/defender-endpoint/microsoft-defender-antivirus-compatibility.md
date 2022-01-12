---
title: Microsoft Defender 防病毒安全产品的兼容性
description: 了解Microsoft Defender 防病毒安全产品和操作系统的集成。
keywords: windows defender， defender for endpoint， 下一代， 防病毒， 兼容性， 被动模式
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
ms.date: 01/06/2022
ms.collection: M365-security-compliance
ms.openlocfilehash: d436dbcc689364276ec8e33ba03e7d15eb52f281
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941896"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender 防病毒安全产品的兼容性

**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

Microsoft Defender 防病毒自动安装在运行以下版本的 Windows：

- Windows 10或更高版本
- Windows Server 2022
- Windows Server 2019
- Windows Server 版本 1803 或更高版本
- Windows Server 2016

当使用另一个非 Microsoft 防病毒/反恶意软件解决方案时，会发生什么情况？ 能否将Microsoft Defender 防病毒防病毒产品一起运行？ 答案取决于多种因素，例如操作系统以及是否将 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) 与防病毒保护一起使用。

本文介绍了在具有或没有 Defender for Endpoint 的情况下Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案会发生什么情况。

> [!IMPORTANT]
> Microsoft Defender 防病毒仅在运行 Windows 10 和 11、Windows Server 2022、Windows Server 2019、Windows Server 版本 1803 或更高版本、Windows Server 2016 和Windows Server 2012 R2。
>
> 在Windows 8.1中，企业级终结点防病毒保护作为 System Center Endpoint Protection 提供，它[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))通过 Microsoft Endpoint Configuration Manager。
>
> Windows Defender为 Windows 8.1 上的消费者设备[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供，Windows Defender不提供企业级管理。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>没有适用于终结点的 Defender 的防病毒保护

本部分介绍未载入Microsoft Defender 防病毒 Defender for Endpoint 的终结点上的非 Microsoft 防病毒/反恶意软件产品会发生什么情况。 下表总结了预期内容：

<br/><br/>

|Windows 版本|主防病毒/反恶意软件解决方案|Microsoft Defender 防病毒状态|
|---|---|---|
|Windows 10 <p> Windows 11|Microsoft Defender 防病毒|主动模式|
|Windows 10 <p> Windows 11|非 Microsoft 防病毒/反恶意软件解决方案|禁用模式 (自动) |
|Windows Server 2022 <p> Windows Server 2019<p> Windows Server 版本 1803 或更高版本 <p> Windows Server 2016 |Microsoft Defender 防病毒|主动模式|
|Windows Server 2022<p>Windows Server 2019<p>Windows Server 版本 1803 或更高版本 <p> Windows Server 2016 <p>  |非 Microsoft 防病毒/反恶意软件解决方案|禁用 (手动设置) <sup>[[1](#fn1)]</sup>|

 (<a id="fn1">1</a>) 在 Windows 服务器上，如果运行的是非 Microsoft 防病毒产品，可以使用组策略禁用 Microsoft Defender 防病毒，或者使用[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)注册表项禁用 Microsoft Defender 防病毒。 若要使用注册表项，请导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` ，并设置或创建名为 的 DWORD 项 `DisableAntiSpyware` 。 将其值设置为 (将注册表项的值设置为 true) ，然后选择 `1` **十** 六进制作为其基础。

> [!TIP]
> 在Windows Server 2016上，*你可能会看到Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒。*

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案

下表汇总了当非 Microsoft 防病毒/反恶意软件解决方案Microsoft Defender 防病毒或没有 Microsoft Defender for Endpoint 时，使用非 Microsoft 防病毒/反恶意软件解决方案时会发生什么情况。 

| Windows 版本   | 防病毒/反恶意软件解决方案  | 已载入 <br/> 适用于终结点的 Defender？ | Microsoft Defender 防病毒状态     |
|------|------|-------|-------|
| Windows 10 <p> Windows 11| Microsoft Defender 防病毒 | 是  | 主动模式 | 
| Windows 10 <p> Windows 11 | Microsoft Defender 防病毒 | 否   | 主动模式 |
| Windows 10 <p> Windows 11  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | 被动模式 (自动)  |
| Windows 10 <p> Windows 11  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否   | 禁用模式 (自动)     |
| Windows Server 2019 <p>Windows Server 版本 1803 或更高版本  | Microsoft Defender 防病毒  | 是 |         主动模式  |
| Windows Server 2019 <p> Windows Server 版本 1803 或更高版本   | Microsoft Defender 防病毒 | 否  | 主动模式 |
| Windows Server 2019 <p> Windows Server 版本 1803 或更高版本  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | Microsoft Defender 防病毒必须设置为被动模式， (手动) <sup> [[2](#fn2)]<sup>  | 
| Windows Server 2019 <p> Windows Server 版本 1803 或更高版本  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否  | Microsoft Defender 防病毒手动 (禁用) <sup> [[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br><br> Windows Server 2012 R2   | Microsoft Defender 防病毒 | 是 | 主动模式 |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft Defender 防病毒 | 否 | 主动模式 |
| Windows Server 2016 <br><br> Windows Server 2012 R2  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是 | Microsoft Defender 防病毒必须设置为被动模式， (手动) <sup> [[2](#fn2)]<sup> |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否 | Microsoft Defender 防病毒手动 (禁用) <sup> [[3](#fn3)]<sup> |

 (<a id="fn2">2</a>) 在 Windows Server 2019、Windows Server 版本 1803 或更高版本、Windows Server 2016 或 Windows Server 2012 R2 上，当您安装非 Microsoft 防病毒时，Microsoft Defender 防病毒 不会自动进入被动模式product。 在这种情况下，将Microsoft Defender 防病毒设置为被动模式，以防止在服务器上安装多个防病毒产品导致的问题。 可以使用 PowerShell Microsoft Defender 防病毒组策略或注册表项将用户设置为被动模式。 

  可以通过设置Microsoft Defender 防病毒注册表项，将用户设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

 > [!NOTE]
 > 若要使被动模式在运行 Windows Server 2016 和 Windows Server 2012 R2 的终结点上运行，这些终结点必须使用 Onboard Windows servers 中所述的新式统[一解决方案](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)载入。 

 (<a id="fn3">3</a>) 在 Windows Server 2016 或 Windows Server 2012 R2 上，如果你使用的是非 Microsoft 防病毒产品，并且该终结点未载入到 Microsoft Defender for Endpoint，则禁用/卸载Microsoft Defender 防病毒 手动防止在服务器上安装多个防病毒产品导致的问题。

> [!TIP]
> 在Windows Server 2016上，*你可能会看到Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒。*

> [!IMPORTANT]
> Microsoft Defender 防病毒仅在运行 Windows 10 和 11、Windows Server 2022、Windows Server 2019、Windows Server 版本 1803 或更高版本、Windows Server 2016 和Windows Server 2012 R2。
>
> 在Windows 8.1中，企业级终结点防病毒保护作为 System Center Endpoint Protection 提供，它[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))通过 Microsoft Endpoint Configuration Manager。
>
> Windows Defender为 Windows 8.1 上的消费者设备[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供，Windows Defender不提供企业级管理。

Defender for Endpoint 包括进一步扩展安装在终结点上的防病毒保护的功能。 通过同时运行其他Microsoft Defender 防病毒，您可以获益。

例如，在阻止[模式下 (EDR) ](edr-in-block-mode.md)终结点检测和响应功能可提供对恶意项目的更多保护，即使Microsoft Defender 防病毒不是主要的防病毒产品。 这些功能要求Microsoft Defender 防病毒被动模式或主动模式安装并运行这些功能。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>要求Microsoft Defender 防病毒被动模式下运行

为了使Microsoft Defender 防病毒被动模式下运行，终结点必须满足以下要求：

- 操作系统：Windows 10或更高版本;Windows Server 2022、Windows Server 2019 或 Windows Server 版本 1803 或更高版本
- Microsoft Defender 防病毒必须安装
- 必须安装另一个非 Microsoft 防病毒/反恶意软件产品，并用作主要的防病毒解决方案
- 终结点必须载入到适用于终结点的 Defender

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>更改Microsoft Defender 防病毒 Defender for Endpoint 功能的影响

Defender for Endpoint 影响Microsoft Defender 防病毒在被动模式下运行。 Microsoft Defender 防病毒影响 Defender for Endpoint 中的某些功能。 例如，实时保护在 Microsoft Defender 防病毒 处于主动或被动模式时有效，Microsoft Defender 防病毒或卸载时则不能。

本节中的表总结了根据 Microsoft Defender 防病毒 处于主动模式、被动模式还是已禁用/卸载状态而主动运行的特性和功能。

> [!IMPORTANT]
> 下表设计为仅供参考。 如果你在被动模式下使用 Microsoft Defender 防病毒 或在阻止模式下使用[EDR，](edr-in-block-mode.md)请不要关闭功能，例如实时保护、云提供的保护或有限定期扫描，这将在后台检测并修正在泄露后检测到的恶意项目。

<br/><br/>

 | 保护 | Microsoft Defender 防病毒 <br/> (*活动模式)* | Microsoft Defender 防病毒 <br/> (*被动模式*)  | Microsoft Defender 防病毒 <br/> (*禁用或卸载)* | [块模式下的 EDR](edr-in-block-mode.md) | 
 |---|---|---|---|---| 
 | [实时保护](configure-real-time-protection-microsoft-defender-antivirus.md) | 是 | 否 <sup>[[4](#fn4)]</sup> | 否 | 否 | 
 | [云端保护](enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 否  | 否 | 否 | 
 | [网络保护](network-protection.md)  | 是 | 否 | 否 | 否 | 
 | [攻击面减少规则](attack-surface-reduction.md)  | 是 | 否 | 否  | 否 | 
 | [有限定期扫描可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 是 | 否 | 
 | [文件扫描和检测信息](review-scan-results-microsoft-defender-antivirus.md) | 是 | 是 | 否 | 是 | 
 | [威胁修正](configure-remediation-microsoft-defender-antivirus.md) | 是 | 请参阅注释 <sup>[[5](#fn5)]</sup> | 否 | 是 | 
 | [安全智能更新](manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 否 | 是 | 

 (<a id="fn4">4</a>) 通常，当 Microsoft Defender 防病毒 处于被动模式时，实时保护不会提供任何阻止或强制，即使处于启用状态且处于被动模式。

 (<a id="fn5">5</a>) 当Microsoft Defender 防病毒处于被动模式时，威胁修正功能仅在计划扫描或按需扫描期间处于活动状态。

> [!NOTE]
> [Microsoft 365终结点数据丢失](/microsoft-365/compliance/endpoint-dlp-learn-about)防护在终结点处于主动或被动Microsoft Defender 防病毒时可继续正常运行。

## <a name="important-notes"></a>重要说明

- 不要禁用、停止或修改由 Microsoft Defender 防病毒、Defender for Endpoint 或 Windows 安全中心 使用的任何关联服务。 此建议包括 wscsvc、SecurityHealthService、MsSense、Sense、WinDefend 或 *MsMpEng* 服务和进程。     手动修改这些服务可能会导致设备严重不稳定，并且可能会使网络易受攻击。 在使用非 Microsoft 防病毒解决方案及其信息在应用中显示的方式时，禁用、停止或修改这些服务Windows 安全中心[问题](microsoft-defender-security-center-antivirus.md)。

- 在 Defender for Endpoint 中，EDR以阻止模式打开，即使Microsoft Defender 防病毒不是你的主要防病毒解决方案。 EDR阻止模式时检测并修正在设备中发现的恶意项目， (泄露后) 。 若要了解更多信息，请参阅EDR[阻止模式。](edr-in-block-mode.md)

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>如何确认Microsoft Defender 防病毒

可以使用几种方法之一来确认Microsoft Defender 防病毒状态，如下表所述：

<br/><br/>

 | 方法 | Procedure | 
 |---|---| 
 | Windows 安全中心应用 |  1. 在 Windows设备上，打开Windows 安全中心应用。<br/>2. 选择 **病毒&威胁防护。**<br/>3. **Who保护我？选择** 管理 **提供程序**。<br/>4. 在"**安全提供程序"** 页上的"**防病毒**"下 **，Microsoft Defender 防病毒"打开"。** | 
 | 任务管理器 |  1. 在Windows上，打开"任务管理器"应用。<br/>2. 选择" **详细信息"** 选项卡。<br/>3. 在 **MsMpEng.exe** 查找列表。 | 
 | Windows PowerShell <br/><br/>  (确认Microsoft Defender 防病毒运行)  |  1.在Windows上，打开Windows PowerShell。 <br/>2. 运行以下 PowerShell cmdlet：。 `Get-Process`<br/>3. 查看结果。 如果启用 **MsMpEng.exe，Microsoft Defender 防病毒** 看到此参数。 | 
 | Windows PowerShell <br/><br/>  (确认防病毒保护已就位)  |  可以使用 [Get-MpComputerStatus PowerShell cmdlet](/powershell/module/defender/get-mpcomputerstatus)。 <br/><br/>1.在Windows上，打开Windows PowerShell。<br/>2. 运行以下 PowerShell cmdlet：。 `Get-MpComputerStatus | select AMRunningMode`<br/>3. 查看结果。 如果在 **终结点上启用了**"常规 **"或** Microsoft Defender 防病毒，则应该会看到"正常"或"被动"。  | 
 | 命令提示符 |  1. 在Windows上，打开命令提示符。<br/>2. 键入 `sc query windefend` ，然后按 Enter。<br/>3. 查看结果，确认Microsoft Defender 防病毒处于被动模式。  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>有关状态Microsoft Defender 防病毒详细信息

本节中的表介绍了你可能在管理时看到的各种Microsoft Defender 防病毒。

<br/><br/>

 |  状态  |  发生的情况  | 
 |---|---| 
 |  主动模式  |  在活动模式下，Microsoft Defender 防病毒用作计算机上防病毒应用。 设置配置管理器、组策略、Microsoft Intune或其他管理产品配置的策略。 将扫描文件、修正威胁，并且检测信息会报告在配置工具 (如配置管理器或终结点本身上的 Microsoft Defender 防病毒 应用) 。  | 
 |  被动模式  |  在被动模式下，Microsoft Defender 防病毒不会用作防病毒应用，威胁 *不会* 由 Microsoft Defender 防病毒。 但是，威胁可通过终结点[检测和响应 (EDR) 阻止模式](edr-in-block-mode.md)进行修正。 <br/><br/> 将扫描文件，并针对与 Defender for Endpoint 服务共享的威胁检测提供报告。 你可能会在 Defender for [Cloud](microsoft-defender-security-center.md)中看到警报，Microsoft Defender 防病毒作为源，即使Microsoft Defender 防病毒处于被动模式。 <br/><br/> 当 Microsoft Defender 防病毒 处于被动模式时，你仍可以管理[Microsoft Defender 防病毒](manage-updates-baselines-microsoft-defender-antivirus.md)的更新;但是，如果你的设备具有提供实时恶意软件防护的非 Microsoft 防病毒产品，你无法将 Microsoft Defender 防病毒 移动到活动模式. <br/><br/> 为获得最佳安全分层防御和检测，请确保获取防病毒和反恶意软件更新，即使 Microsoft Defender 防病毒处于被动模式。 请参阅[管理Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。 <br/><br/> **注意**：被动模式在用户上Windows Server 2016。  | 
 |  已禁用 <br/><br/> 或 <br/><br/> 已卸载  |  禁用或卸载时，Microsoft Defender 防病毒不用作防病毒应用。 不扫描文件，不修正威胁。 <br/><br/> 通常不建议禁用Microsoft Defender 防病毒卸载应用程序;如果可能，Microsoft Defender 防病毒非 Microsoft 反恶意软件/防病毒解决方案，请将其保持被动模式。 <br/><br/> 如果自动Microsoft Defender 防病毒，当非 Microsoft 防病毒/反恶意软件产品过期或停止提供实时保护免受病毒、恶意软件或其他威胁时，可自动重新启用它。 自动重新启用Microsoft Defender 防病毒有助于确保在终结点上维护防病毒保护。 <br/><br/> 如果你使用的是[非](limited-periodic-scanning-microsoft-defender-antivirus.md)Microsoft 防病毒应用，则你可能还使用有限定期扫描Microsoft Defender 防病毒引擎定期检查威胁。  | 


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)
