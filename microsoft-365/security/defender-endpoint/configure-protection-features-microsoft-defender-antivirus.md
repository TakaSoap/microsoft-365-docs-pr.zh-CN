---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 在 Microsoft Defender AV 中启用基于行为的启发式实时保护。
keywords: 启发式， 机器学习， 行为监视器， 实时保护， 始终打开， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925551"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>配置方案、高要求和实时保护


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒使用多种方法来提供威胁防护：

- 云提供的保护，用于即时检测和阻止新出现的威胁
- 始终打开扫描，使用文件和进程行为监视以及其他启发 (也称为"实时保护") 
- 基于机器学习、人工和自动化大数据分析，以及深入的威胁抵御研究的专用保护更新

你可以配置如何Microsoft Defender 防病毒组策略、System Center配置管理、PowerShell cmdlet 和 WMI Windows Management Instrumentation (这些方法) 。

本部分介绍了始终扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。

请参阅[通过云保护Microsoft Defender 防病毒下](cloud-protection-microsoft-defender-antivirus.md)一代技术，了解如何启用和配置Microsoft Defender 防病毒提供的保护。

## <a name="in-this-section"></a>本节内容

 主题 | 说明
---|---
[检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | 检测并阻止网络中可能不需要的应用，如广告软件、浏览器修饰符和工具栏以及未授权或伪造的防病毒应用
[启用和配置Microsoft Defender 防病毒保护功能](configure-real-time-protection-microsoft-defender-antivirus.md) | 启用和配置实时保护、启发和其他始终启用Microsoft Defender 防病毒监视功能
