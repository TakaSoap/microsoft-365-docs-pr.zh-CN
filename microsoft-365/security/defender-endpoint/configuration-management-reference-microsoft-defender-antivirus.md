---
title: 管理业务中的Microsoft Defender 防病毒
description: 了解如何使用 组策略、Configuration Manager、PowerShell、WMI、Intune 和命令行来管理 Microsoft Defender AV
keywords: 组策略， gpo， 配置管理器， sccm， scep， powershell， wmi， intune， defender， 防病毒， 防恶意软件， 安全性， 保护
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 76f6f1cda9b2def0c18be8c368da15645994eece
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787965"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>管理业务中的Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用以下工具管理和配置Microsoft Defender 防病毒：

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (现在是Microsoft Endpoint Manager) 的一部分
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (现在是Microsoft Endpoint Manager) 的一部分
- [组策略](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft 恶意软件保护命令行实用工具](./command-line-arguments-microsoft-defender-antivirus.md) (称为 *mpcmdrun.exe* 实用工具

以下文章提供了有关使用这些工具管理和配置Microsoft Defender 防病毒的更多信息、链接和资源。

|文章|说明|
|:---|:---|
|[使用Microsoft Intune和Microsoft Endpoint Configuration Manager管理Microsoft Defender 防病毒](use-intune-config-manager-microsoft-defender-antivirus.md)|有关使用Intune和Configuration Manager部署、管理、报告和配置Microsoft Defender 防病毒|
|[使用组策略设置管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)|ADMX 模板中所有组策略设置的列表|
|[使用 PowerShell cmdlet 管理Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md)|有关使用 PowerShell cmdlet 管理Microsoft Defender 防病毒的说明，以及指向所有 cmdlet 和允许参数文档的链接|
|[使用 Windows 管理检测 (WMI) 管理Microsoft Defender 防病毒](use-wmi-microsoft-defender-antivirus.md)|有关使用 WMI 管理Microsoft Defender 防病毒的说明，以及 WMIv2 API 文档的链接 (包括所有类、方法和属性) |
|[使用MpCmdRun.exe命令行工具管理Microsoft Defender 防病毒](command-line-arguments-microsoft-defender-antivirus.md)|有关使用专用命令行工具管理和使用Microsoft Defender 防病毒的说明|

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)