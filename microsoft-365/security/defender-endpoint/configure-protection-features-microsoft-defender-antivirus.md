---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 在 Microsoft Defender AV 中启用基于行为、启发式和实时保护。
keywords: 启发式， 机器学习， 行为监视器， 实时保护， 始终打开， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 59754ac5186b87045e8126114fd7342f5aa9532c
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788845"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>配置方案、高要求和实时保护


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒 

**平台**
- Windows

Microsoft Defender 防病毒使用多种方法来提供威胁防护：

- 用于近即时检测和阻止新威胁和新出现威胁的云保护
- 始终打开扫描、使用文件和进程行为监视以及其他启发式 (也称为“实时保护”) 
- 基于机器学习、人工和自动化大数据分析以及深入威胁抵抗研究的专用防护更新

可以配置Microsoft Defender 防病毒如何将这些方法与组策略、System Center配置管理、PowerShell cmdlet 和 Windows Management Instrumentation 配合使用 (WMI) 。

本部分介绍用于始终打开扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。

请参阅[通过云保护使用下一代Microsoft Defender 防病毒技术](cloud-protection-microsoft-defender-antivirus.md)，了解如何启用和配置Microsoft Defender 防病毒云保护。

## <a name="in-this-section"></a>本节内容

| 主题|说明 |
|---|---|
| [检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| 检测和阻止网络中可能不需要的应用，例如广告软件、浏览器修饰符和工具栏，以及恶意或虚假的防病毒应用 |
| [启用和配置Microsoft Defender 防病毒保护功能](configure-real-time-protection-microsoft-defender-antivirus.md)|启用和配置实时保护、启发式和其他始终Microsoft Defender 防病毒监视功能 |

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
