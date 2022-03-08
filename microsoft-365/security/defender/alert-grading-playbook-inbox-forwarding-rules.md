---
title: 可疑收件箱转发规则的警报评分
description: 可疑收件箱转发规则的警报评分，查看警报并采取建议操作来修正攻击和保护你的网络。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
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
ms.openlocfilehash: 08178a1672e3bdd5b124138f698b42be8181373a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325497"
---
# <a name="alert-grading-for-suspicious-inbox-forwarding-rules"></a>可疑收件箱转发规则的警报评分

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

威胁参与者可以将遭到入侵的用户帐户用于多种恶意目的，包括阅读用户收件箱中的电子邮件、创建收件箱规则以将电子邮件转发到外部帐户、发送网络钓鱼邮件等。 恶意收件箱规则在 BEC (和网络钓鱼) 中广泛使用，并且必须持续监视这些规则。

本操作手册可帮助你调查可疑收件箱转发规则的警报，并快速将其评级为真正的误报 (TP) 或误报 (TP) 。 然后，你可以对 TP 警报采取建议操作来修正攻击。 

有关 Microsoft Defender for Office 365 和 Microsoft Defender for Cloud Apps 警报评分的概述，请参阅[简介文章](alert-grading-playbooks.md)。

使用此 Playbook 的结果为：

- 你已将与收件箱转发规则关联的警报标识为恶意 (TP) 活动 (恶意) 警报。

  如果恶意，则你已删除恶意收件箱转发规则。

- 如果电子邮件已转发到恶意电子邮件地址，你已进行必要的操作。

## <a name="inbox-forwarding-rules"></a>收件箱转发规则

配置收件箱规则以根据预定义条件自动管理电子邮件。 例如，可以创建收件箱规则，将经理的所有邮件移动到另一个文件夹中，或将接收的邮件转发到另一个电子邮件地址。

### <a name="suspicious-inbox-forwarding-rules"></a>可疑的收件箱转发规则

获取用户邮箱的访问权限后，攻击者通常会创建收件箱规则，允许其将敏感数据排除在外部电子邮件地址中，并用于恶意目的。 

恶意收件箱规则自动执行邮件删除过程。 使用特定规则，目标用户收件箱中符合规则条件的每封电子邮件将被转发到攻击者的邮箱。 例如，攻击者可能想要收集与财务相关的敏感数据。 他们创建收件箱规则，将主题或邮件正文中包含关键字（如"finance"和"invoice"）的所有电子邮件转发到其邮箱。

可疑收件箱转发规则可能很难检测，因为维护收件箱规则是用户完成常见任务。 因此，监视警报非常重要。 

## <a name="workflow"></a>工作流

下面是标识可疑电子邮件转发规则的工作流。
 
:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png" alt-text="收件箱转发规则的警报调查工作流" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png":::

## <a name="investigation-steps"></a>调查步骤

本节包含响应事件的详细分步指南，并采取了建议的步骤来保护组织免受进一步攻击。

### <a name="review-generated-alerts"></a>查看生成的警报

下面是警报队列中的收件箱转发规则警报的示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png" alt-text="警报队列中的通知示例" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png":::

下面是恶意收件箱转发规则触发的警报详细信息示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png" alt-text="恶意收件箱转发规则触发的警报的详细信息" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png":::

### <a name="investigate-rule-parameters"></a>调查规则参数 

此阶段的目的是确定规则是否按特定条件看起来可疑：

转发规则的收件人：

- 验证目标电子邮件地址不是同一用户拥有的其他邮箱 (可以避免用户在个人邮箱之间自转发电子邮件) 。 
- 验证目标电子邮件地址不是属于公司的内部地址或子域。

筛选器：
 
- 如果收件箱规则包含搜索电子邮件主题或正文中的特定关键字的筛选器，请检查所提供的关键字（如财务、凭据和网络等）是否似乎与恶意活动相关。 您可以在以下属性下找到这些筛选器 (在事件 RawEventData 列) 中显示："BodyContainsWords"、"SubjectContainsWords"或"SubjectOrBodyContainsWords"
- 如果攻击者选择不设置任何邮件筛选器，而收件箱规则将所有邮箱项目转发到攻击者的邮箱) ，则此行为也可疑。 

### <a name="investigate-ip-address"></a>调查 IP 地址

查看与执行规则创建相关事件的 IP 地址相关的属性：

1. 搜索源自租户中同一 IP 的其他可疑云活动。 例如，可疑活动可能是多次登录尝试失败。 
2. ISP 对于此用户是否常见和合理？
3. 此位置是否常见且合理？

### <a name="investigate-any-suspicious-activity-with-the-user-inbox-before-creating-rules"></a>在创建规则之前，调查用户收件箱的任何可疑活动

您可以在创建规则之前查看所有用户活动，检查泄露指示器，并调查看起来可疑的用户操作。 例如，多个登录失败。  

- 登录： 

  验证规则创建事件之前登录活动是否可疑 (如公用位置、ISP 或用户代理) 。 

- 其他警报或事件 

   - 在规则创建之前，用户触发了其他警报。 如果是这样，这可能表示用户受到威胁。 

   - 如果警报与其他警报关联以指示事件，那么事件是否包含其他真正的正警报？ 

## <a name="advanced-hunting-queries"></a>高级搜寻查询

[高级搜寻](advanced-hunting-overview.md) 是一种基于查询的威胁搜寻工具，允许你检查网络中事件并查找威胁指示器。 

运行此查询以查找特定时间窗口内的所有新收件箱规则事件。  

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

通过查看用户的历史记录，运行此查询来检查 ISP 是否适用于用户。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 30d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP 
```

通过查看用户的历史记录，运行此查询来检查用户是否常用国家/地区。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 30d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

运行此查询，通过查看用户的历史记录来检查用户代理是否适用于用户。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 30d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

运行此查询，检查其他用户是否将规则转发到同一目标 (可能会指示其他用户受到入侵以及) 。

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
2. 重置用户帐户凭据。 还可以验证用户帐户是否已被 Microsoft Defender for Cloud Apps 泄露，这将从 Identity Protection Azure Active Directory (Azure AD) 安全信号。
3. 搜索受影响用户执行的其他恶意活动。
4. 如果 ISP 不常 (，请检查租户中来自同一 IP 或同一 ISP) 活动，以查找其他遭到入侵的用户。

## <a name="see-also"></a>另请参阅

- [警报评分概述](alert-grading-playbooks.md)
- [可疑电子邮件转发活动](alert-grading-playbook-email-forwarding.md)
- [可疑的收件箱操作规则](alert-grading-playbook-inbox-manipulation-rules.md)
- [调查警报](investigate-alerts.md)
