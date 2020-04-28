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
ms.openlocfilehash: b1a79598fc49d710c54a23dc9ce92c9f2b7f5805
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632277"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="f0a04-103">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="f0a04-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="f0a04-104">Microsoft 365 中的[统一审核](search-the-audit-log-in-security-and-compliance.md)功能可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。</span><span class="sxs-lookup"><span data-stu-id="f0a04-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="f0a04-105">现在通过发布 Microsoft 365 高级审核，我们增加了新的审核功能，可帮助你的组织进行法庭与合规调查。</span><span class="sxs-lookup"><span data-stu-id="f0a04-105">Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="f0a04-106">高级审核适用于具有 Office 365 E5 或 Microsoft 365 企业版 E5 订阅的组织。</span><span class="sxs-lookup"><span data-stu-id="f0a04-106">Advanced Audit is available for organizations with an Office 365 E5 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="f0a04-107">另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规加载项许可证分配至用户。</span><span class="sxs-lookup"><span data-stu-id="f0a04-107">Additionally, a Microsoft 365 E5 Compliance add-on license can be assigned to users for when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span>

<span data-ttu-id="f0a04-108">本文提供了这些高级审核功能的概览信息。</span><span class="sxs-lookup"><span data-stu-id="f0a04-108">This article provides an overview of these Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="f0a04-109">长期保留审核日志</span><span class="sxs-lookup"><span data-stu-id="f0a04-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="f0a04-110">高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。</span><span class="sxs-lookup"><span data-stu-id="f0a04-110">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="f0a04-111">这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。</span><span class="sxs-lookup"><span data-stu-id="f0a04-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="f0a04-112">这有助于正在进行的法庭或合规调查。</span><span class="sxs-lookup"><span data-stu-id="f0a04-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="f0a04-113">有关详细信息，参见“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。</span><span class="sxs-lookup"><span data-stu-id="f0a04-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="f0a04-114">审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="f0a04-114">Audit log retention policies</span></span>

<span data-ttu-id="f0a04-115">默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="f0a04-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="f0a04-116">但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达一年。</span><span class="sxs-lookup"><span data-stu-id="f0a04-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="f0a04-117">可基于下列一个或多个条件创建保留审核记录的策略：</span><span class="sxs-lookup"><span data-stu-id="f0a04-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="f0a04-118">发生审核活动的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="f0a04-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="f0a04-119">特定的审核活动</span><span class="sxs-lookup"><span data-stu-id="f0a04-119">Specific audited activities</span></span>

- <span data-ttu-id="f0a04-120">执行审核活动的用户</span><span class="sxs-lookup"><span data-stu-id="f0a04-120">The user who performs an audited activity</span></span>

<span data-ttu-id="f0a04-121">还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。</span><span class="sxs-lookup"><span data-stu-id="f0a04-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="f0a04-122">另外注意，如果组织中的部分或全部用户需要保留 Exchange、SharePoint 或 Azure Active Directory 审核记录，则所有自定义审核日志保留策略将优先于默认的审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="f0a04-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="f0a04-123">有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f0a04-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="f0a04-124">访问关键事件进行调查</span><span class="sxs-lookup"><span data-stu-id="f0a04-124">Access to crucial events for investigations</span></span>

<span data-ttu-id="f0a04-125">关键安全和合规性相关审核事件可帮助你调查可能的违规或其他与法庭有关的调查。</span><span class="sxs-lookup"><span data-stu-id="f0a04-125">Crucial security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="f0a04-126">我们发布的第一个此类关键事件是 *MailItemsAccessed* 邮箱审核操作。</span><span class="sxs-lookup"><span data-stu-id="f0a04-126">The first crucial event that we're releasing is the *MailItemsAccessed* mailbox auditing action.</span></span> <span data-ttu-id="f0a04-127">邮件协议和邮件客户端访问邮件数据时，将触发此操作。</span><span class="sxs-lookup"><span data-stu-id="f0a04-127">This action is triggered when mail data is accessed by mail protocols and mail clients.</span></span> <span data-ttu-id="f0a04-128">MailItemsAccessed 操作可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。</span><span class="sxs-lookup"><span data-stu-id="f0a04-128">The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="f0a04-129">如果攻击者获得了对电子邮件的访问权限，即使没有明显的信号表明已实际读取了邮件，也将触发 MailItemsAccessed 操作（换句话说，审核记录中记录了诸如绑定或同步之类的访问类型）。</span><span class="sxs-lookup"><span data-stu-id="f0a04-129">If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="f0a04-130">新的 MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：</span><span class="sxs-lookup"><span data-stu-id="f0a04-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="f0a04-131">MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。</span><span class="sxs-lookup"><span data-stu-id="f0a04-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="f0a04-132">MailItemsAccessed 适用于所有登录类型。</span><span class="sxs-lookup"><span data-stu-id="f0a04-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="f0a04-133">MessageBind 只能由邮件客户端覆盖访问。</span><span class="sxs-lookup"><span data-stu-id="f0a04-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="f0a04-134">它不适用于同步活动。</span><span class="sxs-lookup"><span data-stu-id="f0a04-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="f0a04-135">“绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="f0a04-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="f0a04-136">访问同一封电子邮件时，MessageBind 操作会触发多个审核记录的创建过程，从而导致审核干扰。</span><span class="sxs-lookup"><span data-stu-id="f0a04-136">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="f0a04-137">相反，MailItemsAccessed 事件聚合在较少的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="f0a04-137">In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="f0a04-138">有关 MailItemsAccessed 活动的审核记录的详细信息，请参阅[使用高级审核来调查被泄漏的帐户](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="f0a04-138">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

### <a name="search-for-mailitemsaccessed-audit-records"></a><span data-ttu-id="f0a04-139">搜索 MailItemsAccessed 审核记录</span><span class="sxs-lookup"><span data-stu-id="f0a04-139">Search for MailItemsAccessed audit records</span></span>

<span data-ttu-id="f0a04-140">若要搜索 MailItemsAccessed 审核记录，可以在安全与合规中心，在[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)中的“Exchange 邮箱活动”\*\*\*\* 下拉列表中，搜索“访问的邮箱项目”\*\*\*\* 活动。</span><span class="sxs-lookup"><span data-stu-id="f0a04-140">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span>

![在审核日志搜索工具中搜索 MailItemsAccessed 操作](../media/MailItemsAccessedSCC1.png)

<span data-ttu-id="f0a04-142">此外，还可在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) 或 [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) 命令。</span><span class="sxs-lookup"><span data-stu-id="f0a04-142">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="f0a04-143">高带宽访问 Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="f0a04-143">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="f0a04-144">通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。</span><span class="sxs-lookup"><span data-stu-id="f0a04-144">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="f0a04-145">这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。</span><span class="sxs-lookup"><span data-stu-id="f0a04-145">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="f0a04-146">随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。</span><span class="sxs-lookup"><span data-stu-id="f0a04-146">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="f0a04-147">结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。</span><span class="sxs-lookup"><span data-stu-id="f0a04-147">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="f0a04-148">带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。</span><span class="sxs-lookup"><span data-stu-id="f0a04-148">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="f0a04-149">所有组织最初每分钟分配 2000 个请求基线。</span><span class="sxs-lookup"><span data-stu-id="f0a04-149">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="f0a04-150">根据组织的座位数和许可订阅，此限制将显著增加。</span><span class="sxs-lookup"><span data-stu-id="f0a04-150">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="f0a04-151">E5 组织获得的带宽是非 E5 组织的约两倍。</span><span class="sxs-lookup"><span data-stu-id="f0a04-151">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="f0a04-152">这也是最大宽带的上限，以保护服务的健康。</span><span class="sxs-lookup"><span data-stu-id="f0a04-152">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="f0a04-153">有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。</span><span class="sxs-lookup"><span data-stu-id="f0a04-153">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="f0a04-154">高级审核常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f0a04-154">FAQs for Advanced Audit</span></span>

<span data-ttu-id="f0a04-155">**可在何处访问高级审核？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-155">**Where can I access Advanced Audit?**</span></span>

<span data-ttu-id="f0a04-156">向你的组织推出高级审核后，你将能够使用[安全与合规中心](https://protection.office.com)中的审核日志搜索工具创建审核日志保留策略，并搜索 MailItemsAccessed 审核记录。</span><span class="sxs-lookup"><span data-stu-id="f0a04-156">After Advanced Audit is rolled out to your organization, you will be able to create audit log retention policies and search for MailItemsAccessed audit records using the Audit log search tool in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f0a04-157">我们正致力于在未来几周内将高级审核推出到 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f0a04-157">We're working to roll out Advanced Audit to the [Microsoft 365 compliance center](https://compliance.microsoft.com) in the coming weeks.</span></span>

<span data-ttu-id="f0a04-158">**是否每位用户都需要 E5 许可证才能从高级审核中受益？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-158">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="f0a04-159">若要从用户级高级审核功能中受益，需要向用户分配 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="f0a04-159">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license.</span></span> <span data-ttu-id="f0a04-160">有些功能会检查是否有相应的许可证，确定后才为用户提供相应功能。</span><span class="sxs-lookup"><span data-stu-id="f0a04-160">There are some capabilities that will check for the appropriate license to expose the feature for the user.</span></span> <span data-ttu-id="f0a04-161">例如，如果未向某个用户分配 E5 许可证，而你尝试为其保留审核记录超过 90 天，则系统会返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="f0a04-161">For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="f0a04-162">**为什么即使我们有 E5 订阅并为用户分配了 E5 许可证，我仍然在我的组织中看不到高级审核？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-162">**Why don't I see Advanced Audit in my organization, even though we have an E5 subscription and users that are assigned E5 licenses?**</span></span>

<span data-ttu-id="f0a04-163">很有可能在你的组织中无法使用高级审核功能（例如创建审核日志保留策略和记录 MailItemsAccessed 审核记录的功能），即使有正确的许可也是如此。</span><span class="sxs-lookup"><span data-stu-id="f0a04-163">It's possible that Advanced Audit features (such as the ability to create audit log retention policies and the logging of MailItemsAccessed audit records) aren't available in your organization, even with the correct licensing in place.</span></span> <span data-ttu-id="f0a04-164">如果发生这种情况，是因为高级审核包尚未推出到你的组织。</span><span class="sxs-lookup"><span data-stu-id="f0a04-164">If this is happening to you, it's because the Advanced Audit package hasn't been rolled out to your organization yet.</span></span> <span data-ttu-id="f0a04-165">这是暂时的许可回填问题，应该会在未来几周内针对受影响的组织予以解决。</span><span class="sxs-lookup"><span data-stu-id="f0a04-165">This is a temporary licensing backfill issue, which should be resolved for affected organizations in the next few weeks.</span></span> <span data-ttu-id="f0a04-166">若要缓解此问题，请对每个 E5 用户执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f0a04-166">To mitigate this issue, please perform the following steps for each E5 user:</span></span>

1. <span data-ttu-id="f0a04-167">在 Microsoft 365 管理中心，转到 **“用户”>“活动用户”**，然后选择一个用户。</span><span class="sxs-lookup"><span data-stu-id="f0a04-167">In the Microsoft 365 admin center, go to **Users > Active users**, and then select a user.</span></span>

2. <span data-ttu-id="f0a04-168">在用户属性浮出页面上，单击“**许可证和应用**”。</span><span class="sxs-lookup"><span data-stu-id="f0a04-168">On the user properties flyout page, click **Licenses and Apps**.</span></span>

3. <span data-ttu-id="f0a04-169">展开“**应用**”部分，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f0a04-169">Expand the **Apps** section, and then do one of the following things:</span></span>

   <span data-ttu-id="f0a04-170">a.</span><span class="sxs-lookup"><span data-stu-id="f0a04-170">a.</span></span> <span data-ttu-id="f0a04-171">如果未选中“**Microsoft 365 高级审核**”复选框，请将其选中，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="f0a04-171">If the **Microsoft 365 Advanced Auditing** checkbox is not selected, select it, and then click **Save changes.**</span></span> <span data-ttu-id="f0a04-172">此用户的 MailItemsAccessed 操作审核记录应该会在 24 小时内可供搜索。</span><span class="sxs-lookup"><span data-stu-id="f0a04-172">Audit records for MailItemsAccessed actions for this user should be searchable within 24 hours.</span></span>

   <span data-ttu-id="f0a04-173">b.</span><span class="sxs-lookup"><span data-stu-id="f0a04-173">b.</span></span> <span data-ttu-id="f0a04-174">如果已选中“**Microsoft 365 高级审核**”复选框，请将其清除，然后单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="f0a04-174">If the **Microsoft 365 Advanced Auditing** checkbox is selected, clear it, and then click **Save changes.**</span></span> <span data-ttu-id="f0a04-175">请参阅步骤 4。</span><span class="sxs-lookup"><span data-stu-id="f0a04-175">See step 4.</span></span>

4. <span data-ttu-id="f0a04-176">如果已在步骤 3 中清除复选框，请等待 60 分钟，然后重复步骤 3a 以启用 Microsoft 365 高级审核应用。</span><span class="sxs-lookup"><span data-stu-id="f0a04-176">If you cleared the checkbox in step 3, wait 60 minutes, and then repeat step 3a to enable the Microsoft 365 Advanced Auditing app.</span></span>

<span data-ttu-id="f0a04-177">**如果我的组织采用了将审核记录保留一年的私有预览计划，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-177">**What happens if my organization was in the private preview for one-year retention of audit records?**</span></span>

<span data-ttu-id="f0a04-178">只要你不使用自定义审核保留策略来覆盖和更改预览计划中的审核保留策略，预览计划中的审核保留策略将持续存在。</span><span class="sxs-lookup"><span data-stu-id="f0a04-178">Your audit retention policies from the preview program will persist as long as you don't override and change them with custom audit retention policies.</span></span>

<span data-ttu-id="f0a04-179">**如果我的组织想要保留超过一年的审核日志，该怎么办？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-179">**What if my organization wants to retain audit logs for longer than one year?**</span></span>

<span data-ttu-id="f0a04-180">我们正在探索如何以及是否能为审核记录提供更长保留期的方案。</span><span class="sxs-lookup"><span data-stu-id="f0a04-180">We're exploring options for how and if we can provide longer retention periods for audit records.</span></span> <span data-ttu-id="f0a04-181">你可以通过 [Office 365 用户之声](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187)提供有关延长审核记录保留期的反馈。</span><span class="sxs-lookup"><span data-stu-id="f0a04-181">You can provide any feedback about longer retention of audit records at [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187).</span></span>

<span data-ttu-id="f0a04-182">**我的组织具有 E5 订阅，我是否需要执行任何操作才能获取 MailItemsAccessed 事件的审核记录的访问权限？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-182">**My organization has an E5 subscription, do I need to do anything to get access to audit records for MailItemsAccessed events?**</span></span>

<span data-ttu-id="f0a04-183">符合条件的客户不需要执行任何操作即可访问 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="f0a04-183">For eligible customers, there is no action to get access to MailItemsAccessed events.</span></span> <span data-ttu-id="f0a04-184">但是，如本主题中前面所述，由许可回填问题导致的延迟可能会阻止 MailItemsAccessed 事件的审核记录在审核日志搜索中返回。</span><span class="sxs-lookup"><span data-stu-id="f0a04-184">However, as previously explained in this topic, latency caused by the licensing backfill issue may prevent audit records for MailItemsAccessed event from being returned in an audit log search.</span></span> <span data-ttu-id="f0a04-185">如果发生这种情况，请按照“搜索 MailItemsAccessed 审核记录”部分的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f0a04-185">If this happens, follow the instructions in the Search for MailItemsAccessed audit records section.</span></span>

<span data-ttu-id="f0a04-186">**你们是否计划在今年发布更多事件？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-186">**Are you planning to release additional events this year?**</span></span>

<span data-ttu-id="f0a04-187">是的，我们计划在未来几个月发布对调查至关重要的新事件。</span><span class="sxs-lookup"><span data-stu-id="f0a04-187">Yes, we plan to release new events that are crucial to investigations in the coming months.</span></span> <span data-ttu-id="f0a04-188">临近发布日期时，我们将在 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)中发布有关这些新事件的信息。</span><span class="sxs-lookup"><span data-stu-id="f0a04-188">We will post information about these new events in the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) as we get closer to a release date.</span></span>

<span data-ttu-id="f0a04-189">**高级审核中的新事件在 Office 365 管理活动 API 中是否可用？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-189">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="f0a04-190">是的。</span><span class="sxs-lookup"><span data-stu-id="f0a04-190">Yes.</span></span> <span data-ttu-id="f0a04-191">只要为具有相应许可证的用户生成了审核记录，你就可以通过 Office 365 管理活动 API 访问这些记录。</span><span class="sxs-lookup"><span data-stu-id="f0a04-191">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="f0a04-192">**是否带宽越高意味着延迟改善和 SLA 提高？**</span><span class="sxs-lookup"><span data-stu-id="f0a04-192">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="f0a04-193">目前，高带宽可提供更好的管道，尤其是对于具有大量审核信号和明显消耗模式的组织。</span><span class="sxs-lookup"><span data-stu-id="f0a04-193">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="f0a04-194">这可能会改善延迟。</span><span class="sxs-lookup"><span data-stu-id="f0a04-194">This can lead to better latency.</span></span> <span data-ttu-id="f0a04-195">但是，不存在与高带宽相关的 SLA。</span><span class="sxs-lookup"><span data-stu-id="f0a04-195">But, there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="f0a04-196">文档中已记录标准延迟，这些延迟不会随着高级审核的发布而改变。</span><span class="sxs-lookup"><span data-stu-id="f0a04-196">Standard latencies are documented, and these don't change with the release of Advanced Audit.</span></span>
