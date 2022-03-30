---
title: 电子邮件保护的顺序和优先级
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， Microsoft 365 Defender 门户， Microsoft Defender for Endpoint， Microsoft Defender for Office 365， Microsoft Defender for Identity
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP Exchange Online Protection (中的保护) ，以及保护策略中的优先级值如何确定应用的策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1debec0d2f8ca1498fd674f3d5a2d5a4681196eb
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679777"
---
# <a name="order-and-precedence-of-email-protection"></a>电子邮件保护的顺序和优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在Microsoft 365邮箱位于 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，入站电子邮件可能会受到多种形式的保护标记。 例如，EOP 中可用于所有 Microsoft 365 客户的内置防钓鱼策略，以及 Microsoft Defender 为 Office 365 客户提供的更可靠的防钓鱼策略。 邮件还会通过恶意软件、垃圾邮件、网络钓鱼等的多个检测扫描。鉴于所有这些活动，可能会对应用哪个策略产生混淆。

通常，应用于邮件的策略在 CAT (Category 属性的 **X-Forefront-Antispam-Report** **标头)** 标识。 有关详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。

有两个主要因素可确定将哪个策略应用于邮件：

- **电子邮件保护类型的优先级**：此顺序不可配置，如下表所述：

  |优先级|电子邮件保护|类别|管理位置|
  |---|---|---|---|
  |1|恶意软件|CAT：MALW|[在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)|
  |2|网络钓鱼|CAT：PHSH|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |3|高可信度垃圾邮件|CAT：HSPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |4|网络钓鱼|CAT：SPOOF|[EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|用户模拟 (受保护的用户) |UIMP|[在 Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)|
  |6<sup>\*</sup>|域模拟 (受保护的域) |DIMP|[在 Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md)|
  |7 |垃圾邮件|CAT：SPM|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|
  |8 |批量邮件|CAT：BULK|[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)|

  <sup>\*</sup>这些功能仅在 Microsoft Defender for Office 365 中的反网络钓鱼策略中Office 365。

- 策略优先级：对于每种类型的策略 (反垃圾邮件、反恶意软件、防钓鱼等 ) ，都有一个适用于所有用户的默认策略，但你可以创建自定义策略来应用于特定用户。 每个自定义策略都有一个优先级值，用于确定策略的应用顺序。 默认策略始终应用最后。

  > [!IMPORTANT]
  > 如果用户在相同类型的多个策略中定义，则仅应用优先级最高的策略。 不会为用户评估此类型的任何剩余策略 (包括默认策略) 。

例如，请考虑适用于 Office 365 的 Microsoft Defender 中的以下防钓鱼策略，以及标识为用户模拟和欺骗的邮件：

|策略名称|优先级|用户模拟|反欺骗|
|---|---|---|---|
|策略 A|1|开|关|
|策略 B|2|关|开|

1. 邮件被标记为欺骗邮件并被视为欺骗邮件，因为欺骗的优先级 (4) 比 5 (高) 。
2. 策略 A 应用于用户，因为它的优先级高于策略 B。
3. 根据策略 A 中的设置，不会对邮件执行任何操作，因为策略中已关闭反欺骗。
4. 策略处理将停止，因此策略 B 从不应用于用户。

由于同一用户可能会有意或无意地包含在同一类型的多个自定义策略中，因此请对自定义策略使用以下设计准则：

- 为适用于少数用户的策略分配更高的优先级，为适用于大量用户的策略分配较低的优先级。 请记住，默认策略始终应用最后一个。
- 将高优先级策略配置为具有比较低优先级策略更严格或更专门的设置。
- 请考虑使用更少的自定义策略 (对需要更严格或更专门的设置的用户使用自定义) 。
