---
title: 修复可能的邮件循环见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在安全与合规中心的邮件流仪表板中使用"修复可能的邮件循环"见解&标识和修复其组织的邮件循环。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150227"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>修复安全与合规中心内可能的邮件&见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

邮件循环错误，因为：

- 它们浪费系统资源。
- 它们使用组织的邮件卷配额。
- 它们向原始邮件 (发送混淆的未送达报告) 或退回邮件。

安全 **与** 合规中心内邮件流仪表板的"建议你"区域中 [](mail-flow-insights-v2.md)的"修复可能的邮件 [](https://protection.office.com)循环见解"&在组织中检测到邮件循环时通知您。 

此见解仅在检测到条件 (（如果您没有任何邮件循环）后，您才能看到该) 。

![修复邮件流仪表板的"建议"区域中的慢邮件流规则见解](../../media/mfi-fix-possible-mail-loop.png)

单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：

- **域**
- **消息数**：可以单击"**查看示例** 邮件"以查看受循环 [](message-trace-scc.md)影响的邮件示例的邮件跟踪结果。
- **域类型**" 例如，权威或非权威。
- **MX 记录**： (**邮箱服务器)** MX 记录的优先级值和优先级值。
- **循环原因****和修复** 方法：我们将确定最常见的邮件循环方案并提供建议的操作来修复循环。

![单击"修复可能的邮件循环见解"上的"查看详细信息"后显示的详细信息飞出](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
