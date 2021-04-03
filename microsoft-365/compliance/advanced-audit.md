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
ms.openlocfilehash: 88308d173df79f55f38aba4b70d4b561667941bf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574651"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="b0b76-103">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="b0b76-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="b0b76-104">Microsoft 365 中的[统一审核](search-the-audit-log-in-security-and-compliance.md)功能可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="b0b76-105">高级审核可通过增强执行调查所需的审核日志保留期来帮助组织执行取证和合规性调查，提供对有助于确定泄露范围和快速访问 Office 365 管理活动 API 的重要事件的访问。</span><span class="sxs-lookup"><span data-stu-id="b0b76-105">Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="b0b76-106">高级审核适用于具有 Office 365 E5/G5 或 Microsoft 365 企业版 E5/G5订阅的组织。</span><span class="sxs-lookup"><span data-stu-id="b0b76-106">Advanced Audit is available for organizations with an Office 365 E5/G5 or Microsoft 365 Enterprise E5/G5 subscription.</span></span> <span data-ttu-id="b0b76-107">另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规或 E5 电子数据展示和审核附加产品许可证分配至用户。</span><span class="sxs-lookup"><span data-stu-id="b0b76-107">Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span> <span data-ttu-id="b0b76-108">有关许可的详细信息，请参阅[适用于安全与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-108">For more information about licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="b0b76-109">本文概述了“高级审核”功能，并展示了如何为“高级审核”设置用户。</span><span class="sxs-lookup"><span data-stu-id="b0b76-109">This article provides an overview of Advanced Audit capabilities and shows you how to set up users for Advanced Audit.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="b0b76-110">长期保留审核日志</span><span class="sxs-lookup"><span data-stu-id="b0b76-110">Long-term retention of audit logs</span></span>

<span data-ttu-id="b0b76-111">高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。</span><span class="sxs-lookup"><span data-stu-id="b0b76-111">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="b0b76-112">这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。</span><span class="sxs-lookup"><span data-stu-id="b0b76-112">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="b0b76-113">长期保留审计记录，可以帮助进行取证或合规性调查。</span><span class="sxs-lookup"><span data-stu-id="b0b76-113">Retaining audit records for longer periods can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="b0b76-114">有关详细信息，请参阅“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。</span><span class="sxs-lookup"><span data-stu-id="b0b76-114">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="b0b76-115">我们还发布了保留审核日志 10 年的功能。</span><span class="sxs-lookup"><span data-stu-id="b0b76-115">We're also releasing the capability to retain audit logs for 10 years.</span></span> <span data-ttu-id="b0b76-116">“保留审核日志 10 年”有助于支持长期的调查，并对监管、法律和内部义务作出响应。</span><span class="sxs-lookup"><span data-stu-id="b0b76-116">The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="b0b76-117">保留审核日志 10 年将需要额外的附加产品许可证。</span><span class="sxs-lookup"><span data-stu-id="b0b76-117">Retaining audit logs for 10 years will require an additional add-on license.</span></span> <span data-ttu-id="b0b76-118">此新许可证将于 2021 年初推出。</span><span class="sxs-lookup"><span data-stu-id="b0b76-118">This new license will be available in early 2021.</span></span> <span data-ttu-id="b0b76-119">有关详细信息，请参阅本文中的[高级审核常见问题](#faqs-for-advanced-audit)部分。</span><span class="sxs-lookup"><span data-stu-id="b0b76-119">For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="b0b76-120">审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="b0b76-120">Audit log retention policies</span></span>

<span data-ttu-id="b0b76-121">默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="b0b76-121">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="b0b76-122">但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达 10 年。</span><span class="sxs-lookup"><span data-stu-id="b0b76-122">But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years.</span></span> <span data-ttu-id="b0b76-123">可基于下列一个或多个条件创建保留审核记录的策略：</span><span class="sxs-lookup"><span data-stu-id="b0b76-123">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="b0b76-124">发生审核活动的 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="b0b76-124">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="b0b76-125">特定的审核活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-125">Specific audited activities.</span></span>

- <span data-ttu-id="b0b76-126">执行审核活动的用户。</span><span class="sxs-lookup"><span data-stu-id="b0b76-126">The user who performs an audited activity.</span></span>

<span data-ttu-id="b0b76-127">还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。</span><span class="sxs-lookup"><span data-stu-id="b0b76-127">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="b0b76-128">另请注意，如果你需要为组织中的部分或所有用户保留 Exchange、SharePoint 或 Azure Active Directory 审计记录少于一年（或 10 年），那么任何自定义审核日志保留策略都将优先于默认的审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="b0b76-128">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization.</span></span> <span data-ttu-id="b0b76-129">有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-129">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="b0b76-130">访问关键事件进行调查</span><span class="sxs-lookup"><span data-stu-id="b0b76-130">Access to crucial events for investigations</span></span>

<span data-ttu-id="b0b76-131">高级审核可帮助组织通过提供对重要事件的访问，例如访问邮件项目的时间，或邮件项目被回复和转发的时间，以及用户在 Exchange Online 和 SharePoint Online 中的搜索时间和内容，来执行取证和合规性调查。</span><span class="sxs-lookup"><span data-stu-id="b0b76-131">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="b0b76-132">这些关键事件可以帮助你调查可能的违规行为，并确定泄露的范围。</span><span class="sxs-lookup"><span data-stu-id="b0b76-132">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>  <span data-ttu-id="b0b76-133">高级审核提供以下重要事件：</span><span class="sxs-lookup"><span data-stu-id="b0b76-133">Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="b0b76-134">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="b0b76-134">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="b0b76-135">Send</span><span class="sxs-lookup"><span data-stu-id="b0b76-135">Send</span></span>](#send)

- [<span data-ttu-id="b0b76-136">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="b0b76-136">SearchQueryInitiatedExchange</span></span>](#searchqueryinitiatedexchange)

- [<span data-ttu-id="b0b76-137">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="b0b76-137">SearchQueryInitiatedSharePoint</span></span>](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a><span data-ttu-id="b0b76-138">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="b0b76-138">MailItemsAccessed</span></span>

<span data-ttu-id="b0b76-139">MailItemsAccessed 事件是邮箱审核操作，当邮件数据通过邮件协议和邮件客户端访问时，将触发该事件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-139">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients.</span></span> <span data-ttu-id="b0b76-140">MailItemsAccessed 操作可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。</span><span class="sxs-lookup"><span data-stu-id="b0b76-140">The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="b0b76-141">如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。</span><span class="sxs-lookup"><span data-stu-id="b0b76-141">If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="b0b76-142">MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：</span><span class="sxs-lookup"><span data-stu-id="b0b76-142">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="b0b76-143">MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。</span><span class="sxs-lookup"><span data-stu-id="b0b76-143">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="b0b76-144">MailItemsAccessed 适用于所有登录类型。</span><span class="sxs-lookup"><span data-stu-id="b0b76-144">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="b0b76-145">MessageBind 只能由邮件客户端覆盖访问。</span><span class="sxs-lookup"><span data-stu-id="b0b76-145">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="b0b76-146">它不适用于同步活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-146">It didn't apply to sync activities.</span></span> <span data-ttu-id="b0b76-147">“绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-147">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="b0b76-148">访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。</span><span class="sxs-lookup"><span data-stu-id="b0b76-148">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="b0b76-149">相反，MailItemsAccessed 事件聚合在较少的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="b0b76-149">In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="b0b76-150">有关 MailItemsAccessed 活动的审核记录的详细信息，请参阅[使用高级审核来调查被泄漏的帐户](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-150">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="b0b76-151">若要搜索 MailItemsAccessed 审核记录，可以在 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“访问的邮箱项目”** 活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-151">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在审核日志搜索工具中搜索 MailItemsAccessed 操作](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="b0b76-153">此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="b0b76-153">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="b0b76-154">Send</span><span class="sxs-lookup"><span data-stu-id="b0b76-154">Send</span></span>

<span data-ttu-id="b0b76-155">Send 事件也是邮箱审核操作，当用户执行以下操作之一时将被触发：</span><span class="sxs-lookup"><span data-stu-id="b0b76-155">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="b0b76-156">发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="b0b76-156">Sends an email message</span></span>

- <span data-ttu-id="b0b76-157">答复电子邮件</span><span class="sxs-lookup"><span data-stu-id="b0b76-157">Replies to an email message</span></span>

- <span data-ttu-id="b0b76-158">转发电子邮件</span><span class="sxs-lookup"><span data-stu-id="b0b76-158">Forwards an email message</span></span>

<span data-ttu-id="b0b76-159">调查人员可使用发送事件识别从被泄露的帐户发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-159">Investigators can use the Send event to identify email sent from a compromised account.</span></span> <span data-ttu-id="b0b76-160">发送事件的审核记录中包含有关该邮件的信息，例如发送邮件的时间、InternetMessage ID、主题行以及邮件是否包含附件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-160">The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments.</span></span> <span data-ttu-id="b0b76-161">此审核信息可帮助调查人员识别从已泄露帐户发送的电子邮件或由攻击者发送的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b0b76-161">This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker.</span></span> <span data-ttu-id="b0b76-162">此外，调查人员可使用 Microsoft 365 电子数据展示工具搜索该邮件（通过使用主题行或邮件 ID）来标识该邮件的收件人和已发送邮件的实际内容。</span><span class="sxs-lookup"><span data-stu-id="b0b76-162">Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="b0b76-163">若要搜索 Send 审核记录，可到 Microsoft 365 合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“Exchange 邮箱活动”** 下拉列表中，搜索 **“已发送邮件”** 活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-163">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![在审核日志搜索工具中搜索“已发送邮件”操作](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="b0b76-165">此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="b0b76-165">You can also run the [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="b0b76-166">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="b0b76-166">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="b0b76-167">当用户使用Outlook搜索邮箱中的项目时，会触发SearchQueryInitiatedExchange事件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-167">The SearchQueryInitiatedExchange event is triggered when a person uses Outlook to search for items in a mailbox.</span></span> <span data-ttu-id="b0b76-168">当在以下Outlook环境中执行搜索时，将触发事件：</span><span class="sxs-lookup"><span data-stu-id="b0b76-168">Events are triggered when searches are performed in the following Outlook environments:</span></span>

- <span data-ttu-id="b0b76-169">Outlook（桌面客户端）</span><span class="sxs-lookup"><span data-stu-id="b0b76-169">Outlook (desktop client)</span></span>

- <span data-ttu-id="b0b76-170">Outlook 网页版（OWA）</span><span class="sxs-lookup"><span data-stu-id="b0b76-170">Outlook on the web (OWA)</span></span>

- <span data-ttu-id="b0b76-171">Outlook for iOS</span><span class="sxs-lookup"><span data-stu-id="b0b76-171">Outlook for iOS</span></span>

- <span data-ttu-id="b0b76-172">Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="b0b76-172">Outlook for Android</span></span>

- <span data-ttu-id="b0b76-173">Windows 10的“邮件”应用</span><span class="sxs-lookup"><span data-stu-id="b0b76-173">Mail app for Windows 10</span></span>

<span data-ttu-id="b0b76-174">调查人员可使用 SearchQueryInitiatedExchange 事件来确定可能已泄露帐户的攻击者是否已查找或尝试访问邮箱中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="b0b76-174">Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox.</span></span> <span data-ttu-id="b0b76-175">SearchQueryInitiatedExchange 事件的审核记录包含实际搜索查询文本等信息。</span><span class="sxs-lookup"><span data-stu-id="b0b76-175">The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query.</span></span> <span data-ttu-id="b0b76-176">审计记录也显示了搜索所处的Outlook环境。</span><span class="sxs-lookup"><span data-stu-id="b0b76-176">The audit record also indicates the Outlook environment the search was performed in.</span></span> <span data-ttu-id="b0b76-177">通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的电子邮件数据的意图。</span><span class="sxs-lookup"><span data-stu-id="b0b76-177">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="b0b76-178">若要搜索 SearchQueryInitiatedExchange 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的电子邮件搜索”** 活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-178">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在审核日志搜索工具中搜索“已执行的电子邮件搜索”操作](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="b0b76-180">此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-180">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b0b76-p116">必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedExchange 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="b0b76-p116">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`. </span></span><br/><br/>
<span data-ttu-id="b0b76-182">在多地理环境中，必须在用户邮箱所在的林中运行 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="b0b76-182">In a multi-geo environment, you must run the **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="b0b76-183">若要确定用户的邮箱位置，请运行以下命令：`Get-Mailbox <user identity> | FL MailboxLocations`。</span><span class="sxs-lookup"><span data-stu-id="b0b76-183">To identify the user's mailbox location, run the following command: `Get-Mailbox <user identity> | FL MailboxLocations`.</span></span>
<span data-ttu-id="b0b76-184">如果 `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` 命令之前在与用户邮箱所在林不同的林中运行，则必须从用户的邮箱中删除 SearchQueryInitiated 值（通过运行 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`），然后将其添加到用户邮箱所在的林中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b0b76-184">If the `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` command was previously run in the forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox (by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`) and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="b0b76-185">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="b0b76-185">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="b0b76-186">与搜索邮箱项目类似，当有人在 SharePoint 中搜索项目时，会触发 SearchQueryInitiatedSharePoint 事件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-186">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in SharePoint.</span></span> <span data-ttu-id="b0b76-187">在以下类型的SharePoint站点中进行搜索时，将触发事件：</span><span class="sxs-lookup"><span data-stu-id="b0b76-187">Events are triggered when searches are performed in the following types of SharePoint sites:</span></span>

- <span data-ttu-id="b0b76-188">首页</span><span class="sxs-lookup"><span data-stu-id="b0b76-188">Home sites</span></span>

- <span data-ttu-id="b0b76-189">通信网站</span><span class="sxs-lookup"><span data-stu-id="b0b76-189">Communication sites</span></span>

- <span data-ttu-id="b0b76-190">中心网站</span><span class="sxs-lookup"><span data-stu-id="b0b76-190">Hub sites</span></span>

- <span data-ttu-id="b0b76-191">与 Microsoft Teams 相关联的网站</span><span class="sxs-lookup"><span data-stu-id="b0b76-191">Sites associated with Microsoft Teams</span></span>

<span data-ttu-id="b0b76-192">调查人员可使用 SearchQueryInitiatedSharePoint 事件来确定攻击者是否试图在 SharePoint 中查找（并有可能访问）敏感信息。</span><span class="sxs-lookup"><span data-stu-id="b0b76-192">Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint.</span></span> <span data-ttu-id="b0b76-193">SearchQueryInitiatedSharePoint 事件的审核记录中还包含实际搜索查询文本。</span><span class="sxs-lookup"><span data-stu-id="b0b76-193">The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query.</span></span> <span data-ttu-id="b0b76-194">审计记录还显示所搜索的SharePoint站点的类型。</span><span class="sxs-lookup"><span data-stu-id="b0b76-194">The audit record also indicates the type of SharePoint site that was searched.</span></span> <span data-ttu-id="b0b76-195">通过查看攻击者可能已执行的搜索查询，调查员可以更清晰地了解所搜索的文件数据的意图和范围。</span><span class="sxs-lookup"><span data-stu-id="b0b76-195">By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="b0b76-196">若要搜索 SearchQueryInitiatedSharePoint 审核记录，可到合规中心，在 [审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的 **“搜索活动”** 下拉列表中，搜索 **“已执行的 SharePoint 搜索”** 活动。</span><span class="sxs-lookup"><span data-stu-id="b0b76-196">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![在审核日志搜索工具中搜索“已执行的 SharePoint 搜索”操作](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="b0b76-198">此外，还可在 Exchange Online PowerShell 中运行[Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-198">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="b0b76-p120">必须在 Exchange Online PowerShell 中运行以下命令，审核日志搜索结果中才会包括 SearchQueryInitiatedSharePoint 事件（由指定的 E5 用户执行）： `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="b0b76-p120">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedSharePoint events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`. </span></span><br/><br/>
<span data-ttu-id="b0b76-200">在多地理环境中，必须在用户邮箱所在的林中运行 **Set-Mailbox** 命令。</span><span class="sxs-lookup"><span data-stu-id="b0b76-200">In a multi-geo environment, you must run the **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="b0b76-201">若要确定用户的邮箱位置，请运行以下命令：`Get-Mailbox <user identity> | FL MailboxLocations`。</span><span class="sxs-lookup"><span data-stu-id="b0b76-201">To identify the user's mailbox location, run the following command: `Get-Mailbox <user identity> | FL MailboxLocations`.</span></span>
<span data-ttu-id="b0b76-202">如果 `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` 命令之前在与用户邮箱所在林不同的林中运行，则必须从用户的邮箱中删除 SearchQueryInitiated 值（通过运行 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`），然后将其添加到用户邮箱所在的林中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="b0b76-202">If the `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` command was previously run in the forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox (by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`) and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="b0b76-203">高带宽访问 Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="b0b76-203">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="b0b76-204">通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。</span><span class="sxs-lookup"><span data-stu-id="b0b76-204">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="b0b76-205">这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。</span><span class="sxs-lookup"><span data-stu-id="b0b76-205">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="b0b76-206">随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。</span><span class="sxs-lookup"><span data-stu-id="b0b76-206">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="b0b76-207">结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。</span><span class="sxs-lookup"><span data-stu-id="b0b76-207">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="b0b76-208">带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。</span><span class="sxs-lookup"><span data-stu-id="b0b76-208">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="b0b76-209">所有组织最初每分钟分配 2000 个请求基线。</span><span class="sxs-lookup"><span data-stu-id="b0b76-209">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="b0b76-210">根据组织的座位数和许可订阅，此限制将显著增加。</span><span class="sxs-lookup"><span data-stu-id="b0b76-210">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="b0b76-211">E5 组织获得的带宽约为非 E5 组织的两倍。</span><span class="sxs-lookup"><span data-stu-id="b0b76-211">E5 organizations will get about twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="b0b76-212">这也是最大宽带的上限，以保护服务的健康。</span><span class="sxs-lookup"><span data-stu-id="b0b76-212">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="b0b76-213">有关更多信息，参见“[Office 365 管理活动 API](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。</span><span class="sxs-lookup"><span data-stu-id="b0b76-213">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="set-up-advanced-audit-for-users"></a><span data-ttu-id="b0b76-214">为用户设置“高级审核”</span><span class="sxs-lookup"><span data-stu-id="b0b76-214">Set up Advanced Audit for users</span></span>

<span data-ttu-id="b0b76-215">“高级审核”功能，如记录重要事件（如 MailItemsAccessed 和 Send）功能，需要为用户分配适当的 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="b0b76-215">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="b0b76-216">此外，必须为这些用户启用“高级审核”应用程序/服务计划。</span><span class="sxs-lookup"><span data-stu-id="b0b76-216">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="b0b76-217">要验证“高级审核”应用程序是否已分配给用户，请对每个用户执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b0b76-217">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="b0b76-218">在 [Microsoft 365 管理中心](https://admin.microsoft.com/Adminportal)中，转到“**用户**” > “**活动用户**”，然后选择用户。</span><span class="sxs-lookup"><span data-stu-id="b0b76-218">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="b0b76-219">在用户属性浮出页面上，单击“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="b0b76-219">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="b0b76-220">在“**许可证**”部分，验证是否为用户分配了 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="b0b76-220">In the **Licenses** section, verify that the user is assigned an E5 license.</span></span>

4. <span data-ttu-id="b0b76-221">展开“**应用程序**”部分，并验证是否选中了“**Microsoft 365 高级审核**”复选框。</span><span class="sxs-lookup"><span data-stu-id="b0b76-221">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="b0b76-222">如果未选中该复选框，请将其选中，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="b0b76-222">If the checkbox isn’t selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="b0b76-223">将在 24 小时内开始记录用户的 MailItemsAccessed、Send 和其他关键事件的审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="b0b76-223">The logging of audit records for MailItemsAccessed, Send, and other crucial events for the user will begin within 24 hours.</span></span>

<span data-ttu-id="b0b76-224">对于使用基于组的许可将许可证分配给用户组的组织，必须为组禁用 Microsoft 365 高级审核的许可分配。</span><span class="sxs-lookup"><span data-stu-id="b0b76-224">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="b0b76-225">保存所做的更改后，请验证是否已为组禁用 Microsoft 365 高级审核。</span><span class="sxs-lookup"><span data-stu-id="b0b76-225">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="b0b76-226">然后，重新为组启用许可分配。</span><span class="sxs-lookup"><span data-stu-id="b0b76-226">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="b0b76-227">有关基于组的许可的说明，请参阅[在 Azure Active Directory 中按组成员身份向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="b0b76-227">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="b0b76-228">此外，如果您已自定义登录到用户邮箱或共享邮箱的邮箱操作，则不会在这些邮箱上自动审核新的默认邮箱操作（如 MailItemsAccessed）。</span><span class="sxs-lookup"><span data-stu-id="b0b76-228">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, new default mailbox actions such as MailItemsAccessed will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="b0b76-229">有关更改为每个登录类型审核的邮箱操作的信息，请参阅[管理邮箱审核](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)中的“更改或还原默认记录的邮箱操作”部分。</span><span class="sxs-lookup"><span data-stu-id="b0b76-229">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="b0b76-230">高级审核常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b0b76-230">FAQs for Advanced Audit</span></span>

<span data-ttu-id="b0b76-231">**是否每位用户都需要 E5 许可证才能从高级审核中受益？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-231">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="b0b76-232">若要从用户级高级审核功能中受益，需要向用户分配 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="b0b76-232">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license.</span></span> <span data-ttu-id="b0b76-233">有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。</span><span class="sxs-lookup"><span data-stu-id="b0b76-233">There are some capabilities that will check for the appropriate license to expose the feature for the user.</span></span> <span data-ttu-id="b0b76-234">例如，如果未向某个用户分配 E5 许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b0b76-234">For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="b0b76-235">**我的组织具有 E5 订阅，我是否需要执行任何操作才能获取重要事件的审核记录的访问权限？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-235">**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="b0b76-236">对于已分配相应许可证的符合条件的客户和用户，无需执行任何操作即可访问关键审核事件。</span><span class="sxs-lookup"><span data-stu-id="b0b76-236">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="b0b76-237">**何时会推出新的 10 年审核日志保留附加产品许可证？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-237">**When will the new 10-year audit log retention add-on license be available?**</span></span>

<span data-ttu-id="b0b76-238">现在，拥有 E5 订阅的客户可以购买新的 10 年审核日志保留附加产品。</span><span class="sxs-lookup"><span data-stu-id="b0b76-238">The new 10-year audit log retention add-on is now available for purchase by customers with E5 subscriptions.</span></span>

<span data-ttu-id="b0b76-239">**如果此功能发布了常规可用性，但在 2021 年 2 月推出所需的附加产品许可证前，我创建了 10 年审核日志保留策略，组织的审核日志数据会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-239">**What happens to my organization's audit log data if I created a 10-year audit log retention policy when the feature was released to general availability but before the required add-on license was made available in February 2021?**</span></span>

<span data-ttu-id="b0b76-240">常规可用性后创建的 10 年审核日志保留策略覆盖的任何审核日志数据都将保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="b0b76-240">Any audit log data covered by a 10-year audit log retention policy that you created after general availability will be retained for 10 years.</span></span> <span data-ttu-id="b0b76-241">在 2021 年初推出 10 年审核日志保留附加产品许可证时，你需要为审核数据由现有的 10 年审核保留策略所保留的用户购买附加产品许可证。</span><span class="sxs-lookup"><span data-stu-id="b0b76-241">When the 10-year audit log retention add-on license is available in early 2021, you will need to purchase add-on licenses for users who's audit data is being retained by an existing 10-year audit retention policy.</span></span>

<span data-ttu-id="b0b76-242">**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-242">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="b0b76-243">是的。</span><span class="sxs-lookup"><span data-stu-id="b0b76-243">Yes.</span></span> <span data-ttu-id="b0b76-244">只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。</span><span class="sxs-lookup"><span data-stu-id="b0b76-244">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="b0b76-245">**是否带宽越高意味着延迟改善和 SLA 提高？**</span><span class="sxs-lookup"><span data-stu-id="b0b76-245">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="b0b76-246">目前，高带宽可提供更好的管道，尤其是对于具有大量审核信号和明显消耗模式的组织。</span><span class="sxs-lookup"><span data-stu-id="b0b76-246">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="b0b76-247">带宽增加将改善延迟状况。</span><span class="sxs-lookup"><span data-stu-id="b0b76-247">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="b0b76-248">但是不存在与高带宽相关的 SLA。</span><span class="sxs-lookup"><span data-stu-id="b0b76-248">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="b0b76-249">文档中已记录标准延迟，这些延迟不会随着高级审核的发布而改变。</span><span class="sxs-lookup"><span data-stu-id="b0b76-249">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>
