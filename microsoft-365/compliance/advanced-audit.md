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
ms.openlocfilehash: 4812f81140bc80a1437c13b7bce38a7ed101592d
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280152"
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

关键安全和合规性相关审核事件可帮助你调查可能的违规或其他与法庭有关的调查。 我们发布的第一个此类关键事件是 *MailItemsAccessed* 邮箱审核操作。 邮件协议和邮件客户端访问邮件数据时，将触发此操作。 MailItemsAccessed 操作可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。 如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。

新的 MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：

- MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。 MailItemsAccessed 适用于所有登录类型。

- MessageBind 只能由邮件客户端覆盖访问。 它不适用于同步活动。 “绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。

- 访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。 相反，MailItemsAccessed 事件聚合在较少的审核记录中。

有关邮箱审核日志的详细信息，参见“[管理邮箱审核](enable-mailbox-auditing.md)”。

### <a name="search-for-mailitemsaccessed-audit-records"></a>搜索 MailItemsAccessed 审核记录

若要搜索 MailItemsAccessed 审核记录，可以在 Office 365 安全与合规中心内的[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的“**Exchange 邮箱活动**”下拉列表中搜索“**访问的邮箱项目**”活动。

![在审核日志搜索工具中搜索 MailItemsAccessed 操作](../media/MailItemsAccessedSCC1.png)

此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) 命令。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>高带宽访问 Office 365 管理活动 API

通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。 这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。

随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。 结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。 带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。

所有组织最初每分钟分配 2000 个请求基线。 根据组织的座位数和许可订阅，此限制将显著增加。 E5 组织获得的带宽是非 E5 组织的约两倍。 这也是最大宽带的上限，以保护服务的健康。

有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。

## <a name="faqs-for-advanced-audit"></a>高级审核常见问题解答

**可在何处访问高级审核？**

向你的组织推出高级审核后，你将能够使用 [Office 365 安全与合规中心](https://protection.office.com)中的审核日志搜索工具创建审核日志保留策略并搜索 MailItemsAccessed 审核记录。 我们正致力于在未来几周内将高级审核推出到 [Microsoft 365 合规中心](https://compliance.microsoft.com)。

**是否每位用户都需要 E5 许可证才能从高级审核中受益？**

若要从用户级高级审核功能中受益，需要向用户分配 E5 许可证。 有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。 例如，如果未向某个用户分配 E5 许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。

**为什么即使我们有 E5 订阅并为用户分配了 E5 许可证，我仍然在我的组织中看不到高级审核？**

很有可能在你的组织中无法使用高级审核功能（例如创建审核日志保留策略和记录 MailItemsAccessed 审核记录的功能），即使有正确的许可也是如此。 如果发生这种情况，是因为高级审核包尚未推出到你的组织。 这是暂时的许可回填问题，应该会在未来几周内针对受影响的组织予以解决。 若要缓解此问题，请对每个 E5 用户执行以下步骤：

1. 在 Microsoft 365 管理中心，转到 **“用户”>“活动用户”**，然后选择一个用户。

2. 在用户属性浮出页面上，单击“**许可证和应用**”。

3. 展开“**应用**”部分，然后执行下列操作之一：

   a. 如果未选中“**Microsoft 365 高级审核**”复选框，请将其选中，然后单击“**保存更改**”。 此用户的 MailItemsAccessed 操作审核记录应该会在 24 小时内可供搜索。

   b. 如果已选中“**Microsoft 365 高级审核**”复选框，请将其清除，然后单击“**保存更改**”。 请参阅步骤 4。

4. 如果已在步骤 3 中清除复选框，请等待 60 分钟，然后重复步骤 3a 以启用 Microsoft 365 高级审核应用。

**如果我的组织采用了将审核记录保留一年的私有预览计划，会发生什么情况？**

只要你不使用自定义审核保留策略来覆盖和更改预览计划中的审核保留策略，预览计划中的审核保留策略将持续存在。

**如果我的组织想要保留超过一年的审核日志，该怎么办？**

我们正在探索如何以及是否能为审核记录提供更长保留期的方案。 你可以通过 [Office 365 用户之声](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187)提供有关延长审核记录保留期的反馈。

**我的组织具有 E5 订阅，我是否需要执行任何操作才能获取 MailItemsAccessed 事件的审核记录的访问权限？**

符合条件的客户不需要执行任何操作即可访问 MailItemsAccessed 事件。 但是，如本主题中前面所述，由许可回填问题导致的延迟可能会阻止 MailItemsAccessed 事件的审核记录在审核日志搜索中返回。 如果发生这种情况，请按照“搜索 MailItemsAccessed 审核记录”部分的说明进行操作。

**你们是否计划在今年发布更多事件？**

是的，我们计划在未来几个月发布对调查至关重要的新事件。 临近发布日期时，我们将在 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)中发布有关这些新事件的信息。

**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**

是的。 只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。

**是否带宽越高意味着延迟改善和 SLA 提高？**

目前，高带宽可提供更好的管道，尤其是对于具有大量审核信号和明显消耗模式的组织。 这可能会改善延迟。 但是，不存在与高带宽相关的 SLA。 文档中已记录标准延迟，这些延迟不会随着高级审核的发布而改变。
