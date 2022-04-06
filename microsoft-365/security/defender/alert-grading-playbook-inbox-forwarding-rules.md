---
title: 可疑收件箱转发规则的警报评分
description: 可疑收件箱转发规则的警报评分，以查看警报并采取建议的操作来修正攻击并保护网络。
keywords: 事件， 警报， 调查， 分析， 响应， 相关性， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: dca305b88e6e8db25e0a798c4361086bd7cb1e8b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666011"
---
# <a name="alert-grading-for-suspicious-inbox-forwarding-rules"></a>可疑收件箱转发规则的警报评分

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

威胁执行组件可以将泄露的用户帐户用于多个恶意目的，包括读取用户收件箱中的电子邮件、创建收件箱规则以将电子邮件转发到外部帐户、发送网络钓鱼邮件等。 在商业电子邮件泄露期间，恶意收件箱规则 (BEC) 和网络钓鱼活动中很常见，并且必须一致地监视它们。

此 playbook 可帮助你调查可疑收件箱转发规则的警报，并快速将其评分为 True Positive (TP) 或误报 (TP) 。 然后，可以针对 TP 警报采取建议的操作来修正攻击。

有关Microsoft Defender for Office 365和Microsoft Defender for Cloud Apps警报评分的概述，请参阅[简介文章](alert-grading-playbooks.md)。

使用此 playbook 的结果如下：

- 你已将与收件箱转发规则关联的警报标识为恶意 (TP) 或良性 (FP) 活动。

  如果存在恶意，则已删除恶意收件箱转发规则。

- 如果已将电子邮件转发到恶意电子邮件地址，则已执行必要的操作。

## <a name="inbox-forwarding-rules"></a>收件箱转发规则

你将收件箱规则配置为根据预定义的条件自动管理电子邮件。 例如，可以创建收件箱规则，将管理器中的所有邮件移动到另一个文件夹，或将收到的消息转发到另一个电子邮件地址。

### <a name="suspicious-inbox-forwarding-rules"></a>可疑的收件箱转发规则

获得对用户邮箱的访问权限后，攻击者通常会创建一个收件箱规则，允许他们将敏感数据外泄到外部电子邮件地址，并将其用于恶意目的。

恶意收件箱规则自动执行外泄过程。 使用特定规则时，目标用户收件箱中与规则条件匹配的每封电子邮件都将转发到攻击者的邮箱。 例如，攻击者可能想要收集与财务相关的敏感数据。 创建收件箱规则，将包含关键字（如主题或邮件正文中的"finance"和"invoice"）的所有电子邮件转发到其邮箱。

可疑的收件箱转发规则可能很难检测，因为维护收件箱规则是用户执行的常见任务。 因此，监视警报非常重要。

## <a name="workflow"></a>工作流

下面是用于识别可疑电子邮件转发规则的工作流。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png" alt-text="收件箱转发规则的警报调查工作流" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png":::

## <a name="investigation-steps"></a>调查步骤

本部分包含有关响应事件的详细分步指南，并采取建议的步骤保护组织免受进一步攻击。

### <a name="review-generated-alerts"></a>查看生成的警报

下面是警报队列中收件箱转发规则警报的示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png" alt-text="警报队列中的通知示例" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png":::

下面是恶意收件箱转发规则触发的警报详细信息的示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png" alt-text="恶意收件箱转发规则触发的警报详细信息" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png":::

### <a name="investigate-rule-parameters"></a>调查规则参数

此阶段的目的是根据某些条件确定规则是否看起来可疑：

转发规则的收件人：

- 验证目标电子邮件地址不是同一用户拥有的其他邮箱 (避免用户在个人邮箱) 之间自转电子邮件的情况。
- 验证目标电子邮件地址不是属于公司的内部地址或子域。

过滤 器：

- 如果收件箱规则包含在电子邮件的主题或正文中搜索特定关键字的筛选器，请检查所提供的关键字（如财务、凭据和网络等）是否似乎与恶意活动相关。 可以在以下属性下找到这些筛选器 (显示在事件 RawEventData 列) ："BodyContainsWords"、"SubjectContainsWords"或"SubjectOrBodyContainsWords"
- 如果攻击者选择不将任何筛选器设置为邮件，而收件箱规则则将所有邮箱项目转发到攻击者的邮箱) ，则此行为也是可疑的。

### <a name="investigate-ip-address"></a>调查 IP 地址

查看与执行规则创建相关事件的 IP 地址相关的属性：

1. 搜索源自租户中同一 IP 的其他可疑云活动。 例如，可疑活动可能是多次失败的登录尝试。
2. ISP 对于此用户是否常见且合理？
3. 此用户的位置是否常见且合理？

### <a name="investigate-any-suspicious-activity-with-the-user-inbox-before-creating-rules"></a>在创建规则之前，使用用户收件箱调查任何可疑活动

你可以在创建规则之前查看所有用户活动，检查是否有泄露指示器，并调查看似可疑的用户操作。 例如，多次登录失败。

- 登录：

  验证规则创建事件之前的登录活动是否不可疑 (，例如常见位置、ISP 或用户代理) 。

- 其他警报或事件
  - 创建规则之前，是否为用户触发了其他警报。 如果是这样，则这可能表示用户遭到入侵。
  - 如果警报与其他警报关联以指示事件，则该事件是否包含其他真正的积极警报？

## <a name="advanced-hunting-queries"></a>高级搜寻查询

[高级搜寻](advanced-hunting-overview.md) 是一种基于查询的威胁搜寻工具，可用于检查网络中的事件并查找威胁指示器。

运行此查询，在特定时间段内查找所有新的收件箱规则事件。

```kusto
let start_date = now(-10h);
let end_date = now();
let user_id = ""; // enter here the user id
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where AccountObjectId == user_id
| where Application == @"Microsoft Exchange Online"
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
```

*RuleConfig* 将包含规则配置。

运行此查询，通过查看用户的历史记录来检查 ISP 是否为用户常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

运行此查询，通过查看用户的历史记录来检查用户的国家/地区是否常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

运行此查询，通过查看用户的历史记录来检查用户代理是否常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

运行此查询以检查其他用户是否创建了指向同一目标的转发规则 (可能指示其他用户遭到入侵以及) 。

```kusto
let start_date = now(-10h);
let end_date = now();
let dest_email = ""; // enter here destination email as seen in the alert
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
| where RuleConfig has dest_email
```

## <a name="recommended-actions"></a>建议的操作

1. 禁用恶意收件箱规则。
2. 重置用户的帐户凭据。 还可以验证用户帐户是否已因Microsoft Defender for Cloud Apps而泄露，这会从标识保护Azure Active Directory (Azure AD) 获取安全信号。
3. 搜索受影响用户执行的其他恶意活动。
4. 如果 ISP 不常见，请检查租户中来自同一 IP 或同一 ISP (的其他可疑活动，) 查找其他遭到入侵的用户。

## <a name="see-also"></a>另请参阅

- [警报评分概述](alert-grading-playbooks.md)
- [可疑电子邮件转发活动](alert-grading-playbook-email-forwarding.md)
- [可疑的收件箱操作规则](alert-grading-playbook-inbox-manipulation-rules.md)
- [调查警报](investigate-alerts.md)
