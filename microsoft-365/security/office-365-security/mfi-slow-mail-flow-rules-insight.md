---
title: 修复慢邮件流规则见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: 管理员可了解如何使用安全 & 合规中心内的修复慢邮件流规则见解，以识别并修复其组织中也称为传输规则 () 的低效或断开的邮件流规则。
ms.openlocfilehash: 6319633c47e34d7b62c4f68bfbda7fe298c0deb3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826877"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>修复了安全管理与合规中心中的邮件流&见解

低效邮件流规则 (亦称为"传输规则") 会为组织带来邮件流延迟。 此见解报告会对你组织的邮件流产生影响的邮件流规则。 这些类型的规则的示例包括：

- 大型组 **使用是其** 成员的条件。
- 使用复杂正则表达式条件 (正则表达式) 模式匹配。
- 使用附件中内容检查的条件。

**"为安全**& 合规中心"中的"**为你**区中的邮件流"区域[，"](mail-flow-insights-v2.md)建议的邮件流规则见解"见解会在邮件流规则过长而无法完成时通知你。 只有在检测到条件时如果没有任何邮件循环，则此 (看到的情况就不会) 。

可以使用此通知帮助你确定并调整邮件流规则，以帮助减少邮件流延迟。

![修复邮件流规则缓慢见解，在"为你区中的邮件流仪表板建议"区域](../../media/mfi-fix-slow-mail-flow-rules.png)

在单击 **小部件上的** 查看详细信息时，将出现一个浮出控件，并显示更多信息：

- **规则**：可以将鼠标悬停在摘要上，以查看规则的所有条件、例外情况和操作。 可以单击摘要，以编辑 Exchange 管理中心邮箱 (设置) 。
- **评估的邮件数**：您可以单击 **"查看示例邮件**"来查看受规则[message trace](message-trace-scc.md)影响的邮件示例的邮件跟踪结果。
- **每封邮件的平均时间**
- **邮件上居中时间：** 将上半部分和时间数据分隔开的中间值。

![单击"修复缓慢邮件流规则见解"后显示的详细信息浮出控件](../../media/mfi-fix-slow-mail-flow-rules-details.png)

有关 Exchange Online 中邮件流规则的条件和例外的详细信息，请参阅[邮件流规则条件和例外 (预测) Exchange Online 中的部分。](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
