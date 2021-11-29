---
title: 运行并自定义计划扫描和按需扫描。
description: 自定义和启动Microsoft Defender 防病毒终结点上的扫描
keywords: 扫描， 计划， 自定义， 排除， 排除文件， 修正， 扫描结果， 隔离， 删除威胁， 快速扫描， 完全扫描， Microsoft Defender 防病毒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 9acac2868b0bd2449338f4a61f663d8cfe8a8ee4
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218246"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a>自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

可以使用组策略、PowerShell 和 Windows Management Instrumentation (WMI) 配置Microsoft Defender 防病毒扫描。 

## <a name="in-this-section"></a>本节内容

主题 | 说明
---|---
[配置并验证扫描过程中的文件、文件夹和进程打开Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md) | 你可以排除文件 (包括由指定进程修改的文件) 和文件夹从按需扫描、计划扫描和始终打开实时保护监视和扫描中排除
[配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) | 可以将Microsoft Defender 防病毒配置为包括某些类型的电子邮件存储文件、备份或重新分析点以及存档的文件 (如扫描中.zip) 文件。 还可以启用网络文件扫描
[配置扫描修正](configure-remediation-microsoft-defender-antivirus.md) | 配置Microsoft Defender 防病毒威胁时应执行哪些操作，以及隔离文件应在隔离文件夹中保留多久
[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | 设置定期 (定期) 扫描，包括应何时运行以及是作为完整扫描还是快速扫描运行
[配置并运行扫描](run-scan-microsoft-defender-antivirus.md) | 使用 PowerShell 运行和配置按需扫描、Windows Management Instrumentation，或者使用 Windows 安全中心 应用在终结点上单独运行和配置Windows 安全中心扫描
[查看扫描结果](review-scan-results-microsoft-defender-antivirus.md) | 使用应用、应用Microsoft Endpoint Configuration Manager、Microsoft Intune或Windows 安全中心扫描结果