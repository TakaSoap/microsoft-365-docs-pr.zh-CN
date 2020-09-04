---
title: 修复可能的邮件循环见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的 "邮件流" 仪表板中的 "修复可能的邮件循环真知灼见" 来识别和修复其组织中的邮件循环。
ms.openlocfilehash: 063906195488aa7d65093c538d9045002448e181
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358266"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>修复安全 & 合规中心中可能的邮件循环见解

邮件循环已损坏，因为它会浪费系统资源、使用组织的邮件卷配额，并发送令人费解的未送达报告 (也称为 Ndr 或退回邮件) 发送给原始发件人。

修复了[安全 & 合规中心](https://protection.office.com)中的[邮件流仪表板](mail-flow-insights-v2.md)的**建议**的邮件**循环**见解，当组织中检测到邮件循环时，会向您发出通知。 此洞察力仅在检测到条件后出现 (如果您没有任何邮件循环，则不会看到) 的洞察力。

![修复邮件流仪表板的 "为您推荐的情况" 区域中的邮件流规则的速度下降](../../media/mfi-fix-possible-mail-loop.png)

当您单击小组件上的 " **查看详细信息** " 时，将显示一个弹出项，其中包含详细信息：

- **域**
- **邮件数**：您可以单击 " **查看示例邮件** "，查看受循环影响的邮件示例的 [邮件跟踪](message-trace-scc.md) 结果。
- **域类型**（例如，权威或非权威）。
- **MX 记录**：主机 (域的 MX 记录的 **邮件服务器**) 和 **优先级** 值。
- **循环原因** 和 **解决方法**：我们将尝试确定最常见的邮件循环方案，并提供建议的操作 (如果可用) 修复循环。

![在 "修复可能的邮件循环" 见解上单击 "查看详细信息" 后出现的详细信息浮出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
