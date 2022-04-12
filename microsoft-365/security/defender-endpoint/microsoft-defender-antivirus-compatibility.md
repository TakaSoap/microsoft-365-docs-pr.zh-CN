---
title: Microsoft Defender 防病毒与其他安全产品的兼容性
description: 了解与其他安全产品和操作系统Microsoft Defender 防病毒。
keywords: windows defender， defender for endpoint， next-generation， 防病毒， 兼容性， 被动模式
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
ms.date: 03/16/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: d7e2acf9c0935dcabcace974db009f3c13c6e2ed
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789351"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender 防病毒与其他安全产品的兼容性

**适用于：**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**平台**
- Windows

[!include[Prerelease information](../../includes/prerelease.md)]

Microsoft Defender 防病毒自动安装在运行以下Windows版本的终结点上：

- Windows 10或更高版本
- Windows Server 2022
- Windows Server 2019
- Windows服务器、版本 1803 或更高版本
- Windows Server 2016

使用另一个非 Microsoft 防病毒/反恶意软件解决方案时会发生什么情况？ 是否可以与其他防病毒产品一起运行Microsoft Defender 防病毒？ 答案取决于多种因素，例如操作系统以及是否将[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)与防病毒保护结合使用。

本文介绍Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案（无论是否具有 Defender for Endpoint）发生的情况。

> [!IMPORTANT]
> - Microsoft Defender 防病毒在运行 Windows 10 和 11、Windows Server 2022、Windows Server 2019、Windows 服务器、版本 1803 或更高版本以及Windows Server 2016的设备上可用。 
> - 使用[新式统一解决方案](/microsoft-365/security/defender-endpoint/configure-server-endpoints)加入时，Microsoft Defender 防病毒也可在 Windows Server 2012 R2 上使用。
> - Windows 8.1，企业级终结点防病毒保护作为 [System Center Endpoint Protection] (/previous-versions/system-center/system-center-2012-R2/hh508760 (v=technet.10) 提供，该) 通过Microsoft Endpoint Configuration Manager。
> - Windows 8.1[上也为使用者设备提供Windows Defender](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)，尽管Windows Defender不提供企业级管理。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>没有 Defender for Endpoint 的防病毒保护

本部分介绍在未载入到 Defender for Endpoint 的终结点上将Microsoft Defender 防病毒与非 Microsoft 防病毒/反恶意软件产品一起使用时会发生什么情况。 

> [!NOTE]
> 通常，Microsoft Defender 防病毒不会在未载入到 Defender for Endpoint 的设备上以被动模式运行。

下表汇总了预期的内容：

|Windows 版本|主要防病毒/反恶意软件解决方案|Microsoft Defender 防病毒状态|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Microsoft Defender 防病毒|主动模式|
|Windows 10 <br/> Windows 11|非 Microsoft 防病毒/反恶意软件解决方案|禁用模式 (自动) |
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows服务器、版本 1803 或更高版本 <br/> Windows Server 2016 |Microsoft Defender 防病毒|主动模式|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows服务器、版本 1803 或更高版本 <br/> Windows Server 2016  |非 Microsoft 防病毒/反恶意软件解决方案|禁用 (手动设置) <sup>[[1](#fn1)]</sup>|

 (<a id="fn1">1</a>) 在 Windows 服务器上运行非 Microsoft 防病毒产品时，可以卸载Microsoft Defender 防病毒以防止冲突。 如果设备已载入到Microsoft Defender for Endpoint，则可以在被动模式下使用Microsoft Defender 防病毒 (请参阅下) 。

> [!TIP]
> 在Windows Server 2016，你可能会看到 *Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒*。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender 防病毒和非 Microsoft 防病毒/反恶意软件解决方案

> [!NOTE]
> 通常，Microsoft Defender 防病毒只能在载入到 Defender for Endpoint 的终结点上设置为被动模式。

Microsoft Defender 防病毒是在主动模式、被动模式下运行还是禁用取决于多种因素，例如：

- 终结点上安装了哪个版本的Windows
- Microsoft Defender 防病毒是否是终结点上的主要防病毒/反恶意软件解决方案
- 终结点是否载入到 Defender for Endpoint

下表总结了多个方案中的Microsoft Defender 防病毒状态。 

| Windows 版本   | 防病毒/反恶意软件解决方案  | 载入到 <br/> Defender for Endpoint？ | Microsoft Defender 防病毒状态     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Microsoft Defender 防病毒 | 是  | 主动模式 | 
| Windows 10 <br/> Windows 11 | Microsoft Defender 防病毒 | 否   | 主动模式 |
| Windows 10 <br/> Windows 11  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | 被动模式 (自动)  |
| Windows 10 <br/> Windows 11  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否   | 禁用模式 (自动)     |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows服务器版本 1803 或更高版本  | Microsoft Defender 防病毒  | 是 |         主动模式  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows服务器版本 1803 或更高版本   | Microsoft Defender 防病毒 | 否  | 主动模式 |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows服务器版本 1803 或更高版本  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是  | Microsoft Defender 防病毒必须设置为被动模式 (手动) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows服务器版本 1803 或更高版本  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否  | 必须手动<sup> (Microsoft Defender 防病毒) [[3](#fn3)] 禁用<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Microsoft Defender 防病毒 | 是 | 主动模式 |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft Defender 防病毒 | 否 | 主动模式 |
| Windows Server 2016 <br/> Windows Server 2012 R2  | 非 Microsoft 防病毒/反恶意软件解决方案 | 是 | Microsoft Defender 防病毒必须设置为被动模式 (手动) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | 非 Microsoft 防病毒/反恶意软件解决方案 | 否 | 必须手动<sup> (Microsoft Defender 防病毒) [[3](#fn3)] 禁用<sup> |

 (<a id="fn2">2</a>) 在 Windows Server 2019、Windows Server、版本 1803 或更高版本、Windows Server 2016或 Windows Server 2012 R2 上，安装非 Microsoft 防病毒软件时，Microsoft Defender 防病毒不会自动进入被动模式产品。 在这些情况下，请将Microsoft Defender 防病毒设置为被动模式，以防止服务器上安装了多个防病毒产品导致的问题。 可以使用 PowerShell、组策略 或注册表项将Microsoft Defender 防病毒设置为被动模式。 

  可以通过设置以下注册表项将Microsoft Defender 防病毒设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

 > [!NOTE]
 > 若要使被动模式适用于运行Windows Server 2016和Windows Server 2012 R2 的终结点，这些终结点必须与[载入Windows服务器](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)中描述的新式统一解决方案一起载入。 

 (<a id="fn3">3</a>) Windows Server 2016、Windows Server 2012 R2、Windows Server 版本 1803 或更高版本、Windows Server 2019 和 Windows Server 2022（如果在 *未* 载入到的终结点上使用非 Microsoft 防病毒产品）Microsoft Defender for Endpoint，手动禁用/卸载Microsoft Defender 防病毒，以防止在服务器上安装多个防病毒产品导致的问题。

> [!TIP]
> 在Windows Server 2016，你可能会看到 *Windows Defender 防病毒* 而不是 *Microsoft Defender 防病毒*。

> [!IMPORTANT]
> Microsoft Defender 防病毒仅适用于运行 Windows 10 和 11、Windows Server 2022、Windows Server 2019、Windows 服务器、版本 1803 或更高版本、Windows Server 2016 和Windows Server 2012 R2。
>
> 在Windows 8.1中，企业级终结点防病毒保护作为[System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))提供，通过Microsoft Endpoint Configuration Manager进行管理。
>
> Windows 8.1[上也为使用者设备提供Windows Defender](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)，尽管Windows Defender不提供企业级管理。

Defender for Endpoint 包括进一步扩展在终结点上安装的防病毒保护的功能。 可以从与其他防病毒解决方案一起运行Microsoft Defender 防病毒中获益。

例如，即使Microsoft Defender 防病毒不是主要防病毒产品，[在阻止模式下的终结点检测和响应](edr-in-block-mode.md) (EDR) 也可为恶意项目提供额外的保护。 此类功能需要在被动模式或主动模式下安装和运行Microsoft Defender 防病毒。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>在被动模式下运行Microsoft Defender 防病毒的要求

若要使Microsoft Defender 防病毒在被动模式下运行，终结点必须满足以下要求：

- 操作系统：Windows 10或更新;Windows Server 2022、Windows Server 2019 或 Windows Server 版本 1803 或更高版本
- 必须安装Microsoft Defender 防病毒
- 必须安装另一个非 Microsoft 防病毒/反恶意软件产品并将其用作主要防病毒解决方案
- 终结点必须载入到 Defender for Endpoint

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender 防病毒如何影响 Defender for Endpoint 功能

Defender for Endpoint 会影响Microsoft Defender 防病毒是否可以在被动模式下运行。 Microsoft Defender 防病毒也会影响 Defender for Endpoint 中的某些功能。 例如，当Microsoft Defender 防病毒处于主动或被动模式，但在禁用或卸载Microsoft Defender 防病毒时，实时保护不起作用。

本部分中的表根据Microsoft Defender 防病毒处于主动模式、被动模式还是已禁用/卸载，汇总了主动工作或不工作的功能。

> [!IMPORTANT]
> 下表设计为仅信息。 如果在被动模式下使用Microsoft Defender 防病毒，或者在 [阻止模式](edr-in-block-mode.md)下使用EDR，则 **不要关闭** 实时保护、云提供的保护或有限的定期扫描等功能，这些功能在后台工作，用于检测和修正在违规后检测到的恶意项目。

 | 保护 | Microsoft Defender 防病毒 <br/> (*活动模式*)  | Microsoft Defender 防病毒 <br/> (*被动模式*)  | Microsoft Defender 防病毒 <br/> (*已禁用或卸载*)  | [块模式下的 EDR](edr-in-block-mode.md) | 
 |:---|:---|:---|:---|:---| 
 | [实时保护](configure-real-time-protection-microsoft-defender-antivirus.md) | 是 | 请参阅注释 <sup>[[4](#fn4)]</sup> | 否 | 否 | 
 | [云传递的保护](enable-cloud-protection-microsoft-defender-antivirus.md) | 是 | 否  | 否 | 否 | 
 | [网络保护功能](network-protection.md)  | 是 | 否 | 否 | 否 | 
 | [攻击面减少规则](attack-surface-reduction.md)  | 是 | 否 | 否  | 否 | 
 | [有限的定期扫描可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | 否 | 否 | 是 | 否 | 
 | [文件扫描和检测信息](review-scan-results-microsoft-defender-antivirus.md) | 是 | 是<sup>[[5](#fn5)]</sup> | 否 | 是 | 
 | [威胁修正](configure-remediation-microsoft-defender-antivirus.md) | 是 | 请参阅注释 <sup>[[6](#fn6)]</sup> | 否 | 是 | 
 | [安全智能更新](manage-updates-baselines-microsoft-defender-antivirus.md) | 是 | 是 | 否 | 是 | 

 (<a id="fn4">4</a>) 一般情况下，当Microsoft Defender 防病毒处于被动模式时，实时保护不会提供任何阻止或强制执行，即使它已启用且处于被动模式。

 (<a id="fn5">5</a>) 当Microsoft Defender 防病毒处于被动模式时，不会计划扫描。

 (<a id="fn6">6</a>) 当Microsoft Defender 防病毒处于被动模式时，它不会修正威胁。 但是，可以在[阻止模式下通过终结点检测和响应 (EDR) ](edr-in-block-mode.md)修正威胁。 在这种情况下，你可能会看到将Microsoft Defender 防病毒显示为源的警报，即使Microsoft Defender 防病毒处于被动模式。

> [!NOTE]
> Microsoft 365当Microsoft Defender 防病毒处于主动或被动模式时，[终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)继续正常运行。

## <a name="important-notes"></a>重要说明

- 请勿禁用、停止或修改Microsoft Defender 防病毒、Defender for Endpoint 或Windows 安全中心应用使用的任何关联服务。 此建议包括 *wscsvc*、 *SecurityHealthService*、 *MsSense*、 *Sense*、 *WinDefend* 或 *MsMpEng* 服务和流程。 手动修改这些服务可能会导致设备严重不稳定，并可能使网络易受攻击。 禁用、停止或修改这些服务也可能导致使用非 Microsoft 防病毒解决方案时出现问题，以及它们的信息如何显示在[Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)中。

- 在 Defender for Endpoint 中，打开阻止模式下的EDR，即使Microsoft Defender 防病毒不是你的主要防病毒解决方案。 EDR在阻止模式下检测和修正在设备上找到的恶意项目 (违规后) 。 若要了解详细信息，请参阅[阻止模式下的EDR](edr-in-block-mode.md)。

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>如何确认Microsoft Defender 防病毒的状态

可以使用多种方法之一来确认Microsoft Defender 防病毒状态，如下表所述：

 | 方法 | Procedure | 
 |:---|:---| 
 | Windows 安全中心应用 |  1. 在Windows设备上，打开Windows 安全中心应用。<br/>2. 选择 **病毒&威胁防护**。<br/>3. **在Who保护我的情况下？** 选择 **“管理提供程序**”。<br/>4. 在 **“安全提供程序**”页上，在 **“防病毒**”下，应会看到 **Microsoft Defender 防病毒已打开**。 | 
 | 任务管理器 |  1. 在Windows设备上，打开 Task Manager 应用。<br/>2.选择 **“详细信息** ”选项卡。<br/>3. 在列表中查找 **MsMpEng.exe** 。 | 
 | Windows PowerShell <br/>  (确认Microsoft Defender 防病毒正在运行)  |  1. 在Windows设备上，打开Windows PowerShell。 <br/>2. 运行以下 PowerShell cmdlet： `Get-Process`.<br/>3. 查看结果。 如果启用 **了Microsoft Defender 防病毒，** 应会看到MsMpEng.exe。 | 
 | Windows PowerShell <br/> (若要确认是否已实施防病毒保护)  |  可以使用 [Get-MpComputerStatus PowerShell cmdlet](/powershell/module/defender/get-mpcomputerstatus)。<br/>1. 在Windows设备上，打开Windows PowerShell。<br/>2. 运行以下 PowerShell cmdlet：<br/> \|Get-MpComputerStatus选择 AMRunningMode <br/>3. 查看结果。 如果在终结点上启用了Microsoft Defender 防病毒，则应会看到“**正常**”或“**被动**”。  | 
 | 命令提示符 |  1. 在Windows设备上，打开命令提示符。<br/>2. 键 `sc query windefend`入，然后按 Enter。<br/>3. 查看结果，确认Microsoft Defender 防病毒在被动模式下运行。  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>有关Microsoft Defender 防病毒状态的更多详细信息

本部分中的表介绍了Microsoft Defender 防病毒可能看到的各种状态。

 |  状态  |  发生的情况  | 
 |:---|:---| 
 |  主动模式  |  在活动模式下，Microsoft Defender 防病毒用作计算机上的防病毒应用。 将应用使用Configuration Manager、组策略、Microsoft Intune或其他管理产品配置的设置。 将扫描文件，修正威胁，并在配置工具中报告检测信息， (，例如终结点上的Configuration Manager或Microsoft Defender 防病毒应用) 。  | 
 |  被动模式  |  在被动模式下，Microsoft Defender 防病毒不用作防病毒应用，Microsoft Defender 防病毒 *不会* 修正威胁。 但是，[可以在阻止模式下通过终结点检测和响应 (EDR) ](edr-in-block-mode.md)修正威胁。 <br/><br/> 文件由EDR扫描，并提供与 Defender for Endpoint 服务共享的威胁检测报告。 你可能会看到将Microsoft Defender 防病毒显示为源的警报，即使Microsoft Defender 防病毒处于被动模式。 <br/><br/> 当Microsoft Defender 防病毒处于被动模式时，仍可以[管理Microsoft Defender 防病毒的更新](manage-updates-baselines-microsoft-defender-antivirus.md);但是，如果设备具有提供恶意软件实时保护的非 Microsoft 防病毒产品，则无法将Microsoft Defender 防病毒移动到主动模式. <br/><br/> 为了获得最佳的安全分层防御和检测效能，请确保获取防病毒和反恶意软件更新，即使Microsoft Defender 防病毒处于被动模式下运行。 请参阅[“管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。 <br/><br/> 请注意，仅在使用[新式统一解决方案](/microsoft-365/security/defender-endpoint/configure-server-endpoints)载入计算机时，Windows Server 2012 R2 & 2016 支持被动模式。  | 
 |  Disabled <br/><br/> 或 <br/><br/> 卸载  |  禁用或卸载时，Microsoft Defender 防病毒不用作防病毒应用。 不会扫描文件，也不会修正威胁。 <br/><br/> 通常不建议禁用或卸载Microsoft Defender 防病毒;如果可能，如果使用非 Microsoft 反恶意软件/防病毒解决方案，请将Microsoft Defender 防病毒保持被动模式。 <br/><br/> 如果自动禁用Microsoft Defender 防病毒，则在非 Microsoft 防病毒/反恶意软件产品过期或停止提供病毒、恶意软件或其他威胁的实时保护时，可以自动重新启用它。 自动重新启用Microsoft Defender 防病毒有助于确保在终结点上维护防病毒保护。 <br/><br/> 还可使用[有限的定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)，该扫描可与Microsoft Defender 防病毒引擎配合使用，以便在使用非 Microsoft 防病毒应用时定期检查威胁。  | 

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

- [Windows客户端上的Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上的 Microsoft Defender 防病毒软件](microsoft-defender-antivirus-on-windows-server.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [了解 Microsoft 365 终结点数据丢失防护](/microsoft-365/compliance/endpoint-dlp-learn-about)
