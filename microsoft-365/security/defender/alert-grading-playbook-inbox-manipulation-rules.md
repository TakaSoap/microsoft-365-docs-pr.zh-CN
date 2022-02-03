---
title: 可疑收件箱操作规则的警报评分
description: 可疑收件箱操作规则的警报评分，查看警报并采取建议操作来修正攻击和保护你的网络。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 102731beb6da535e91ad197379a08d4d0f7cddfe
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355106"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>可疑收件箱操作规则的警报评分

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

威胁参与者可以将遭到入侵的用户帐户用于许多恶意目的，包括阅读用户收件箱中的电子邮件、创建收件箱规则以将电子邮件转发到外部帐户、删除跟踪和发送网络钓鱼邮件。 恶意收件箱规则在 BEC (和网络钓鱼) 中很常见，并且必须持续监视它们。 

本操作手册可帮助你调查与攻击者配置的可疑收件箱操作规则相关的任何事件，并采取建议的操作来修正攻击和保护你的网络。 本手册适用于安全团队，包括安全运营中心 (SOC) 查看、调查和评级警报的分析师和 IT 管理员。 你可以将警报快速分级为真正的误报 (TP) 或误报 (TP) 并针对 TP 警报采取建议操作以修正攻击。 

使用此 Playbook 的结果为：

- 你已将与收件箱操作规则关联的警报标识为恶意 (TP) 或恶意 (FP) 活动。

  如果恶意，则你已删除恶意收件箱操作规则。

- 如果电子邮件已转发到恶意电子邮件地址，你已进行必要的操作。

## <a name="inbox-manipulation-rules"></a>收件箱操作规则

收件箱规则设置为根据预定义条件自动管理电子邮件。 例如，可以创建收件箱规则，将经理的所有邮件移动到另一个文件夹中，或将接收的邮件转发到另一个电子邮件地址。

### <a name="malicious-inbox-manipulation-rules"></a>恶意收件箱操作规则

攻击者可能会设置电子邮件规则来隐藏受损用户邮箱中的传入电子邮件，以向用户隐藏其恶意活动。 他们还可能在受损的用户邮箱中设置规则，以删除电子邮件、将电子邮件移动到另一个不太明显的文件夹 (如 RSS) ，或将邮件转发到外部帐户。 某些规则可能会将所有电子邮件移动到另一个文件夹，并标记为"已读"，而某些规则可能仅移动电子邮件或主题中包含特定关键字的邮件。 

例如，收件箱规则可能设置为查找"发票"、"网络钓鱼"、"不答复"、"可疑电子邮件"或"垃圾邮件"等关键字，然后将它们移动到外部电子邮件帐户。 攻击者也可能使用遭到入侵的用户邮箱来分发垃圾邮件、网络钓鱼电子邮件或恶意软件。 

## <a name="workflow"></a>工作流

下面是用于标识可疑收件箱操作规则活动的工作流。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="收件箱操作规则的警报调查工作流" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::


## <a name="investigation-steps"></a>调查步骤

本节包含响应事件的详细分步指南，并采取了建议的步骤来保护组织免受进一步攻击。

### <a name="1-review-the-alerts"></a>1. 查看警报

下面是警报队列中的收件箱操作规则警报的示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="收件箱操作规则示例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

下面是恶意收件箱操作规则触发的警报的详细信息示例。

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="恶意收件箱操作规则触发的警报的详细信息" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::


### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. 调查收件箱操作规则参数 

根据以下规则参数或条件确定规则是否看起来可疑：

- Keywords

   攻击者可能仅将操作规则应用于包含特定词语的电子邮件。 可以在某些属性下找到这些关键字，例如："BodyContainsWords"、"SubjectContainsWords"或"SubjectOrBodyContainsWords"。 

   如果存在按关键字筛选的关键字，请检查关键字是否看起来可疑 (常见方案是筛选与攻击者活动相关的电子邮件，例如"网络钓鱼"、"垃圾邮件"、"不回复"等) 。

   如果没有任何筛选器，也可能可疑。

- 目标文件夹

   为了规避安全检测，攻击者可能会将电子邮件移动到不太明显的文件夹，将电子邮件标记为已读 (例如，"RSS"文件夹) 。 如果攻击者应用"MoveToFolder"和"MarkAsRead"操作，请检查目标文件夹是否以某种方式与规则中的关键字相关，以确定它是否看起来可疑。 

- 全部删除

   某些攻击者将仅删除传入的所有电子邮件以隐藏其活动。 大多数情况下，"删除所有传入电子邮件"而不使用关键字筛选它们的规则是恶意活动的指示器。 
 
下面是"删除所有传入电子邮件"规则配置示例 (，如相关事件日志的 RawEventData.Parameters) 所示。 

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="删除所有传入电子邮件规则配置的示例" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::


### <a name="3-investigate-the-ip-address"></a>3. 调查 IP 地址

查看执行规则创建相关事件的 IP 地址的属性：

- 搜索源自租户中同一 IP 的其他可疑云活动。 例如，可疑活动可能是多次登录尝试失败。 
- ISP 对于此用户是否常见和合理？
- 此位置是否常见且合理？

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. 在创建规则之前调查用户的可疑活动

您可以在创建规则之前查看所有用户活动，检查泄露指示器，并调查看起来可疑的用户操作。 

例如，对于多个登录失败，请检查： 

- 登录活动 

   验证规则创建之前登录活动是否可疑。  (公用位置/ISP/用户代理) 。 

- 警报

   在创建规则之前，检查用户是否收到警报。 这可能表示用户帐户可能受到威胁。 例如，不可能的旅行警报、不频繁的国家/地区、多次登录失败等) 

- 事件

   检查警报是否与指示事件的其他警报关联。 如果是，则检查事件是否包含其他真正的正警报。

## <a name="advanced-hunting-queries"></a>高级搜寻查询

[高级搜寻](advanced-hunting-overview.md) 是一种基于查询的威胁搜寻工具，允许你检查网络中事件以查找威胁指示器。 

使用此查询可查找特定时间窗口内的所有新收件箱规则事件。  

```kusto
let start_date = now(-10h); 
let end_date = now();
let user_id = ""; // enter here the user id
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where AccountObjectId == user_id
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
```

*RuleConfig* 列将提供新的收件箱规则配置。

通过查看用户的历史记录，使用此查询来检查 ISP 是否适用于用户。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP 
```

通过查看用户的历史记录，使用此查询来检查用户是否常用国家/地区。

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

使用此查询通过查看用户的历史记录来检查用户代理对于用户是否常见。

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
2. 重置用户帐户的凭据。 还可以验证用户帐户是否已被 Microsoft Defender for Cloud Apps 泄露，这将从 Identity Protection 获取Azure Active Directory (Azure AD) 信号。
3. 搜索受影响用户帐户执行的其他恶意活动。
4. 如果 ISP 不常 (则检查来自同一 IP 或同一 ISP) 的其他可疑活动，以查找其他遭到入侵的用户帐户。

## <a name="see-also"></a>另请参阅

- [警报评分概述](alert-grading-playbooks.md)
- [可疑电子邮件转发活动](alert-grading-playbook-email-forwarding.md)
- [可疑收件箱转发规则](alert-grading-playbook-inbox-forwarding-rules.md)
- [调查警报](investigate-alerts.md)
