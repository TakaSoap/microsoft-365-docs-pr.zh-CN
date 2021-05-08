---
title: Microsoft 365 Defender 中的自动调查和响应
description: 大致了解 Microsoft 365 Defender 中的自动调查和响应功能（也称为自我修复）
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259531"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的自动调查和响应

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

如果你的组织使用[Microsoft 365 Defender，](microsoft-365-defender.md)则每当检测到恶意或可疑活动或项目Microsoft 365安全中心内收到警报。 鉴于可能进入的威胁流看起来从未结束，安全团队经常面临解决大量警报的挑战。 幸运的是，Microsoft 365 Defender 包括自动调查和修正 (AIR) 功能，可帮助你的安全运营团队更高效地应对威胁。

本文概述了 AIR，并包含指向下一步步骤和其他资源的链接。

> [!TIP]
> 希望体验 Microsoft 365 Defender？ 你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。

## <a name="how-automated-investigation-and-self-healing-works"></a>自动调查和自我修复的工作原理

触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。 对警报进行优先级划分和调查可能会非常耗时，如果在调查期间不断发出新警报，则尤为如此。 安全运营团队可能对必须监视和防范的大量威胁感到不知所措。 Defender 中的自动调查和响应功能以及自我修复Microsoft 365 Defender 可以提供帮助。

观看以下视频，了解自我修复的工作原理： <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

在 Microsoft 365 Defender 中，具有自我修复功能的自动调查和响应适用于你的设备、电子邮件&内容和标识。
 
> [!TIP]
> 本文介绍了自动调查和响应的工作原理。 若要配置这些功能，请参阅在 Microsoft 365 Defender 中配置[自动调查和响应功能](m365d-configure-auto-investigation-response.md)。

## <a name="your-own-virtual-analyst"></a>你自己的虚拟分析师

Imagine级别 1 或第 2 层安全运营团队中具有虚拟分析师。 虚拟分析师模仿安全运营团队调查和修正威胁所采取的理想步骤。 虚拟分析师可以 24x7 工作，且容量不受限制，并承担大量的调查和威胁修正工作。 此类虚拟分析师可以显著减少响应时间，释放安全运营团队用于其他重要威胁或战略项目。 如果此方案看起来像科学虚构，则不是！ 此类虚拟分析师是你的 Microsoft 365 Defender 套件的一部分，其名称是 *自动调查和响应*。

自动调查和响应功能使安全运营团队可以大大增加组织处理安全警报和事件的能力。 通过自动调查和响应，你可以降低调查和修正活动处理的成本，并能够最利用威胁防护套件。 自动调查和响应功能可有助于安全运营团队：

1. 确定威胁是否需要操作。
2. 采取 (或建议) 必要的修正操作。
3. 确定是否应进行其他调查以及应进行哪些其他调查。
4. 根据需要对其他警报重复此过程。

## <a name="the-automated-investigation-process"></a>自动调查流程

警报将创建一个事件，可以启动自动调查。 自动调查会针对每条证据做出裁定。 裁定可以是：
- *恶意*
- *可疑* 
- *未发现威胁* 

识别恶意或可疑实体的修正操作。 修正操作的示例包括：

- 将文件发送到隔离区
- 停止进程
- 隔离设备
- 阻止 URL 
- 其他操作

有关详细信息，请参阅 Defender 中的修正[Microsoft 365操作](m365d-remediation-actions.md)。

根据 [组织的自动](m365d-configure-auto-investigation-response.md) 调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。 所有操作（无论是挂起操作还是已完成操作）都列在操作 [中心中](m365d-action-center.md)。

运行调查时，出现的所有其他相关警报将被添加到调查中，直到调查完成。 如果在其他地方看到受影响的实体，则自动调查会扩展其范围以包括该实体，并且调查过程将重复。 

在 Microsoft 365 Defender 中，每个自动调查将 Microsoft Defender for Identity、Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 信号关联起来，如下表所示： 

|实体 |威胁防护服务  |
|:---------|:---------|
|设备 (也称为终结点或计算机)  |[适用于终结点的 Defender](../defender-endpoint/automated-investigations.md) |      
|本地 Active Directory 用户、实体行为和活动     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|电子邮件 (可能包含文件和 URL 的电子邮件)      |[Defender for Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> 不是每个警报都会触发自动调查，而并非所有调查都会触发自动修正操作。 这取决于如何为组织配置自动调查和响应。 请参阅 [配置自动调查和响应功能](m365d-configure-auto-investigation-response.md)。

## <a name="viewing-a-list-of-investigations"></a>查看调查列表

若要查看调查，请转到" **事件"** 页面。 选择事件，然后选择" **调查"** 选项卡。若要了解详细信息， [请参阅详细信息和自动调查的结果](m365d-autoir-results.md)。


## <a name="next-steps"></a>后续步骤

- [请参阅自动调查和响应的先决条件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [为组织配置自动调查和响应](m365d-configure-auto-investigation-response.md)
- [详细了解操作中心](m365d-action-center.md)
