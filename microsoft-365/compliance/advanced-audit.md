---
title: Microsoft 365 高级审核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 高级审核提供了新的审核功能，可帮助组织进行法庭与合规调查。
ms.openlocfilehash: 0cfa6c1b672dabcbe5d5418461a0a55ea42867ab
ms.sourcegitcommit: 27eb93a7d46bcbb9c948a50b0a8481ffd3832ca0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2021
ms.locfileid: "61612616"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 高级审核

通过 Microsoft 365 中的 [统一审核功能](search-the-audit-log-in-security-and-compliance.md)，组织可以了解 Microsoft 365 众多不同服务中许多类型的审核活动。高级审核通过增加执行调查所需的审核日志保留期来帮助组织执行取证和合规性调查，提供对有助于确定泄露范围和更快访问 Office 365 管理活动 API 的重要事件的访问（通过使用 Microsoft 365 合规中心和 Office 365 管理活动 API）。

> [!NOTE]
> 高级审核适用于具有 Office 365 E5/A5/G5 或 Microsoft 365 企业版 E5/A5/G5 订阅的组织。 应为用户分配Microsoft 365 E5/A5/G5 合规性或 E5/A5/G5 电子数据展示和审核加载项许可证，以获取高级审核功能，例如长期保留审核日志和生成高级审核事件以进行调查。 有关许可的详细信息，请参阅：<br/>- [高级审核许可要求](auditing-solutions-overview.md#licensing-requirements)<br/>- [Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。

本文概述了“高级审核”功能，并展示了如何为“高级审核”设置用户。

## <a name="long-term-retention-of-audit-logs"></a>长期保留审核日志

高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。 这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。 长期保留审计记录，可以帮助进行取证或合规性调查。 有关详细信息，请参阅“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。

除了提供高级审核的一年保留功能，我们还发布了将审核日志保留 10 年的功能。 保留审核日志 10 年有助于对长期调查提供支持，并对监管、法律和内部义务作出响应。

> [!NOTE]
> 保留审核日志 10 年将需要每位用户额外的附加产品许可证。 将此许可证分配给用户并为其设置适当的 10 年审核日志保留策略后，该策略涵盖的审核日志开始保留 10 年。 此策略不是追溯性的，不能保留在创建 10 年审核日志保留策略之前生成的审核日志。 有关详细信息，请参阅本文中的[高级审核常见问题](#faqs-for-advanced-audit)部分。

### <a name="audit-log-retention-policies"></a>审核日志保留策略

默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。 但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达 10 年。 可基于下列一个或多个条件创建保留审核记录的策略：

- 发生审核活动的 Microsoft 365 服务。

- 特定的审核活动。

- 执行审核活动的用户。

还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。 另请注意，如果你需要为组织中的部分或所有用户保留 Exchange、SharePoint 或 Azure Active Directory 审计记录少于一年（或 10 年），那么任何自定义审核日志保留策略都将优先于默认的审核保留策略。 有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。

## <a name="advanced-audit-events"></a>高级审核事件

高级审核通过提供对重要事件（例如何时访问邮件项目、答复和转发邮件项目的时间以及用户在 Exchange Online 和 SharePoint Online 中搜索的时间和内容）的访问权限，帮助组织执行取证和合规性调查。 这些事件可帮助你调查可能的违规，并确定泄露的范围。 除了 Exchange 和 SharePoint 中的这些事件之外，其他Microsoft 365服务中还存在被视为重要事件的事件，并要求为用户分配[授予高级审核许可证](auditing-solutions-overview.md#licensing-requirements)。 必须为用户分配高级审核许可证，以便在用户执行这些事件时生成审核日志。

高级审核提供以下事件：

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

- [Microsoft 365 中的其他高级审核事件](#other-advanced-audit-events-in-microsoft-365)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

MailItemsAccessed 事件是邮箱审核操作，当邮件数据通过邮件协议和邮件客户端访问时，将触发该事件。 此事件可帮助调查人员识别数据泄露，并确定可能已泄露的邮件的范围。 如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。

MailItemsAccessed 事件将替换 Exchange Online 中邮箱审核日志记录中的 MessageBind，并提供以下改进：

- MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。 MailItemsAccessed 适用于所有登录类型。

- MessageBind 只能由邮件客户端覆盖访问。 它不适用于同步活动。 “绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。

- 访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。相反，MailItemsAccessed 事件会整合为在较少的审核记录。

有关 MailItemsAccessed 活动的审核记录的详细信息，请参阅[使用高级审核来调查被泄漏的帐户](mailitemsaccessed-forensics-investigations.md)。

若要搜索 MailItemsAccessed 审核记录，可以在 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“访问的邮箱项目”** 活动。

![在审核日志搜索工具中搜索 MailItemsAccessed 操作。](../media/AdvAudit_MailItemsAccessed.png)

此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) 命令。

### <a name="send"></a>Send

Send 事件也是邮箱审核操作，当用户执行以下操作之一时将被触发：

- 发送电子邮件

- 答复电子邮件

- 转发电子邮件

调查人员可使用发送事件识别从被泄露的帐户发送的电子邮件。 发送事件的审核记录中包含有关该邮件的信息，例如发送邮件的时间、InternetMessage ID、主题行以及邮件是否包含附件。 此审核信息可帮助调查人员识别从已泄露帐户发送的电子邮件或由攻击者发送的电子邮件的相关信息。 此外，调查人员可使用 Microsoft 365 电子数据展示工具搜索该邮件（通过使用主题行或邮件 ID）来标识该邮件的收件人和已发送邮件的实际内容。

若要搜索 Send 审核记录，可到 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“已发送邮件”** 活动。

![在审核日志搜索工具中搜索“已发送邮件”操作。](../media/AdvAudit_SentMessage.png)

此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) 命令。

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

当用户使用Outlook搜索邮箱中的项目时，会触发SearchQueryInitiatedExchange事件。 当在以下Outlook环境中执行搜索时，将触发事件：

- Outlook（桌面客户端）

- Outlook 网页版（OWA）

- Outlook for iOS

- Outlook for Android

- Windows 10的“邮件”应用

调查人员可使用 SearchQueryInitiatedExchange 事件来确定可能已泄露帐户的攻击者是否已查找或尝试访问邮箱中的敏感信息。 SearchQueryInitiatedExchange 事件的审核记录包含实际搜索查询文本等信息。 审计记录也显示了搜索所处的Outlook环境。 通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的电子邮件数据的意图。

若要搜索 SearchQueryInitiatedExchange 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的电子邮件搜索”** 活动。

![在审核日志搜索工具中搜索“已执行的电子邮件搜索”操作。](../media/AdvAudit_SearchExchange.png)

此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog)。

> [!NOTE]
> 必须启用对 SearchQueryInitiatedExchange 进行记录，以便可以在审核日志中搜索此事件。有关说明，请参阅 [设置高级审核](set-up-advanced-audit.md#step-2-enable-advanced-audit-events)。

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

与搜索邮箱项目类似，当有人在 SharePoint 中搜索项目时，会触发 SearchQueryInitiatedSharePoint 事件。 在以下类型的SharePoint站点中进行搜索时，将触发事件：

- 首页

- 通信网站

- 中心网站

- 与 Microsoft Teams 相关联的网站

调查人员可使用 SearchQueryInitiatedSharePoint 事件来确定攻击者是否试图在 SharePoint 中查找（并有可能访问）敏感信息。 SearchQueryInitiatedSharePoint 事件的审核记录中还包含实际搜索查询文本。 审计记录还显示所搜索的SharePoint站点的类型。 通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的文件数据的意图和范围。

若要搜索 SearchQueryInitiatedSharePoint 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的 SharePoint 搜索”** 活动。

![在审核日志搜索工具中搜索“已执行的 SharePoint 搜索”操作。](../media/AdvAudit_SearchSharePoint.png)

此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog)。

> [!NOTE]
> 必须启用对 SearchQueryInitiatedSharePoint 进行记录，以便可以在审核日志中搜索此事件。有关说明，请参阅 [设置高级审核](set-up-advanced-audit.md#step-2-enable-advanced-audit-events)。

### <a name="other-advanced-audit-events-in-microsoft-365"></a>Microsoft 365 中的其他高级审核事件

除了 Exchange Online 和 SharePoint Online 中的事件之外，在为用户分配适当的高级审核许可时，其他Microsoft 365服务中还记录了事件。 以下Microsoft 365服务提供高级审核事件。 选择相应的链接以转到标识和描述这些事件的文章。

- [Microsoft Forms](search-the-audit-log-in-security-and-compliance.md#microsoft-forms-activities)

- [Microsoft Stream](/stream/audit-logs#actions-logged-in-stream)

- [Microsoft Teams](/microsoftteams/audit-log-events#teams-activities)

- [Yammer](search-the-audit-log-in-security-and-compliance.md#yammer-activities)

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>高带宽访问 Office 365 管理活动 API

通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。 这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。

随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。 结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。 带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5/A5/G5 组织将获得比非 E5/A5/G5 组织更多的带宽。

所有组织最初每分钟分配 2000 个请求基线。 根据组织的座位数和许可订阅，此限制将显著增加。 E5/A5/G5 组织获得的带宽约为非 E5/A5/G5 组织的两倍。 这也是最大宽带的上限，以保护服务的健康。

有关更多信息，参见“[Office 365 管理活动 API](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。

## <a name="faqs-for-advanced-audit"></a>高级审核常见问题解答

**是否每位用户都需要 E5/A5/G5 许可证才能从高级审核中受益？**

若要从用户级高级审核功能中受益，需要向用户分配 E5/A5/G5 许可证。 有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。 例如，如果未向某个用户分配相应的许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。

**我的组织有 E5/A5/G5 订阅，我是否需要执行任何操作来访问高级审核事件的审核记录？**

对于分配了相应 E5/A5/G5 许可证的合格客户和用户，除了启用 SearchQueryInitiatedExchange 和 SearchQueryInitiatedSharePoint 事件之外，无需执行任何操作即可访问高级审核事件（如本文中所述）。 只有在分配了这些许可证后，才会为具有 E5/A5/G5 许可证的用户生成高级审核事件。

**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**

是的。 只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。

**当功能已向公众发布且在必需的附加产品许可证可用之前，如果我创建了 10 年审核日志保留策略，则组织的审核日志数据将会怎样？**

此功能在2020年最后一个季度正式发布，此后创建的审核日志数据，如果在10年审核日志保留策略涵盖范围内，都将保留 10 年。 这包括在 2021 年 3 月所需的附加许可证可以购买之前创建的 10 年审核日志保留策略。 但是，由于 10 年审核日志保留附加许可证现已可以购买，因此将需要为审核数据被 10 年审核保留策略涵盖的所有用户购买并分配附加许可证。
