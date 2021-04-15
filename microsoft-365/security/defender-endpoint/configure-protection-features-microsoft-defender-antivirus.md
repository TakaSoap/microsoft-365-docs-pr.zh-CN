---
title: 启用和配置 Microsoft Defender 防病毒保护功能
description: 在 Microsoft Defender AV 中启用基于行为的启发式实时保护。
keywords: 启发式， 机器学习， 行为监视器， 实时保护， 始终运行， Microsoft Defender 防病毒， 反恶意软件， 安全性， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 9fc51682b659670a21c3c293ea8996beb228802a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765067"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>配置方案、高要求和实时保护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒使用多种方法来提供威胁防护：

- 云提供的保护，用于即时检测和阻止新出现的威胁
- 始终打开扫描，使用文件和进程行为监视以及其他启发 (也称为"实时保护") 
- 基于机器学习、人工和自动化大数据分析，以及深入的威胁抵御研究的专用保护更新

你可以配置 Microsoft Defender 防病毒如何使用组策略、System Center Configuration Manage、PowerShell cmdlet 和 Windows Management Instrumentation (WMI) 。

本部分介绍了始终扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。

请参阅 [通过云保护使用](cloud-protection-microsoft-defender-antivirus.md) 下一代 Microsoft Defender 防病毒技术，了解如何启用和配置 Microsoft Defender 防病毒云保护。

## <a name="in-this-section"></a>本节内容

 主题 | 说明
---|---
[检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | 检测并阻止网络中可能不需要的应用，如广告软件、浏览器修饰符和工具栏以及未授权或伪造的防病毒应用
[启用和配置 Microsoft Defender 防病毒保护功能](configure-real-time-protection-microsoft-defender-antivirus.md) | 启用和配置实时保护、启发和其他始终启用的 Microsoft Defender 防病毒监视功能