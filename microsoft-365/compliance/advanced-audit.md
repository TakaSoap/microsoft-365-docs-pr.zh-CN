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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365 高级审核提供了新的审核功能，可帮助组织进行法庭与合规调查。
ms.openlocfilehash: bd92d8d471af07d6be252390f0be0764e6b320f7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200301"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 高级审核

Microsoft 365 中的[统一审核](search-the-audit-log-in-security-and-compliance.md)功能可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。 高级审核可通过增强执行调查所需的审核日志保留期来帮助组织执行取证和合规性调查，提供对有助于确定泄露范围和快速访问 Office 365 管理活动 API 的重要事件的访问。

> [!NOTE]
> 高级审核适用于具有 Office 365 E5 或 Microsoft 365 企业版 E5 订阅的组织。 另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规或 E5 电子数据展示和审核附加产品许可证分配至用户。 有关许可的详细信息，请参阅[适用于安全与合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。

本文提供了高级审核功能的概览信息。

## <a name="long-term-retention-of-audit-logs"></a>长期保留审核日志

高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。 这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。 长期保留审计记录，可以帮助进行取证或合规性调查。 有关详细信息，请参阅“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。

我们还发布了保留审核日志 10 年的功能。 “保留审核日志 10 年”有助于支持长期的调查，并对监管、法律和内部义务作出响应。

> [!NOTE]
> 保留审核日志 10 年将需要额外的附加产品许可证。 此新许可证将于 2021 年初推出。 有关详细信息，请参阅本文中的[高级审核常见问题](#faqs-for-advanced-audit)部分。

### <a name="audit-log-retention-policies"></a>审核日志保留策略

默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。 但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达 10 年。 可基于下列一个或多个条件创建保留审核记录的策略：

- 发生审核活动的 Microsoft 365 服务。

- 特定的审核活动。

- 执行审核活动的用户。

还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。 另请注意，如果你需要为组织中的部分或所有用户保留 Exchange、SharePoint 或 Azure Active Directory 审计记录少于一年（或 10 年），那么任何自定义审核日志保留策略都将优先于默认的审核保留策略。 有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。

## <a name="access-to-crucial-events-for-investigations"></a>访问关键事件进行调查

高级审核可帮助组织通过提供对重要事件的访问，例如访问邮件项目的时间，或邮件项目被回复和转发的时间，以及用户在 Exchange Online 和 SharePoint Online 中的搜索时间和内容，来执行取证和合规性调查。 这些关键事件可以帮助你调查可能的违规行为，并确定泄露的范围。  高级审核提供以下重要事件：

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

MailItemsAccessed 事件是邮箱审核操作，当邮件数据通过邮件协议和邮件客户端访问时，将触发该事件。 MailItemsAccessed 操作可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。 如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。

MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：

- MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。 MailItemsAccessed 适用于所有登录类型。

- MessageBind 只能由邮件客户端覆盖访问。 它不适用于同步活动。 “绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。

- 访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。 相反，MailItemsAccessed 事件聚合在较少的审核记录中。

有关 MailItemsAccessed 活动的审核记录的详细信息，请参阅[使用高级审核来调查被泄漏的帐户](mailitemsaccessed-forensics-investigations.md)。

若要搜索 MailItemsAccessed 审核记录，可以在 Microsoft 365 合规中心，在[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“访问的邮箱项目”** 活动。

![在审核日志搜索工具中搜索 MailItemsAccessed 操作](../media/AdvAudit_MailItemsAccessed.png)

此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。

### <a name="send"></a>Send

Send 事件也是邮箱审核操作，当用户执行以下操作之一时将被触发：

- 发送电子邮件

- 答复电子邮件

- 转发电子邮件

调查人员可使用发送事件识别从被泄露的帐户发送的电子邮件。 发送事件的审核记录中包含有关该邮件的信息，例如发送邮件的时间、InternetMessage ID、主题行以及邮件是否包含附件。 此审核信息可帮助调查人员识别从已泄露帐户发送的电子邮件或由攻击者发送的电子邮件的相关信息。 此外，调查人员可使用 Microsoft 365 电子数据展示工具搜索该邮件（通过使用主题行或邮件 ID）来标识该邮件的收件人和已发送邮件的实际内容。

若要搜索 Send 审核记录，可到 Microsoft 365 合规中心，在[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“已发送邮件”** 活动。

![在审核日志搜索工具中搜索“已发送邮件”操作](../media/AdvAudit_SentMessage.png)

此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

当用户在 Outlook 或 Outlook 网页版中使用搜索栏搜索邮箱中的项目时，会触发 SearchQueryInitiatedExchange 事件。 调查人员可使用 SearchQueryInitiatedExchange 事件来确定可能已泄露帐户的攻击者是否已查找或尝试访问邮箱中的敏感信息。 SearchQueryInitiatedExchange 事件的审核记录包含实际搜索查询文本，以及是否在 Outlook 桌面客户端或 Outlook 网页版中执行搜索等信息。 通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的电子邮件数据的意图。

若要搜索 SearchQueryInitiatedExchange 审核记录，可到合规中心，在[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的电子邮件搜索”** 活动。

![在审核日志搜索工具中搜索“已执行的电子邮件搜索”操作](../media/AdvAudit_SearchExchange.png)

此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。

> [!NOTE]
> 必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedExchange 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

类似于搜索邮箱项目，当某人在组织中的 SharePoint 主页网站、Teams 网站、协作网站和中心网站中搜索项目时，会触发 SearchQueryInitiatedSharePoint 事件。 调查人员可使用 SearchQueryInitiatedSharePoint 事件来确定攻击者是否试图在 SharePoint 中查找（并有可能访问）敏感信息。 SearchQueryInitiatedSharePoint 事件的审核记录中还包含实际搜索查询文本。 通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的文件数据的意图和范围。

若要搜索 SearchQueryInitiatedSharePoint 审核记录，可到合规中心，在[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的 SharePoint 搜索”** 活动。

![在审核日志搜索工具中搜索“已执行的 SharePoint 搜索”操作](../media/AdvAudit_SearchSharePoint.png)

此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。

> [!NOTE]
> 必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedSharePoint 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>高带宽访问 Office 365 管理活动 API

通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。 这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。

随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。 结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。 带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。

所有组织最初每分钟分配 2000 个请求基线。 根据组织的座位数和许可订阅，此限制将显著增加。 E5 组织获得的带宽约为非 E5 组织的两倍。 这也是最大宽带的上限，以保护服务的健康。

有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。

## <a name="faqs-for-advanced-audit"></a>高级审核常见问题解答

**是否每位用户都需要 E5 许可证才能从高级审核中受益？**

若要从用户级高级审核功能中受益，需要向用户分配 E5 许可证。 有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。 例如，如果未向某个用户分配 E5 许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。

**我的组织具有 E5 订阅，我是否需要执行任何操作才能获取重要事件的审核记录的访问权限？**

符合条件的客户不需要执行任何操作即可访问重要的审核事件。 但是，如本主题中前面所述，由许可回填问题导致的延迟可能会阻止重要事件的审核记录在审核日志搜索中返回。 如果发生这种情况，请按照之前的常见问题中有关临时许可回填问题的说明进行操作。

**何时会推出新的 10 年审核日志保留附加产品许可证？**

2021 年初，拥有 E5 订阅的客户可购买新的 10 年审核日志保留附加产品。

**如果此功能发布了常规可用性，但在 2021 年初推出所需的附加许可证前，我创建了 10 年审核日志保留策略，组织的审核日志数据会发生什么情况？**

常规可用性后创建的 10 年审核日志保留策略覆盖的任何审核日志数据都将保留 10 年。 在 2021 年初推出 10 年审核日志保留附加产品许可证时，你需要为审核数据由现有的 10 年审核保留策略所保留的用户购买附加产品许可证。 此外，在 2021 年初推出附加许产品可证后，创建新的 10 年审核日志保留策略时，将强制实施相应的许可证。

**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**

是的。 只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。

**是否带宽越高意味着延迟改善和 SLA 提高？**

目前，高带宽可提供更好的管道，尤其是对于具有大量审核信号和明显消耗模式的组织。 带宽增加将改善延迟状况。 但是不存在与高带宽相关的 SLA。 文档中已记录标准延迟，这些延迟不会随着高级审核的发布而改变。
