---
title: 可疑收件箱操作规则的警报评分
description: 可疑收件箱操作规则的警报评分，以查看警报并采取建议的操作来修正攻击并保护网络。
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
ms.openlocfilehash: e663d02037633599b9dffc19e1ebbd174aa279e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663173"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>可疑收件箱操作规则的警报评分

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

威胁执行组件可以将泄露的用户帐户用于许多恶意目的，包括读取用户收件箱中的电子邮件、创建收件箱规则以将电子邮件转发到外部帐户、删除跟踪以及发送网络钓鱼邮件。 在商业电子邮件泄露期间，恶意收件箱规则在 BEC) 和网络钓鱼活动 (很常见，因此必须一致地监视这些规则。

此 playbook 可帮助你调查与攻击者配置的可疑收件箱操作规则相关的任何事件，并采取建议的操作来修正攻击并保护网络。 此 playbook 适用于安全团队，包括安全运营中心 (SOC) 分析人员和 IT 管理员，他们查看、调查和评分警报。 可以快速将警报评分为 True Positive (TP) 或误报 (TP) ，并为 TP 警报采取建议的操作来修正攻击。

使用此 playbook 的结果如下：

- 你已将与收件箱操作规则关联的警报标识为恶意 (TP) 或良性 (FP) 活动。

  如果存在恶意，则已删除恶意收件箱操作规则。

- 如果已将电子邮件转发到恶意电子邮件地址，则已执行必要的操作。

## <a name="inbox-manipulation-rules"></a>收件箱操作规则

收件箱规则设置为根据预定义的条件自动管理电子邮件。 例如，可以创建收件箱规则，将管理器中的所有邮件移动到另一个文件夹，或将收到的消息转发到另一个电子邮件地址。

### <a name="malicious-inbox-manipulation-rules"></a>恶意收件箱操作规则

攻击者可能会设置电子邮件规则来隐藏被入侵用户邮箱中的传入电子邮件，以掩盖用户的恶意活动。 他们还可以在被入侵的用户邮箱中设置规则以删除电子邮件、将电子邮件移动到另一个不太明显的文件夹 (（如 RSS) ）或将邮件转发到外部帐户。 某些规则可能会将所有电子邮件移动到另一个文件夹，并将其标记为"读取"，而某些规则可能仅移动电子邮件或主题中包含特定关键字的邮件。

例如，收件箱规则可能设置为查找关键字，例如"发票"、"网络钓鱼"、"不回复"、"可疑电子邮件"或"垃圾邮件"等，并将其移动到外部电子邮件帐户。 攻击者还可能使用泄露的用户邮箱来分发垃圾邮件、网络钓鱼电子邮件或恶意软件。

## <a name="workflow"></a>工作流

下面是用于识别可疑收件箱操作规则活动的工作流。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="收件箱操作规则的警报调查工作流" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::

## <a name="investigation-steps"></a>调查步骤

本部分包含有关响应事件的详细分步指南，并采取建议的步骤保护组织免受进一步攻击。

### <a name="1-review-the-alerts"></a>1. 查看警报

下面是警报队列中收件箱操作规则警报的示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="收件箱操作规则的示例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

下面是恶意收件箱操作规则触发的警报的详细信息示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="恶意收件箱操作规则触发的警报详细信息" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::

### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. 调查收件箱操作规则参数

根据以下规则参数或条件确定规则是否可疑：

- 关键字

   攻击者可能仅将操作规则应用于包含某些单词的电子邮件。 可以在某些属性下找到这些关键字，例如："BodyContainsWords"、"SubjectContainsWords"或"SubjectOrBodyContainsWords"。

   如果按关键字进行筛选，请检查关键字是否看起来可疑 (常见方案是筛选与攻击者活动相关的电子邮件，如"网络钓鱼"、"垃圾邮件"、"不回复"等) 。

   如果没有筛选器，它也可能可疑。

- 目标文件夹

   为了逃避安全检测，攻击者可能会将电子邮件移动到不太明显的文件夹，并将电子邮件标记为读取 (例如"RSS"文件夹) 。 如果攻击者应用"MoveToFolder"和"MarkAsRead"操作，请检查目标文件夹是否与规则中的关键字有某种关系，以确定它是否看起来可疑。

- 全部删除

   某些攻击者只会删除所有传入的电子邮件以隐藏其活动。 大多数情况下，"删除所有传入电子邮件"而不使用关键字筛选它们的规则是恶意活动的指示器。

下面是有关事件日志的 RawEventData.Parameters) 上看到的"删除所有传入电子邮件"规则配置 (示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="删除所有传入电子邮件规则配置的示例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::

### <a name="3-investigate-the-ip-address"></a>3. 调查 IP 地址

查看执行规则创建相关事件的 IP 地址的属性：

- 搜索源自租户中同一 IP 的其他可疑云活动。 例如，可疑活动可能是多次失败的登录尝试。
- ISP 对于此用户是否常见且合理？
- 此用户的位置是否常见且合理？

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. 在创建规则之前调查用户的可疑活动

你可以在创建规则之前查看所有用户活动，检查是否存在泄露指标，并调查看似可疑的用户操作。

例如，对于多个失败的登录名，请检查：

- 登录活动

   验证创建规则之前的登录活动是否不可疑。  (常见位置/ISP/用户代理) 。

- 警报

   在创建规则之前检查用户是否收到警报。 这可能表示用户帐户可能遭到入侵。 例如，不可能的旅行警报、不频繁的国家/地区、多个失败的登录名等。) 

- 事件

   检查警报是否与指示事件的其他警报相关联。 如果是，请检查事件是否包含其他真实的正面警报。

## <a name="advanced-hunting-queries"></a>高级搜寻查询

[高级搜寻](advanced-hunting-overview.md) 是一种基于查询的威胁搜寻工具，可用于检查网络中的事件以查找威胁指示器。

使用此查询可在特定时间段内查找所有新的收件箱规则事件。

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

*RuleConfig* 列将提供新的收件箱规则配置。

使用此查询通过查看用户的历史记录来检查 ISP 是否为用户常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

通过查看用户的历史记录，使用此查询检查用户的国家/地区是否常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

使用此查询通过查看用户的历史记录来检查用户代理是否常见。

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

## <a name="recommended-actions"></a>建议的操作

1. 禁用恶意收件箱规则。
2. 重置用户帐户的凭据。 还可以验证用户帐户是否已因Microsoft Defender for Cloud Apps而泄露，这会从标识保护Azure Active Directory (Azure AD) 获取安全信号。
3. 搜索受影响的用户帐户执行的其他恶意活动。
4. 如果 ISP 不常见，请检查租户中源自同一 IP 或同一 ISP (的其他可疑活动，) 查找其他已泄露的用户帐户。

## <a name="see-also"></a>另请参阅

- [警报评分概述](alert-grading-playbooks.md)
- [可疑电子邮件转发活动](alert-grading-playbook-email-forwarding.md)
- [可疑的收件箱转发规则](alert-grading-playbook-inbox-forwarding-rules.md)
- [调查警报](investigate-alerts.md)
