---
title: Microsoft 365 高级审核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 高级审核提供了新的审核功能，可帮助组织进行法庭与合规调查。
ms.openlocfilehash: 79c7e24349d3b6603e82946fda4a3c1f0c0ae6ff
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170512"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 高级审核

Microsoft 365 中的[统一审核](search-the-audit-log-in-security-and-compliance.md)功能可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。 现在通过发布 Microsoft 365 高级审核，我们增加了新的审核功能，可帮助你的组织进行法庭与合规调查。

> [!NOTE]
> 高级审核适用于具有 Office 365 或 Microsoft 365 企业版 E5 订阅的组织。 另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规加载项订阅分配至用户。

本文提供了这些高级审核功能的概览信息。

## <a name="long-term-retention-of-audit-logs"></a>长期保留审核日志

高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。 这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。 这有助于正在进行的法庭或合规调查。 有关详细信息，参见“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。

## <a name="audit-log-retention-policies"></a>审核日志保留策略

默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。 但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达一年。 可基于下列一个或多个条件创建保留审核记录的策略：

- 发生审核活动的 Microsoft 365 服务

- 特定的审核活动

- 执行审核活动的用户

还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。 另外注意，如果组织中的部分或全部用户需要保留 Exchange、SharePoint 或 Azure Active Directory 审核记录，则所有自定义审核日志保留策略将优先于默认的审核保留策略。 有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。

## <a name="access-to-crucial-events-for-investigations"></a>访问关键事件进行调查

关键安全和合规性相关审核事件可帮助你调查可能的违规或其他与法庭有关的调查。 我们发布的第一个此类关键事件是 *MailItemsAccessed* 邮箱审核事件。 邮件协议和客户端存取邮件数据时，触发此事件。 MailItemsAccessed 事件可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。 如果攻击者获得了对电子邮件的访问权限，MailItemsAccessed 事件将被触发，即使邮件实际上未被读取也是如此（即通过“绑定”或“同步” 记录到审核记录中的访问类型）。

新的 MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：

- MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。 MailItemsAccessed 适用于所有登录类型。

- MessageBind 只能由邮件客户端覆盖访问。 它不适用于同步活动。 “绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。

- 访问同一封电子邮件时，MessageBind 操作会触发多个审核记录，从而导致审核“噪音”。 相反，MailItemsAccessed 事件聚合在较少的审核记录中。

有关邮箱审核日志的详细信息，参见“[管理邮箱审核](enable-mailbox-auditing.md)”。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>高带宽访问 Office 365 管理活动 API

通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。 这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。

随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。 结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。 带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。

所有组织最初每分钟分配 2000 个请求基线。 根据组织的座位数和许可订阅，此限制将显著增加。 E5 组织获得的带宽是非 E5 组织的约两倍。 这也是最大宽带的上限，以保护服务的健康。

有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。
