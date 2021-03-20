---
title: Microsoft 365 Defender 中的自动调查和响应
description: 在 Microsoft 365 Defender 中大致了解自动调查和响应功能（也称为自我修复）
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 199bc72e7a8e1e5783105b44de150368a41b872c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917078"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

如果你的组织使用的是 [Microsoft 365 Defender，](microsoft-threat-protection.md)则安全运营团队将在检测到恶意或可疑项目时收到警报。 鉴于似乎永远不会结束的威胁流，安全团队通常会面临解决大量警报的挑战。 幸运的是，Microsoft 365 Defender 包括自动调查和修正 (AIR) 功能，可帮助你的安全运营团队更有效地应对威胁。

本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。

> [!TIP]
> 想要体验 Microsoft 365 Defender？ 可以在[实验室环境中评估它或在](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab)[生产中运行你的试验项目](./mtp-pilot.md?ocid=cx-evalpilot)。

## <a name="how-automated-investigation-and-self-healing-works"></a>自动调查和自我修复的工作原理

触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 Microsoft 365 Defender 中的自动调查和响应功能以及自我修复可提供帮助。

观看以下视频，了解自我修复的工作原理： <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，具有自我修复功能的自动调查和响应适用于你的设备、电子邮件&内容和标识。
 
> [!TIP]
> 本文介绍了自动调查和响应的工作原理。 若要配置这些功能，请参阅在 [Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中配置自动调查和响应功能。

## <a name="your-own-virtual-analyst"></a>你自己的虚拟分析师

假设你的第 1 层或第 2 层安全运营团队有一个虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟助手可以全天候工作，且容量无限制，它承担大量的调查和威胁修正工作。 这样的虚拟助手可以大大减少响应时间，让你的安全运营团队腾出时间来进行其他重要的战略项目。 如果此方案看起来像科学虚构，则不是！ 此类虚拟分析师是 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。

自动调查和响应功能使安全运营团队可以大大增加组织处理安全警报和事件的能力。 通过自动调查和响应，你可以降低调查和修正活动处理的成本，并能够最利用威胁防护套件。 自动调查和响应功能可有助于安全运营团队：

1. 确定是否需要针对威胁执行操作；
2. 采取 (或建议) 必要的修正操作;
3. 确定是否应进行其他调查以及应进行哪些其他调查;和
4. 根据需要对其他警报重复此过程。

## <a name="the-automated-investigation-process"></a>自动调查流程

警报将创建一个事件，可以启动自动调查。 自动调查会针对每条证据做出裁定。 裁定可以是：
- *恶意*;
- *可疑*;或 
- *未找到威胁*。 

识别恶意或可疑实体的修正操作。 修正操作的示例包括：
- 将文件发送到隔离区;
- 停止进程;
- 隔离设备;
- 阻止 URL;和 
- 其他操作。  ([Microsoft 365 Defender](mtp-remediation-actions.md).) 中的修正操作

根据 [组织的自动](mtp-configure-auto-investigation-response.md) 调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。 所有操作（无论是挂起操作还是已完成操作）都列在操作 [中心中](mtp-action-center.md)。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他地方看到已规定实体，则自动调查会扩展其范围以包括该实体，并且调查过程将重复。 

在 Microsoft 365 Defender 中，每个自动调查将跨 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Defender for Office 365 的信号关联起来，如下表所示： 

|实体 |威胁防护服务  |
|:---------|:---------|
|设备 (也称为终结点，有时也称为计算机)      |[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件 (可能包含文件和 URL 的电子邮件)      |[Microsoft Defender for Office 365](../office-365-security/office-365-atp.md)         |

> [!NOTE]
> 不是每个警报都会触发自动调查，并且并非所有调查都会触发自动修正操作;这取决于如何为组织配置自动调查和响应。 请参阅 [在 Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)中配置自动调查和响应功能。

## <a name="next-steps"></a>后续步骤

- [请参阅 Microsoft 365 Defender 中自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [为组织配置自动调查和响应](mtp-configure-auto-investigation-response.md)
- [详细了解操作中心](mtp-action-center.md)