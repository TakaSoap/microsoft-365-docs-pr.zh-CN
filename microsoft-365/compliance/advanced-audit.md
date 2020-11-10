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
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 高级审核提供了新的审核功能，可帮助组织进行法庭与合规调查。
ms.openlocfilehash: 51ec75cc8d8ae554ea9cbef3a9ea2aa18171e70a
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950991"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="8ecfd-103">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="8ecfd-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="8ecfd-p101">Microsoft 365 中的[统一审核功能](search-the-audit-log-in-security-and-compliance.md)可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。高级审核可通过增强执行调查所需的审核日志保留期来帮助组织执行取证和合规性调查，提供对有助于确定泄露范围和快速访问 Office 365 管理活动 API 的重要事件的访问。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p101">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365. Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="8ecfd-p102">高级审核适用于具有 Office 365 E5 或 Microsoft 365 企业版 E5 订阅的组织。另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规或 E5 电子数据展示和审核附加产品许可证分配至用户。有关许可的详细信息，请参阅[适用于安全与合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p102">Advanced Audit is available for organizations with an Office 365 E5 or Microsoft 365 Enterprise E5 subscription. Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations. For more information about licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="8ecfd-109">本文提供了高级审核功能的概览信息。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-109">This article provides an overview of Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="8ecfd-110">长期保留审核日志</span><span class="sxs-lookup"><span data-stu-id="8ecfd-110">Long-term retention of audit logs</span></span>

<span data-ttu-id="8ecfd-p103">高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。这是通过默认审核日志保留策略来实现的，此策略将包含 **工作负载** 属性（表示发生活动的服务）的 **Exchange** 、 **SharePoint** 或 **AzureActiveDirectory** 值的所有审核记录保留一年。长期保留审计记录，可以帮助进行取证或合规性调查。有关详细信息，请参阅“ [管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”部分。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p103">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year. This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange** , **SharePoint** , or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year. Retaining audit records for longer periods can help with on-going forensic or compliance investigations. For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="8ecfd-p104">我们还发布了保留审核日志 10 年的功能。“保留审核日志 10 年”有助于支持长期的调查，并对监管、法律和内部义务作出响应。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p104">We're also releasing the capability to retain audit logs for 10 years. The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="8ecfd-p105">保留审核日志 10 年将需要额外的附加产品许可证。此新许可证将于 2021 年初推出。有关详细信息，请参阅本文中的[高级审核常见问题](#faqs-for-advanced-audit)部分。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p105">Retaining audit logs for 10 years will require an additional add-on license. This new license will be available in early 2021. For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="8ecfd-120">审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="8ecfd-120">Audit log retention policies</span></span>

<span data-ttu-id="8ecfd-p106">默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达 10 年。可基于下列一个或多个条件创建保留审核记录的策略：</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p106">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days. But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years. You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="8ecfd-124">发生审核活动的 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-124">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="8ecfd-125">特定的审核活动。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-125">Specific audited activities.</span></span>

- <span data-ttu-id="8ecfd-126">执行审核活动的用户。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-126">The user who performs an audited activity.</span></span>

<span data-ttu-id="8ecfd-p107">还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。另请注意，如果你需要为组织中的部分或所有用户保留 Exchange、SharePoint 或 Azure Active Directory 审计记录少于一年（或 10 年），那么任何自定义审核日志保留策略都将优先于默认的审核保留策略。有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p107">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies. Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization. For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="8ecfd-130">访问关键事件进行调查</span><span class="sxs-lookup"><span data-stu-id="8ecfd-130">Access to crucial events for investigations</span></span>

<span data-ttu-id="8ecfd-p108">高级审核可帮助组织通过提供对重要事件的访问，例如访问邮件项目的时间，或邮件项目被回复和转发的时间，以及用户在 Exchange Online 和 SharePoint Online 中的搜索时间和内容，来执行取证和合规性调查。这些关键事件可以帮助你调查可能的违规行为，并确定泄露的范围。高级审核提供以下重要事件：</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p108">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online. These crucial events can help you investigate possible breaches and determine the scope of compromise.  Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="8ecfd-134">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="8ecfd-134">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="8ecfd-135">Send</span><span class="sxs-lookup"><span data-stu-id="8ecfd-135">Send</span></span>](#send)

- [<span data-ttu-id="8ecfd-136">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="8ecfd-136">SearchQueryInitiatedExchange</span></span>](#searchqueryinitiatedexchange)

- [<span data-ttu-id="8ecfd-137">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="8ecfd-137">SearchQueryInitiatedSharePoint</span></span>](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a><span data-ttu-id="8ecfd-138">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="8ecfd-138">MailItemsAccessed</span></span>

<span data-ttu-id="8ecfd-p109">MailItemsAccessed 事件是邮箱审核操作，当邮件数据通过邮件协议和邮件客户端访问时，将触发该事件。MailItemsAccessed 操作可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p109">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients. The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised. If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="8ecfd-142">MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：</span><span class="sxs-lookup"><span data-stu-id="8ecfd-142">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="8ecfd-p110">MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。MailItemsAccessed 适用于所有登录类型。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p110">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions. MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="8ecfd-p111">MessageBind 只能由邮件客户端覆盖访问。它不适用于同步活动。“绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p111">MessageBind only covered access by a mail client. It didn't apply to sync activities. MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="8ecfd-p112">访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。相反，MailItemsAccessed 事件聚合在较少的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p112">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise". In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="8ecfd-150">有关 MailItemsAccessed 活动的审核记录的详细信息，请参阅[使用高级审核来调查被泄漏的帐户](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-150">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="8ecfd-151">若要搜索 MailItemsAccessed 审核记录，可以在 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“访问的邮箱项目”** 活动。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-151">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在审核日志搜索工具中搜索 MailItemsAccessed 操作](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="8ecfd-153">此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-153">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="8ecfd-154">Send</span><span class="sxs-lookup"><span data-stu-id="8ecfd-154">Send</span></span>

<span data-ttu-id="8ecfd-155">Send 事件也是邮箱审核操作，当用户执行以下操作之一时将被触发：</span><span class="sxs-lookup"><span data-stu-id="8ecfd-155">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="8ecfd-156">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="8ecfd-156">Sends an email message</span></span>

- <span data-ttu-id="8ecfd-157">答复电子邮件</span><span class="sxs-lookup"><span data-stu-id="8ecfd-157">Replies to an email message</span></span>

- <span data-ttu-id="8ecfd-158">转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="8ecfd-158">Forwards an email message</span></span>

<span data-ttu-id="8ecfd-p113">调查人员可使用发送事件识别从被泄露的帐户发送的电子邮件。发送事件的审核记录中包含有关该邮件的信息，例如发送邮件的时间、InternetMessage ID、主题行以及邮件是否包含附件。此审核信息可帮助调查人员识别从已泄露帐户发送的电子邮件或由攻击者发送的电子邮件的相关信息。此外，调查人员可使用 Microsoft 365 电子数据展示工具搜索该邮件（通过使用主题行或邮件 ID）来标识该邮件的收件人和已发送邮件的实际内容。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p113">Investigators can use the Send event to identify email sent from a compromised account. The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments. This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker. Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="8ecfd-163">若要搜索 Send 审核记录，可到 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的“ **Exchange 邮箱活动** ”下拉列表中，搜索“ **已发送邮件** ”活动。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-163">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在审核日志搜索工具中搜索“已发送邮件”操作](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="8ecfd-165">此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-165">You can also run the [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="8ecfd-166">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="8ecfd-166">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="8ecfd-p114">当用户在 Outlook 网页版 (OWA) 中使用搜索栏搜索邮箱中的项目时，会触发 SearchQueryInitiatedExchange 事件。调查人员可使用 SearchQueryInitiatedExchange 事件来确定可能已盗用帐户的攻击者是否已查找或尝试访问邮箱中的敏感信息。SearchQueryInitiatedExchange 事件的审核记录包含实际搜索查询文本等信息。通过查看攻击者可能已执行的搜索查询，调查员可更清晰地了解遭到搜索的电子邮件数据的意图。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p114">The SearchQueryInitiatedExchange event is triggered when a person uses the Search bar in Outlook on the web (OWA) to search for items in a mailbox. Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox. The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="8ecfd-171">若要搜索 SearchQueryInitiatedExchange 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的“ **搜索活动** ”下拉列表中，搜索“ **已执行的电子邮件搜索** ”活动。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-171">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在审核日志搜索工具中搜索“已执行的电子邮件搜索”操作](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="8ecfd-173">此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-173">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="8ecfd-174">必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedExchange 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-174">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="8ecfd-175">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="8ecfd-175">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="8ecfd-p115">与搜索邮箱项目类似，当有人在组织中的 SharePoint 主页网站搜索项目时，会触发 SearchQueryInitiatedSharePoint 事件。调查人员可使用 SearchQueryInitiatedSharePoint 事件来确定攻击者是否试图在 SharePoint 中查找（并有可能访问）敏感信息。SearchQueryInitiatedSharePoint 事件的审核记录中还包含实际搜索查询文本。通过查看攻击者可能已执行的搜索查询，调查员可更清晰地了解遭到搜索的文件数据的意图和范围。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p115">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in the SharePoint home site for your organization. Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint. The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="8ecfd-180">若要搜索 SearchQueryInitiatedSharePoint 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的“ **搜索活动** ”下拉列表中，搜索“ **已执行的 SharePoint 搜索** ”活动。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-180">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在审核日志搜索工具中搜索“已执行的 SharePoint 搜索”操作](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="8ecfd-182">此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-182">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="8ecfd-183">必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedSharePoint 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-183">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedSharePoint events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="8ecfd-184">高带宽访问 Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="8ecfd-184">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="8ecfd-p116">通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p116">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level. This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="8ecfd-p117">随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p117">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit. The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data. The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="8ecfd-p118">所有组织最初每分钟分配 2000 个请求基线。根据组织的座位数和许可订阅，此限制将显著增加。E5 组织获得的带宽约为非 E5 组织的两倍。这也是最大宽带的上限，以保护服务的健康。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p118">All organizations are initially allocated a baseline of 2,000 requests per minute. This limit will dynamically increase depending on an organization's seat count and their licensing subscription. E5 organizations will get about twice as much bandwidth as non-E5 organizations. There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="8ecfd-194">有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-194">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="8ecfd-195">高级审核常见问题解答</span><span class="sxs-lookup"><span data-stu-id="8ecfd-195">FAQs for Advanced Audit</span></span>

<span data-ttu-id="8ecfd-196">**是否每位用户都需要 E5 许可证才能从高级审核中受益？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-196">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="8ecfd-p119">若要从用户级高级审核功能中受益，需要向用户分配 E5 许可证。有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。例如，如果未向某个用户分配 E5 许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-p119">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license. There are some capabilities that will check for the appropriate license to expose the feature for the user. For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="8ecfd-200">**我的组织具有 E5 订阅，我是否需要执行任何操作才能获取重要事件的审核记录的访问权限？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-200">**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="8ecfd-201">对于已分配相应许可证的符合条件的客户和用户，无需执行任何操作即可访问关键审核事件。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-201">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="8ecfd-202">**何时会推出新的 10 年审核日志保留附加产品许可证？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-202">**When will the new 10-year audit log retention add-on license be available?**</span></span>

<span data-ttu-id="8ecfd-203">2021 年初，拥有 E5 订阅的客户可购买新的 10 年审核日志保留附加产品。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-203">The new 10-year audit log retention add-on will be available for purchase by customers with E5 subscriptions in early 2021.</span></span>

<span data-ttu-id="8ecfd-204">**如果此功能发布了常规可用性，但在 2021 年初推出所需的附加许可证前，我创建了 10 年审核日志保留策略，组织的审核日志数据会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-204">**What happens to my organization's audit log data if I create 10-year audit log retention policy the feature is released to general availability but before the required add-on license is available in early 2021?**</span></span>

<span data-ttu-id="8ecfd-205">常规可用性后创建的 10 年审核日志保留策略覆盖的任何审核日志数据都将保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-205">Any audit log data covered by a 10-year audit log retention policy that you create after general availability will be retained for 10 years.</span></span> <span data-ttu-id="8ecfd-206">在 2021 年初推出 10 年审核日志保留附加产品许可证时，你需要为审核数据由现有的 10 年审核保留策略所保留的用户购买附加产品许可证。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-206">When the 10-year audit log retention add-on license is available in early 2021, you will need to purchase add-on licenses for users who's audit data is being retained by an existing 10-year audit retention policy.</span></span> <span data-ttu-id="8ecfd-207">此外，在 2021 年初推出附加许产品可证后，创建新的 10 年审核日志保留策略时，将强制实施相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-207">Also, once the add-on license is available in early 2021, the appropriate licensing will be enforced when you create new 10-year audit log retention policies.</span></span>

<span data-ttu-id="8ecfd-208">**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-208">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="8ecfd-209">是的。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-209">Yes.</span></span> <span data-ttu-id="8ecfd-210">只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-210">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="8ecfd-211">**是否带宽越高意味着延迟改善和 SLA 提高？**</span><span class="sxs-lookup"><span data-stu-id="8ecfd-211">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="8ecfd-212">目前，高带宽可提供更好的管道，尤其是对于具有大量审核信号和明显消耗模式的组织。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-212">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="8ecfd-213">带宽增加将改善延迟状况。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-213">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="8ecfd-214">但是不存在与高带宽相关的 SLA。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-214">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="8ecfd-215">文档中已记录标准延迟，这些延迟不会随着高级审核的发布而改变。</span><span class="sxs-lookup"><span data-stu-id="8ecfd-215">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>
