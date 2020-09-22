---
title: 电子邮件保护的顺序和优先级
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
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
description: 管理员可以了解 Exchange Online Protection (EOP) 中的应用程序保护顺序，以及保护策略中的优先级值如何确定应用的策略。
ms.openlocfilehash: e2da22bfbe0e7df70cf8d8b0d8cfd09eaf6e2ee3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196043"
---
# <a name="order-and-precedence-of-email-protection"></a>电子邮件保护的顺序和优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，入站电子邮件可能会被多种保护形式标记。 例如，可供所有 Microsoft 365 客户使用的内置 EOP 反网络钓鱼策略，以及在 Office 365 高级威胁防护中也可用于 Office 高级威胁防护 (Office 365 ATP) 客户的更强健的 ATP 反网络钓鱼策略。 邮件还会通过多个检测扫描，针对恶意软件、垃圾邮件、网络钓鱼等。在所有此活动中，可能会对应用的策略产生一些混淆。

通常情况下，应用于邮件的策略在**CAT (Category) **属性中的**X-Forefront-反垃圾邮件报告**标头中进行标识。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

有两个主要因素可用于确定将哪个策略应用于邮件：

- **电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：

  ****

  |Priority|电子邮件保护|类别|管理位置|
  |---|---|---|---|
  |1|恶意软件|CAT： MALW|[在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)|
  |2 |网络钓鱼|CAT： PHSH|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |第三章|高可信度垃圾邮件|CAT： HSPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |4 |网络钓鱼|分类程序：欺骗|[在 EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)|
  |5 |垃圾邮件|CAT： SPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |6 |批量邮件|分类程序：批量|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |步<sup>\*</sup>|域模拟 (受保护的用户) |DIMP|[配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)|
  |utf-8<sup>\*</sup>|用户模拟 (受保护的域) |UIMP|[配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup> 这些功能仅在 ATP 反网络钓鱼策略中可用。

- **策略的优先级**：对于每种保护类型 (反垃圾邮件、反恶意软件、反网络钓鱼等 ) ，有一个适用于每个人的默认策略，但您可以创建适用于特定用户的自定义策略。 每个自定义策略都有一个优先级值，用于确定策略在中的应用顺序。 默认策略总是最后应用。

  如果用户是在同一类型的多个策略中定义的，则仅对其应用具有最高优先级的策略。 该类型的任何剩余策略不会评估给用户 (包括默认策略) 。

例如，考虑以下 ATP 反网络钓鱼策略，这些策略 **适用于相同的用户**以及同时标识为用户模拟和哄骗的邮件：

  ****

  |ATP 反网络钓鱼策略|Priority|用户模拟|反欺骗|
  |---|---|---|---|
  |策略 A|1|开|关|
  |Policy B|2 |关|开|
  |

1. 邮件被标记为欺骗，因为哄骗的优先级高于用户模拟 (8)  (4) 。
2. 策略 A 应用于用户，因为它的优先级高于策略 B。
3. 根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中禁用了反欺骗功能。
4. 策略处理停止，因此策略 B 永远不会应用到用户。

由于相同的用户可能有意或无意地包含在同一类型的多个自定义策略中，因此，请对自定义策略使用以下设计准则：

- 为适用于少数用户的策略分配更高的优先级，并为应用于大量用户的策略分配较低的优先级。 请记住，默认策略总是最后应用。
- 配置更高优先级的策略，使其具有比低优先级策略更严格或更多的专用设置。
- 请考虑使用较少的自定义策略 (仅对需要更严格或更多专用设置) 的用户使用自定义策略。
