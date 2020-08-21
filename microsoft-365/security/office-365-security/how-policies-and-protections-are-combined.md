---
title: 电子邮件保护的顺序和优先级
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， ATP， Microsoft Defender ATP， Office 365 ATP， Azure ATP
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (和 EOP) 中的应用程序防护顺序，以及保护策略中的优先级值如何确定应用哪种策略。
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827405"
---
# <a name="order-and-precedence-of-email-protection"></a>电子邮件保护的顺序和优先级

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，入站电子邮件可能会被多种形式的保护标记。 例如，适用于所有 Microsoft 365 客户的内置 EOP 防钓鱼策略，以及也为 Office 365 高级威胁防护 (Office 365 ATP 客户提供的更强大的 ATP) 防钓鱼策略。 邮件还会通过对恶意软件、垃圾邮件、网络钓鱼等进行多次检测扫描。鉴于所有此活动，可能会混淆策略所应用于的对象。

通常情况下，应用于邮件的策略在"CAT 和类别和属性的**X-Forefront-Antispam-Report"****标头)  (标识**。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

确定对邮件应用哪个策略有两个主要因素：

- **电子邮件保护类型的优先级：** 此顺序不可配置，下表中进行了详细介绍：

  ****

  |Priority|电子邮件保护|类别|管理位置|
  |---|---|---|---|
  |1|恶意软件|CAT：MALW|[在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)|
  |2|网络钓鱼|CAT：PHSH|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |3|高可信度垃圾邮件|CAT：HSPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |4 |网络钓鱼|CAT：SPOOF|[在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)|
  |5 |垃圾邮件|CAT：SPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |6 |批量邮件|CAT：BULK|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|域模拟 (受保护用户) |DIMP|[配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|用户模拟 (受保护的域) |UIMP|[配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup> 这些功能仅在 ATP 防钓鱼策略中提供。

- **策略的优先级：** 对于每种保护类型 (反垃圾邮件、反恶意软件、反网络钓鱼 ) 等，有一个适用于所有人的默认策略，但您可以创建应用于特定用户的自定义策略。 每个自定义策略都具有一个优先级值，用于确定应用策略时的顺序。 默认策略始终最后应用。

  如果用户在同一类型的多个策略中定义，则只会向其应用优先级最高的策略。 不会为用户查询该类型的任何其他策略 (包括默认策略) 。

例如，请考虑以下适用于相同用户的 ATP 防钓鱼 **策略以及**标识为用户模拟和欺骗邮件的邮件：

  ****

  |ATP 防钓鱼策略|Priority|用户模拟|反欺骗|
  |---|---|---|---|
  |策略 A|1|开|关|
  |策略 B|2|关|开|
  |

1. 该邮件将标记并视为欺骗邮件，因为欺骗的优先级高于用户模拟 (4) 4% (8) 。
2. 策略 A 应用于用户，因为它的优先级高于策略 B。
3. 根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中已禁用反欺骗。
4. 策略处理停止，因此策略 B 永远不会应用于用户。

由于有意或无意包括在同一类型的多个自定义策略中包含相同用户，请使用以下针对自定义策略的设计指南：

- 为适用于少量用户的策略分配较高优先级，并为适用于大量用户的策略分配较低优先级。 请记住，默认策略始终最后应用。
- 配置高优先级策略，使具有比低优先级策略更严格或更高级的设置。
- 请考虑使用更少 (的自定义策略，只对需要更严格或更专用设置的用户使用自定义) 。
