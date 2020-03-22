---
title: Office 365 中的电子邮件保护的顺序和优先级
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 介绍 Office 365 保护的应用程序顺序，以及保护策略中的优先级值如何确定应用的策略。
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895331"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Office 365 中的电子邮件保护的顺序和优先级

作为 Office 365 用户，您的入站电子邮件可能会被多种保护形式标记。 例如，可用于所有 Office 365 客户的内置 EOP 反网络钓鱼策略，以及 Office 365 高级威胁防护客户也可以使用的更强健的 ATP 反网络钓鱼策略。 邮件还会通过多个检测扫描，针对恶意软件、垃圾邮件、网络钓鱼等。在所有此活动中，可能会对应用的策略产生一些混淆。

通常情况下，应用于邮件的策略在**CAT （Category）** 属性的**X-Forefront-反垃圾邮件报告**标头中标识。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

有两个主要因素可用于确定将哪个策略应用于邮件：

- **电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：

  |||||
  |---|---|---|---|
  |**Priority**|**电子邮件保护**|**类别**|**管理位置**|
  |1|恶意软件|CAT： MALW|[在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)|
  |双面|网络钓鱼|CAT： PHSH|[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |第三章|高可信度垃圾邮件|CAT： HSPM|[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |4 |网络钓鱼|分类程序：欺骗|[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md) <Br/><br/> [详细了解防欺骗智能](learn-about-spoof-intelligence.md)|
  |5 |垃圾邮件|CAT： SPM|[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |6 |批量邮件|分类程序：批量|[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |步<sup>\*</sup>|域模拟|DIMP|[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)|
  |utf-8<sup>\*</sup>|用户模拟|UIMP|[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>这些功能仅在 ATP 中可用。

- **策略的优先级**：对于每种保护类型（反垃圾邮件、反恶意软件、反网络钓鱼等），都有一个适用于每个人的默认策略，但您可以创建适用于特定用户的自定义策略。 每个自定义策略都有一个优先级值，用于确定策略在中的应用顺序。 默认策略总是最后应用。

  如果用户是在多个自定义策略中定义的，则仅对其应用具有最高优先级的策略。 不会为用户评估任何剩余的策略（包括默认策略）。

例如，请考虑以下**适用于相同用户**的反网络钓鱼策略，以及同时标识为用户模拟和哄骗的邮件：

  |||||
  |---|---|---|---|
  |**反垃圾邮件策略**|**Priority**|**用户模拟（ATP）**|**反欺骗（EOP）**|
  |策略 A|1|开|关闭|
  |Policy B|双面|关|开|
  |

1. 邮件被标记为欺骗，因为哄骗具有更高的优先级（4），而不是用户模拟（8）。
2. 策略 A 应用于用户，因为它的优先级高于优先级 B。
3. 根据策略 A 中的设置，不会对邮件执行任何操作，因为在策略中禁用了反欺骗功能。
4. 反垃圾邮件策略处理停止，因此策略 B 永远不会应用到用户。

由于有多个用户在同一类型的多个自定义策略中存在，因此请考虑针对自定义策略的以下设计准则：

- 为适用于少数用户的策略分配更高的优先级，并为应用于大量用户的策略分配较低的优先级。 请记住，默认策略总是最后应用。
- 配置更高优先级的策略，使其具有比低优先级策略更严格或更多的专用设置。
- 请考虑使用较少的自定义策略（仅对需要更严格或更多的 specialize 设置的用户使用自定义策略）。
