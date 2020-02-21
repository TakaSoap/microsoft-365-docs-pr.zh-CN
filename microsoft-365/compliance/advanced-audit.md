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
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="6682c-103">Microsoft 365 高级审核</span><span class="sxs-lookup"><span data-stu-id="6682c-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="6682c-104">Microsoft 365 中的[统一审核](search-the-audit-log-in-security-and-compliance.md)功能可让组织深入了解 Microsoft 365 众多服务中的不同类型审核活动。</span><span class="sxs-lookup"><span data-stu-id="6682c-104">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365.</span></span> <span data-ttu-id="6682c-105">现在通过发布 Microsoft 365 高级审核，我们增加了新的审核功能，可帮助你的组织进行法庭与合规调查。</span><span class="sxs-lookup"><span data-stu-id="6682c-105">Now with the release of Advanced Audit in Microsoft 365, we're adding new auditing capabilities that can help your organization with forensic and compliance investigations.</span></span>

> [!NOTE]
> <span data-ttu-id="6682c-106">高级审核适用于具有 Office 365 或 Microsoft 365 企业版 E5 订阅的组织。</span><span class="sxs-lookup"><span data-stu-id="6682c-106">Advanced Audit is available for organizations with an Office 365 or Microsoft 365 Enterprise E5 subscription.</span></span> <span data-ttu-id="6682c-107">另外，当对于高级审核功能需要每用户授权时（长期保留审核日志和访问关键事件进行调查就是这种情况），可将 Microsoft 365 E5 合规加载项订阅分配至用户。</span><span class="sxs-lookup"><span data-stu-id="6682c-107">Additionally, a Microsoft 365 E5 Compliance add-on subscription can be assigned to users for when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations.</span></span>

<span data-ttu-id="6682c-108">本文提供了这些高级审核功能的概览信息。</span><span class="sxs-lookup"><span data-stu-id="6682c-108">This article provides an overview of these Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="6682c-109">长期保留审核日志</span><span class="sxs-lookup"><span data-stu-id="6682c-109">Long-term retention of audit logs</span></span>

<span data-ttu-id="6682c-110">高级审核将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。</span><span class="sxs-lookup"><span data-stu-id="6682c-110">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="6682c-111">这是通过默认审核日志保留策略来实现的，此策略保留包含“**工作量**”属性（表示发生活动的服务）的“**Exchange**”、“**SharePoint**” 或“**AzureActiveDirectory**”的所有审核记录。</span><span class="sxs-lookup"><span data-stu-id="6682c-111">This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange**, **SharePoint**, or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year.</span></span> <span data-ttu-id="6682c-112">这有助于正在进行的法庭或合规调查。</span><span class="sxs-lookup"><span data-stu-id="6682c-112">This can help with on-going forensic or compliance investigations.</span></span> <span data-ttu-id="6682c-113">有关详细信息，参见“[管理审核日志保留策略](audit-log-retention-policies.md#default-audit-log-retention-policy)”中的“默认审核日志保留策略”。</span><span class="sxs-lookup"><span data-stu-id="6682c-113">For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

## <a name="audit-log-retention-policies"></a><span data-ttu-id="6682c-114">审核日志保留策略</span><span class="sxs-lookup"><span data-stu-id="6682c-114">Audit log retention policies</span></span>

<span data-ttu-id="6682c-115">默认审核日志保留策略（上节中描述）未包含其它服务中生成的所有审核记录，将保留 90 天。</span><span class="sxs-lookup"><span data-stu-id="6682c-115">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days.</span></span> <span data-ttu-id="6682c-116">但是，现在可创建自定义审核日志保留策略，以保留其它审核记录长达一年。</span><span class="sxs-lookup"><span data-stu-id="6682c-116">However, now you can create customized audit log retention policies to retain other audit records for up to one year.</span></span> <span data-ttu-id="6682c-117">可基于下列一个或多个条件创建保留审核记录的策略：</span><span class="sxs-lookup"><span data-stu-id="6682c-117">You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="6682c-118">发生审核活动的 Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="6682c-118">The Microsoft 365 service where the audited activities occur</span></span>

- <span data-ttu-id="6682c-119">特定的审核活动</span><span class="sxs-lookup"><span data-stu-id="6682c-119">Specific audited activities</span></span>

- <span data-ttu-id="6682c-120">执行审核活动的用户</span><span class="sxs-lookup"><span data-stu-id="6682c-120">The user who performs an audited activity</span></span>

<span data-ttu-id="6682c-121">还可以指定与策略和优先级匹配的审核记录时长，从而使指定的策略优先于其它策略。</span><span class="sxs-lookup"><span data-stu-id="6682c-121">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies.</span></span> <span data-ttu-id="6682c-122">另外注意，如果组织中的部分或全部用户需要保留 Exchange、SharePoint 或 Azure Active Directory 审核记录，则所有自定义审核日志保留策略将优先于默认的审核保留策略。</span><span class="sxs-lookup"><span data-stu-id="6682c-122">Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year for some or all the users in your organization.</span></span> <span data-ttu-id="6682c-123">有关详细信息，请参阅[管理审核日志保留策略](audit-log-retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6682c-123">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="6682c-124">访问关键事件进行调查</span><span class="sxs-lookup"><span data-stu-id="6682c-124">Access to crucial events for investigations</span></span>

<span data-ttu-id="6682c-125">关键安全和合规性相关审核事件可帮助你调查可能的违规或其他与法庭有关的调查。</span><span class="sxs-lookup"><span data-stu-id="6682c-125">Crucial security- and compliance-related audit events are ones that can help you investigate possible breaches or other forensic-related investigations.</span></span> <span data-ttu-id="6682c-126">我们发布的第一个此类关键事件是 *MailItemsAccessed* 邮箱审核事件。</span><span class="sxs-lookup"><span data-stu-id="6682c-126">The first crucial event that we're releasing is the *MailItemsAccessed* mailbox auditing event.</span></span> <span data-ttu-id="6682c-127">邮件协议和客户端存取邮件数据时，触发此事件。</span><span class="sxs-lookup"><span data-stu-id="6682c-127">This event is trigger when mail data is accessed by mail protocols and clients.</span></span> <span data-ttu-id="6682c-128">MailItemsAccessed 事件可帮助调查人员识别数据泄露并确定已泄露的邮件的可能范围。</span><span class="sxs-lookup"><span data-stu-id="6682c-128">The MailItemsAccessed event can help investigators identify data breaches and determine the scope of messages that may have been compromised.</span></span> <span data-ttu-id="6682c-129">如果攻击者获得了对电子邮件的访问权限，MailItemsAccessed 事件将被触发，即使邮件实际上未被读取也是如此（即通过“绑定”或“同步” 记录到审核记录中的访问类型）。</span><span class="sxs-lookup"><span data-stu-id="6682c-129">If an attacker gained access to email messages, MailItemsAccessed event will be triggered even if there is no explicit signal that it was actually read (in other words, the type of access such as via bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="6682c-130">新的 MailItemsAccessed 邮箱操作替代 Exchange Online 邮箱审核日志中的 MessageBind ，同时提供下列改进：</span><span class="sxs-lookup"><span data-stu-id="6682c-130">The new MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="6682c-131">MessageBind 仅可为 AuditAdmin 用户登录类型配置；不适用于代理人或所有者操作。</span><span class="sxs-lookup"><span data-stu-id="6682c-131">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions.</span></span> <span data-ttu-id="6682c-132">MailItemsAccessed 适用于所有登录类型。</span><span class="sxs-lookup"><span data-stu-id="6682c-132">MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="6682c-133">MessageBind 只能由邮件客户端覆盖访问。</span><span class="sxs-lookup"><span data-stu-id="6682c-133">MessageBind only covered access by a mail client.</span></span> <span data-ttu-id="6682c-134">它不适用于同步活动。</span><span class="sxs-lookup"><span data-stu-id="6682c-134">It didn't apply to sync activities.</span></span> <span data-ttu-id="6682c-135">“绑定”和“同步”访问类型都会触发 MailItemsAccessed 事件。</span><span class="sxs-lookup"><span data-stu-id="6682c-135">MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="6682c-136">访问同一封电子邮件时，MessageBind 操作会触发多个审核记录，从而导致审核“噪音”。</span><span class="sxs-lookup"><span data-stu-id="6682c-136">MessageBind actions would trigger multiple audit records to be created when the same email message was accessed, which resulted in auditing "noise".</span></span> <span data-ttu-id="6682c-137">相反，MailItemsAccessed 事件聚合在较少的审核记录中。</span><span class="sxs-lookup"><span data-stu-id="6682c-137">In contrast, MailItemsAccessed events are aggregated in fewer audit records.</span></span>

<span data-ttu-id="6682c-138">有关邮箱审核日志的详细信息，参见“[管理邮箱审核](enable-mailbox-auditing.md)”。</span><span class="sxs-lookup"><span data-stu-id="6682c-138">For more information about mailbox auditing logging, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="6682c-139">高带宽访问 Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="6682c-139">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="6682c-140">通过 Office 365 管理活动 API 访问审核日志的组织，会因发布者级别限制而受限。</span><span class="sxs-lookup"><span data-stu-id="6682c-140">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level.</span></span> <span data-ttu-id="6682c-141">这意味着，对于代表多个客户请求数据的发布者而言，限制由所有这些客户共享。</span><span class="sxs-lookup"><span data-stu-id="6682c-141">This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="6682c-142">随着高级审核的发布，我们将从发布者级别的限制迁移到租户级别的限制。</span><span class="sxs-lookup"><span data-stu-id="6682c-142">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit.</span></span> <span data-ttu-id="6682c-143">结果是每个组织都会获得自己完全分配的带宽配额，以访问其审核数据。</span><span class="sxs-lookup"><span data-stu-id="6682c-143">The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data.</span></span> <span data-ttu-id="6682c-144">带宽不是静态的预定义的限制，但根据因素组合进行建模，包括组织中的席位数，该 E5 组织将获得比非 E5 组织更多的带宽。</span><span class="sxs-lookup"><span data-stu-id="6682c-144">The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="6682c-145">所有组织最初每分钟分配 2000 个请求基线。</span><span class="sxs-lookup"><span data-stu-id="6682c-145">All organizations are initially allocated a baseline of 2,000 requests per minute.</span></span> <span data-ttu-id="6682c-146">根据组织的座位数和许可订阅，此限制将显著增加。</span><span class="sxs-lookup"><span data-stu-id="6682c-146">This limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="6682c-147">E5 组织获得的带宽是非 E5 组织的约两倍。</span><span class="sxs-lookup"><span data-stu-id="6682c-147">E5 organizations will get approximately twice as much bandwidth as non-E5 organizations.</span></span> <span data-ttu-id="6682c-148">这也是最大宽带的上限，以保护服务的健康。</span><span class="sxs-lookup"><span data-stu-id="6682c-148">There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="6682c-149">有关更多信息，参见“[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)”中的“API 限制”部分。</span><span class="sxs-lookup"><span data-stu-id="6682c-149">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>
