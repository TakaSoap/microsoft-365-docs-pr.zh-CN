---
title: 修复慢邮件流规则见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的"修复慢速邮件流规则"见解来识别和修复低效率或已损坏的邮件流规则 (也称为组织中) 传输规则。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150780"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>修复安全与合规中心内缓慢&规则见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

无效的邮件流规则 (也称为传输规则) 可能会导致组织的邮件流延迟。 此见解报告对组织的邮件流有影响的邮件流规则。 这些类型的规则的示例包括：

- 使用" **是大型组** 的成员"的条件。
- 使用复杂正则表达式的条件 (正则表达式) 模式匹配。
- 在附件中使用内容检查的条件。

安全 **与** 合规中心内邮件流仪表板的"建议你"区域中的 [](mail-flow-insights-v2.md)"修复慢邮件流 [](https://protection.office.com)规则"见解&在邮件流规则完成时间过长时通知您。 

此见解仅在检测到条件 (（如果您没有任何邮件循环）后，您才能看到该) 。

可以使用此通知来帮助确定和微调邮件流规则，以帮助减少邮件流延迟。

![修复邮件流仪表板的"建议"区域中的慢邮件流规则见解](../../media/mfi-fix-slow-mail-flow-rules.png)

单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：

- **规则**：您可以将鼠标悬停在摘要上方，以查看规则的所有条件、例外和操作。 You can click on the summary to edit the rule in the Exchange admin center (EAC) .
- **评估的邮件数**：可以单击"查看示例邮件"以查看受规则影响 [](message-trace-scc.md)的邮件示例的邮件跟踪结果。
- **每封邮件所花费的平均时间**
- **在邮件上花费的中值时间**：将上半部分与下半部分时间数据分开的中间值。

![单击"修复慢速邮件流规则"见解上的"查看详细信息"后显示的详细信息飞出](../../media/mfi-fix-slow-mail-flow-rules-details.png)

有关邮件流规则中的条件和例外的信息，请参阅 Exchange Online 中的邮件流规则 ([例外) 和例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
