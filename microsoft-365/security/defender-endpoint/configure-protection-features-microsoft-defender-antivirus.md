---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 在 Microsoft Defender AV 中启用基于行为的启发式实时保护。
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
ms.openlocfilehash: a82349553c098c604e8901568a7a42b1c4f896df
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555940"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>配置方案、高要求和实时保护


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒使用多种方法来提供威胁防护：

- 用于快速检测和阻止新威胁和新兴威胁的云保护
- 始终打开扫描，使用文件和进程行为监视以及其他启发 (也称为"实时保护") 
- 基于机器学习、人工和自动化大数据分析，以及深入的威胁抵御研究的专用保护更新

你可以配置如何Microsoft Defender 防病毒组策略、System Center配置管理、PowerShell cmdlet 和 WMI Windows Management Instrumentation (这些方法) 。

本部分介绍了始终扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。

请参阅[通过云保护](cloud-protection-microsoft-defender-antivirus.md)Microsoft Defender 防病毒下一代技术，了解如何启用和配置Microsoft Defender 防病毒云保护。

## <a name="in-this-section"></a>本节内容

| 主题|说明 |
|---|---|
| [检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| 检测并阻止网络中可能不需要的应用，例如广告软件、浏览器修饰符和工具栏以及未授权或伪造的防病毒应用 |
| [启用和配置Microsoft Defender 防病毒保护功能](configure-real-time-protection-microsoft-defender-antivirus.md)|启用和配置实时保护、启发和其他始终启用Microsoft Defender 防病毒监视功能 |
