---
title: Microsoft 365 Defender 中的自动调查和响应
description: 大致了解自动调查和响应功能（也称为自我修复Microsoft 365 Defender
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 5ca23f61b2843f582ed704b69f702559afdeeffa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199473"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

如果组织正在使用[Microsoft 365 Defender，](microsoft-365-defender.md)则每当检测到恶意或可疑活动Microsoft 365 Defender，安全运营团队都会在安全门户中收到警报。 鉴于可能进入的威胁流看起来从未结束，安全团队经常面临解决大量警报的挑战。 幸运的是，Microsoft 365 Defender包括自动调查和响应 (AIR) 功能，可帮助安全运营团队更有效地应对威胁。

本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。

> [!TIP]
> 想要体验 Microsoft 365 Defender？你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。

## <a name="how-automated-investigation-and-self-healing-works"></a>自动调查和自我修复的工作原理

触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 自动调查和响应功能以及自动修复功能Microsoft 365 Defender可提供帮助。

观看以下视频，了解自我修复的工作原理： <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在Microsoft 365 Defender中，具有自我修复功能的自动调查和响应适用于你的设备、电子邮件&内容和标识。
 
> [!TIP]
> 本文介绍了自动调查和响应的工作原理。 若要配置这些功能，请参阅在 Microsoft 365 Defender[中配置自动调查和响应Microsoft 365 Defender。](m365d-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>你自己的虚拟分析师

Imagine级别 1 或第 2 层安全运营团队中具有虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟分析师可以 24x7 工作，且容量不受限制，并承担大量的调查和威胁修正工作。 此类虚拟分析师可以显著减少响应时间，释放安全运营团队用于其他重要威胁或战略项目。 如果此方案看起来像科学虚构，则不是！ 此类虚拟分析师是 Microsoft 365 Defender套件的一部分，其名称是自动 *调查和响应*。

自动调查和响应功能使安全运营团队可以大大增加组织处理安全警报和事件的能力。 通过自动调查和响应，你可以降低调查和响应活动处理的成本，并能够最利用威胁防护套件。 自动调查和响应功能可有助于安全运营团队：

1. 确定是否需要针对某个威胁采取行动。
2. 执行（或建议执行）任何必要的修正操作。
3. 确定是否应执行其他调查以及应执行哪些其他调查。
4. 根据需要对其他警报重复此流程。

## <a name="the-automated-investigation-process"></a>自动调查流程

警报将创建一个事件，可以启动自动调查。 自动调查会针对每条证据做出裁定。 裁定可以是：
- *恶意*
- *可疑* 
- *未发现威胁* 

识别恶意或可疑实体的修正操作。 修正操作的示例包括：

- 将文件发送到隔离区
- 停止进程
- 正在隔离设备
- 阻止 URL 
- 其他操作

有关详细信息，请参阅修正[操作Microsoft 365 Defender。](m365d-remediation-actions.md)

根据 [组织的自动](m365d-configure-auto-investigation-response.md) 调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。 所有操作（无论是挂起操作还是已完成操作）都列在操作 [中心中](m365d-action-center.md)。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，则自动调查会扩展其范围以包含该实体，并且重复调查流程。 

在 Microsoft 365 Defender 中，每个自动调查将 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之间的信号关联起来，如下表所示： 

|实体 |威胁防护服务  |
|:---------|:---------|
|设备 (也称为终结点或计算机)  |[Defender for Endpoint](../defender-endpoint/automated-investigations.md) |      
|本地 Active Directory 用户、实体行为和活动     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件 (可能包含文件和 URL 的电子邮件)      |[Defender for Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> 不是每个警报都会触发自动调查，而并非所有调查都会触发自动修正操作。 这取决于如何为组织配置自动调查和响应。 请参阅 [配置自动调查和响应功能](m365d-configure-auto-investigation-response.md)。

## <a name="viewing-a-list-of-investigations"></a>查看调查列表

若要查看调查，请转到" **事件"** 页面。 选择事件，然后选择" **调查"** 选项卡。若要了解详细信息， [请参阅详细信息和自动调查的结果](m365d-autoir-results.md)。

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

使用 Microsoft Learn 中的此学习模块可Microsoft 365 Defender自动自我修复用于事件调查和响应。

|培训：|使用 Microsoft 365 Defender 自动 self-healing|
|---|---|
|![使用培训图标自动Microsoft 365 Defender自我修复。](../../media/m365d-autoir/m365-defender-auto-self-healing.svg)| Microsoft 365 Defender AI 自动修复事件，帮助安全运营团队更有效地应对威胁。 <p> 11 分钟 - 5 个单位 |

> [!div class="nextstepaction"]
> [开始>](/learn/modules/defender-self-healing/)

## <a name="next-steps"></a>后续步骤

- [请参阅自动调查和响应的先决条件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [为组织配置自动调查和响应](m365d-configure-auto-investigation-response.md)
- [详细了解操作中心](m365d-action-center.md)
