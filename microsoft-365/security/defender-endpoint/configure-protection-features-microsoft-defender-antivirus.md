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
ms.openlocfilehash: f949623b7d0647d71f4c665ed2016ee14a765e5f
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807508"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>配置方案、高要求和实时保护


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender 防病毒使用多种方法来提供威胁防护：

- 用于快速检测和阻止新威胁和新兴威胁的云保护
- 始终扫描，使用文件和进程行为监视以及其他启发 (也称为"实时保护") 
- 基于机器学习、人工和自动大数据分析以及深度威胁防护研究专用的保护更新

你可以配置如何Microsoft Defender 防病毒组策略、System Center配置管理、PowerShell cmdlet 和 WMI Windows Management Instrumentation (这些方法) 。

本部分介绍始终扫描的配置，包括如何检测和阻止被视为不安全但可能不会被检测为恶意软件的应用。

请参阅[通过云保护Microsoft Defender 防病毒](cloud-protection-microsoft-defender-antivirus.md)下一代云技术，了解如何启用和配置Microsoft Defender 防病毒云保护。

## <a name="in-this-section"></a>本节内容

| 主题|说明 |
|---|---|
| [检测并阻止可能不需要的应用程序](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md)| 检测并阻止网络中可能不需要的应用，如广告软件、浏览器修饰符和工具栏以及未授权或伪造的防病毒应用 |
| [启用和配置Microsoft Defender 防病毒保护功能](configure-real-time-protection-microsoft-defender-antivirus.md)|启用和配置实时保护、启发和其他始终启用Microsoft Defender 防病毒监视功能 |
