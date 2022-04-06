---
title: 修复慢邮件流规则见解
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的"修复慢邮件流规则"见解来识别和修复无效或损坏的邮件流规则 (也称为) 传输规则。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af6d727f84cdaaed1b7f7558313ac7d080a13c93
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681515"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>修复安全与合规中心中的&流规则见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

无效的邮件流 (也称为传输规则) 可能导致组织的邮件流延迟。 此见解报告对组织的邮件流有影响的邮件流规则。 这些类型的规则的示例包括：

- 对于大型 **组，使用 Is** 成员的条件。
- 使用复杂正则表达式的条件 (正则表达式) 模式匹配。
- 使用附件内容检查的条件。

安全 [&](https://protection.office.com)**与** 合规中心内"邮件流"仪表板的"建议你 [](mail-flow-insights-v2.md)"区域中的"修复慢邮件流规则"见解在邮件流规则完成时间过长时通知您。

此见解仅在检测到条件 (（如果没有任何邮件循环）后显示，你将看不到) 。

可以使用此通知来帮助确定和微调邮件流规则，以帮助减少邮件流延迟。

![修复邮件流仪表板的"推荐使用"区域中的慢邮件流规则见解。](../../media/mfi-fix-slow-mail-flow-rules.png)

单击小 **组件上的** "查看详细信息"时，将显示一个包含详细信息的飞出控件：

- **规则**：您可以将鼠标悬停在摘要上以查看规则的所有条件、例外和操作。 You can click on the summary to edit the rule in the Exchange admin center (EAC) at <https://admin.exchange.microsoft.com/#/transportrules>.
- **评估的邮件数**：可以单击"查看示例邮件"以查看受规则影响 [](message-trace-scc.md)的邮件示例的邮件跟踪结果。
- **每封邮件所花费的平均时间**
- **在邮件上花费的中值时间**：将上半部分与上半部分时间数据分开的中间值。

![详细信息 在单击"修复慢速邮件流规则见解"上的"查看详细信息"后出现的飞出图。](../../media/mfi-fix-slow-mail-flow-rules-details.png)

有关邮件流规则中的条件和例外项详细信息，请参阅邮件流规则条件和例外 ([中) Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。