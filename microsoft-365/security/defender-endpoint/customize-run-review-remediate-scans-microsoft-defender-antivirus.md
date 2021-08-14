---
title: 运行并自定义计划扫描和按需扫描。
description: 自定义和启动Microsoft Defender 防病毒终结点上的扫描
keywords: 扫描， 计划， 自定义， 排除， 排除文件， 修正， 扫描结果， 隔离， 删除威胁， 快速扫描， 完全扫描， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: d00cb3a3c708573d7283c83d79ebaabcb45f6ce68a649109cb874c77c6cfabc3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53847495"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组策略、PowerShell 和 WMI Windows Management Instrumentation (WMI) 配置Microsoft Defender 防病毒扫描。 

## <a name="in-this-section"></a>本节内容

主题 | 说明
---|---
[配置并验证扫描过程中的文件、文件夹和进程打开Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md) | 你可以排除文件 (包括由指定进程) 修改的文件和文件夹从按需扫描、计划扫描和始终打开实时保护监视和扫描中排除
[配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 可以将Microsoft Defender 防病毒配置为包括某些类型的电子邮件存储文件、备份或重新分析点以及存档的文件 (如扫描中.zip) 文件。 还可以启用网络文件扫描
[配置扫描修正](configure-remediation-microsoft-defender-antivirus.md) | 配置Microsoft Defender 防病毒威胁时应执行哪些操作，以及隔离文件应在隔离文件夹中保留多久
[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
[配置并运行扫描](run-scan-microsoft-defender-antivirus.md) | 使用 PowerShell、Windows Management Instrumentation 运行和配置按需扫描，或者使用 Windows 安全中心 应用在终结点上单独运行和配置Windows 安全中心扫描
[查看扫描结果](review-scan-results-microsoft-defender-antivirus.md) | 使用应用、Microsoft Endpoint Configuration Manager或Microsoft Intune查看Windows 安全中心结果