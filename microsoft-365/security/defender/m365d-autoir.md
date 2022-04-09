---
title: Microsoft 365 Defender 中的自动调查和响应
description: 大致了解自动调查和响应功能（也称为自我修复）Microsoft 365 Defender
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 自我修复
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 332802150235ec6f47c4bdea34b34edb94ea1b90
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731320"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

如果组织使用[Microsoft 365 Defender](microsoft-365-defender.md)，则每当检测到恶意或可疑活动或项目时，安全运营团队都会在Microsoft 365 Defender门户中收到警报。 鉴于可能出现的威胁似乎永无止境，安全团队通常面临着应对大量警报的挑战。 幸运的是，Microsoft 365 Defender包括自动调查和响应 (AIR) 功能，可帮助安全运营团队更高效、更有效地应对威胁。

本文概述了 AIR，并包含指向后续步骤和其他资源的链接。

## <a name="how-automated-investigation-and-self-healing-works"></a>自动化调查和自我修复的工作原理

在触发安全警报时，安全操作团队将负责调查这些警报，并采取措施保护组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 自动调查和响应功能，通过自我修复，在Microsoft 365 Defender可以帮助。

观看以下视频，了解自我修复的工作原理： <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在Microsoft 365 Defender中，使用自我修复功能的自动调查和响应可在设备、电子邮件&内容和标识之间工作。
 
> [!TIP]
> 本文介绍自动调查和响应的工作原理。 若要配置这些功能，请参阅Microsoft 365 Defender[中配置自动调查和响应功能](m365d-configure-auto-investigation-response.md)。

## <a name="your-own-virtual-analyst"></a>你自己的虚拟分析师

Imagine第 1 层或第 2 层安全运营团队中拥有虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟分析师可以使用 24x7，容量不受限制，并承担大量的调查和威胁修正。 此类虚拟分析师可以显著减少响应时间，从而为其他重要威胁或战略项目释放安全运营团队。 如果这个场景听起来像科幻小说， 不是！ 此类虚拟分析师是Microsoft 365 Defender套件的一部分，其名称是 *自动调查和响应*。

自动调查和响应功能使安全运营团队能够大幅提高组织处理安全警报和事件的能力。 通过自动调查和响应，可以降低处理调查和响应活动的成本，并充分利用威胁防护套件。 自动调查和响应功能通过以下方式帮助安全运营团队：

1. 确定是否需要针对某个威胁采取行动。
2. 执行（或建议执行）任何必要的修正操作。
3. 确定是否应执行其他调查以及应执行哪些其他调查。
4. 根据需要对其他警报重复此流程。

## <a name="the-automated-investigation-process"></a>自动调查流程

警报会创建一个事件，该事件可以启动自动调查。 自动调查结果为每一件证据做出判决。 判决可以是：
- *恶意*
- *可疑* 
- *未发现威胁* 

识别恶意或可疑实体的修正操作。 修正操作的示例包括：

- 将文件发送到隔离区
- 停止进程
- 正在隔离设备
- 阻止 URL 
- 其他操作

有关详细信息，请参阅[Microsoft 365 Defender中的修正操作](m365d-remediation-actions.md)。

根据为组织 [配置自动调查和响应功能的方式](m365d-configure-auto-investigation-response.md) ，修正操作是自动执行的，或者仅在安全运营团队批准后才执行。 操作 [中心](m365d-action-center.md)中列出了所有操作（无论是挂起还是已完成）。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他位置看到受影响的实体，则自动调查会扩展其范围以包含该实体，并且重复调查流程。 

在Microsoft 365 Defender中，每个自动调查都会将Microsoft Defender for Identity、Microsoft Defender for Endpoint和Microsoft Defender for Office 365，如下表所述： 

|实体 |威胁防护服务  |
|:---------|:---------|
|设备 (也称为终结点或计算机)  |[Defender for Endpoint](../defender-endpoint/automated-investigations.md) |      
|本地 Active Directory 用户、实体行为和活动     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件内容 (可以包含文件和 URL 的电子邮件)      |[Defender for Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> 并非每个警报都会触发自动调查，而不是每个调查都会导致自动修正操作。 这取决于如何为组织配置自动调查和响应。 请参阅 [配置自动调查和响应功能](m365d-configure-auto-investigation-response.md)。

## <a name="viewing-a-list-of-investigations"></a>查看调查列表

若要查看调查，请转到 **"事件"** 页。 选择事件，然后选择" **调查** "选项卡。若要了解详细信息，请参阅 [自动化调查的详细信息和结果](m365d-autoir-results.md)。

## <a name="training-for-security-analysts"></a>针对安全分析师的培训

使用 Microsoft Learn 中的此学习模块了解Microsoft 365 Defender如何使用自动自我修复进行事件调查和响应。

|培训：|使用 Microsoft 365 Defender 自动 self-healing|
|---|---|
|![使用Microsoft 365 Defender训练图标自动自我修复。](../../media/m365d-autoir/m365-defender-auto-self-healing.svg)| Microsoft 365 Defender使用 AI 自动修正事件，帮助安全运营团队更高效、更有效地应对威胁。 <p> 11 分钟 - 5 个单位 |

> [!div class="nextstepaction"]
> [开始>](/learn/modules/defender-self-healing/)

## <a name="next-steps"></a>后续步骤

- [查看自动调查和响应的先决条件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [为组织配置自动调查和响应](m365d-configure-auto-investigation-response.md)
- [详细了解操作中心](m365d-action-center.md)
