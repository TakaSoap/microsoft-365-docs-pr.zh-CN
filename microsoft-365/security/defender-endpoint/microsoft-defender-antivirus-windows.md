---
title: Windows 10 中的 Microsoft Defender 防病毒
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒、内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒、Windows Defender、反恶意软件、SCEP、System Center 端点保护、System Center Configuration Manager、病毒、恶意软件、威胁、检测、保护、安全
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 465a2775bdec232e248cb6d14a96b86770b64e5c
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121634"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Windows 10 中的 Microsoft Defender 防病毒

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

Microsoft Defender 防病毒在 Windows 10 和 Windows 11 以及 Windows Server 的多个版本中提供。

Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 中下一代保护的主要组件。 此保护结合了机器学习、大数据分析、深度威胁抵御研究和 Microsoft 云基础结构来保护组织中的设备（或终结点）。 Microsoft Defender 防病毒内置于 Windows 中，与 Microsoft Defender for Endpoint 一起在设备上和云中提供保护。

## <a name="compatibility-with-other-antivirus-products"></a>与其他防病毒软件产品的兼容性

如果正在设备上使用非 Microsoft 防病毒/反恶意软件产品，可能可以在使用非 Microsoft 防病毒软件解决方案的同时以被动模式运行 Microsoft Defender 防病毒。 具体取决于所使用的操作系统，以及设备是否已加入 Defender for Endpoint。 要了解详细信息，请参阅 [Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)。

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>比较主动模式、被动模式和已禁用模式

下表介绍了 Microsoft Defender 防病毒处于主动模式、被动模式或已禁用模式下应发生的情况。

<br/><br/>

| 模式 | 发生的情况 |
|---|---|
| 主动模式 | 在主动模式下，Microsoft Defender 防病毒用作设备上的主防病毒应用。 将扫描文件，修正威胁，并将检测到的威胁列在组织的安全报告中和 Windows 安全中心应用中。 |
| 被动模式 | 在被动模式下，不将 Microsoft Defender 防病毒用作设备上的主防病毒应用。 将扫描文件，并报告检测到的威胁，但 Microsoft Defender 防病毒不会修正威胁。 <br/><br/> **重要**： Microsoft Defender 防病毒只能在载入到 Microsoft Defender for Endpoint 的终结点上以被动模式运行。 请参阅 [在被动模式](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)中运行Microsoft Defender 防病毒的要求。 |
| 已禁用或卸载 | 在已禁用或卸载时，不使用 Microsoft Defender 防病毒。 不会扫描文件，并且不会修正威胁。 通常，我们不建议禁用或卸载 Microsoft Defender 防病毒。 |

要了解详细信息，请参阅 [Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)。

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>检查设备上的 Microsoft Defender 防病毒状态

要检查设备上的 Microsoft Defender 防病毒状态，可以使用几种方法之一，例如 Windows 安全中心应用或 Windows PowerShell。

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>使用 Windows 安全中心应用检查 Microsoft Defender 防病毒状态

1. 在 Windows 设备上，选择“开始”菜单，然后开始键入 `Security`。 然后在结果中打开 Windows 安全中心应用。

2. 选择“**病毒和威胁防护**”。

3. 在“**病毒和威胁防护设置**”下选择“**管理设置**”。

设置页面上将显示防病毒/反恶意软件解决方案的名称。

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>使用 PowerShell 检查 Microsoft Defender 防病毒状态

1. 选择“开始”菜单，然后开始键入 `PowerShell`。 然后在结果中打开 Windows PowerShell。

2. 类型 `Get-MpComputerStatus`。

3. 在结果列表中，查看 **AMRunningMode** 行。

   - **正常** 表示 Microsoft Defender 防病毒在主动模式下运行。

   - **被动模式** 表示 Microsoft Defender 防病毒正在运行，但不是设备上的主要防病毒/反恶意软件产品。 被动模式仅适用于已载入 Microsoft Defender for Endpoint 且满足特定要求的设备。 若要了解详细信息，请参阅 [Microsoft Defender 防病毒在被动模式](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode)运行的要求。

   - **EDR 阻止模式** 意味着Microsoft Defender 防病毒正在运行，并且在阻止模式下 [终结点检测和响应 （EDR），](edr-in-block-mode.md)（Microsoft Defender for Endpoint 中的功能）已启用。

   - **SxS 被动模式** 意味着Microsoft Defender 防病毒与其他防病毒/反恶意软件产品一起运行，并且 [使用有限定期扫描](limited-periodic-scanning-microsoft-defender-antivirus.md)。

> [!TIP]
> 要了解 Get-MpComputerStatus PowerShell cmdlet 的详细信息，请参阅参考文章 [get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

## <a name="get-your-antivirusantimalware-platform-updates"></a>获取防病毒/反恶意软件平台更新

请务必确保 Microsoft Defender 防病毒或任何防病毒/反恶意软件解决方案保持最新。 Microsoft 定期发布更新，以帮助确保你的设备具有最新技术来防范新的恶意软件和攻击技术。 要了解详细信息，请参阅 [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>另请参阅

- [Microsoft Defender 防病毒管理和配置](configuration-management-reference-microsoft-defender-antivirus.md)
- [评估 Microsoft Defender 防病毒保护](evaluate-microsoft-defender-antivirus.md)
