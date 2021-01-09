---
title: Microsoft 365 中优先级帐户的安全建议
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: 管理员可以了解如何提升安全设置，并使用其 Microsoft 365 组织中优先级帐户的报告、警报和调查。
ms.openlocfilehash: acd2eba0acd533d0cd8223f2c433cc023fc23287
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790122"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a><span data-ttu-id="54b04-103">Microsoft 365 中优先级帐户的安全建议</span><span class="sxs-lookup"><span data-stu-id="54b04-103">Security recommendations for priority accounts in Microsoft 365</span></span>

<span data-ttu-id="54b04-104">并非所有用户帐户都有权访问相同的公司信息。</span><span class="sxs-lookup"><span data-stu-id="54b04-104">Not all user accounts have access to the same company information.</span></span> <span data-ttu-id="54b04-105">某些帐户有权访问敏感信息，例如财务数据、产品开发信息、合作伙伴对关键生成系统的访问权限等。</span><span class="sxs-lookup"><span data-stu-id="54b04-105">Some accounts have access to sensitive information, such as financial data, product development information, partner access to critical build systems, and more.</span></span> <span data-ttu-id="54b04-106">有权访问高度机密信息的帐户如果受到威胁，将构成严重的威胁。</span><span class="sxs-lookup"><span data-stu-id="54b04-106">Accounts that have access to highly confidential information pose a serious threat if compromised.</span></span> <span data-ttu-id="54b04-107">我们将这些类型的帐户称为 _优先级帐户_。</span><span class="sxs-lookup"><span data-stu-id="54b04-107">We call these types of accounts _priority accounts_.</span></span> <span data-ttu-id="54b04-108">优先级帐户包括 CEOS、COS、CFOS、基础结构管理员帐户、生成系统帐户等。</span><span class="sxs-lookup"><span data-stu-id="54b04-108">Priority accounts include CEOs, CISOs, CFOs, infrastructure admin accounts, build system accounts and more.</span></span>

<span data-ttu-id="54b04-109">对于攻击者，为普通用户或未知用户转换随机网络的普通网络钓鱼攻击效率低下。</span><span class="sxs-lookup"><span data-stu-id="54b04-109">For attackers, ordinary phishing attacks that cast a random net for ordinary or unknown users are inefficient.</span></span> <span data-ttu-id="54b04-110">另一方面，_以_ 优先级帐户为目标的网络钓鱼或钓鱼攻击对攻击者来说非常具有攻击性。</span><span class="sxs-lookup"><span data-stu-id="54b04-110">On the other hand, _spear phishing_ or _whaling_ attacks that target priority accounts are very rewarding for attackers.</span></span> <span data-ttu-id="54b04-111">因此，优先级帐户需要比普通保护更强大的保护来帮助防止帐户泄露。</span><span class="sxs-lookup"><span data-stu-id="54b04-111">So, priority accounts require stronger than ordinary protection to help prevent account compromise.</span></span>

<span data-ttu-id="54b04-112">Microsoft 365 和 Microsoft Defender for Office 365 包含多个关键功能，这些功能可为优先帐户提供额外的安全层。</span><span class="sxs-lookup"><span data-stu-id="54b04-112">Microsoft 365 and Microsoft Defender for Office 365 contain several key features that provide additional layers of security for your priority accounts.</span></span> <span data-ttu-id="54b04-113">本文介绍这些功能及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="54b04-113">This article describes these capabilities and how to use them.</span></span>

![图标表单中的安全建议摘要](../../media/security-recommendations-for-priority-users.png)

****

|<span data-ttu-id="54b04-115">任务</span><span class="sxs-lookup"><span data-stu-id="54b04-115">Task</span></span>|<span data-ttu-id="54b04-116">所有 Office 365 企业版计划</span><span class="sxs-lookup"><span data-stu-id="54b04-116">All Office 365 Enterprise plans</span></span>|<span data-ttu-id="54b04-117">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="54b04-117">Microsoft 365 E3</span></span>|<span data-ttu-id="54b04-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="54b04-118">Microsoft 365 E5</span></span>|
|---|:---:|:---:|:---:|
|[<span data-ttu-id="54b04-119">提高优先级帐户的登录安全性</span><span class="sxs-lookup"><span data-stu-id="54b04-119">Increase sign-in security for priority accounts</span></span>](#increase-sign-in-security-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="54b04-123">对优先级帐户使用严格预设安全策略</span><span class="sxs-lookup"><span data-stu-id="54b04-123">Use Strict preset security policies for priority accounts</span></span>](#use-strict-preset-security-policies-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="54b04-127">将用户标记应用于优先级帐户</span><span class="sxs-lookup"><span data-stu-id="54b04-127">Apply user tags to priority accounts</span></span>](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[<span data-ttu-id="54b04-129">监视警报、报告和检测中的优先级帐户</span><span class="sxs-lookup"><span data-stu-id="54b04-129">Monitor priority accounts in alerts, reports, and detections</span></span>](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a><span data-ttu-id="54b04-131">提高优先级帐户的登录安全性</span><span class="sxs-lookup"><span data-stu-id="54b04-131">Increase sign-in security for priority accounts</span></span>

<span data-ttu-id="54b04-132">优先级帐户要求提高登录安全性。</span><span class="sxs-lookup"><span data-stu-id="54b04-132">Priority accounts require increased sign-in security.</span></span> <span data-ttu-id="54b04-133">通过要求使用多重身份验证和禁用传统身份验证协议， (MFA) 提高登录安全性。</span><span class="sxs-lookup"><span data-stu-id="54b04-133">You can increase their sign-in security by requiring multi-factor authentication (MFA) and disabling legacy authentication protocols.</span></span>

<span data-ttu-id="54b04-134">有关说明，请参阅 [步骤 1。使用 MFA 提高远程工作者的登录安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="54b04-134">For instructions, see [Step 1. Increase sign-in security for remote workers with MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in).</span></span> <span data-ttu-id="54b04-135">虽然本文介绍的是远程工作者，但相同的概念也适用于优先用户。</span><span class="sxs-lookup"><span data-stu-id="54b04-135">Although this article is about remote workers, the same concepts apply to priority users.</span></span>

<span data-ttu-id="54b04-136">**注意**：我们强烈建议您全局禁用所有优先级用户的旧版身份验证协议，如上一篇文章中所述。</span><span class="sxs-lookup"><span data-stu-id="54b04-136">**Note**: We strongly recommend that you globally disable legacy authentication protocols for all priority users as described in the previous article.</span></span> <span data-ttu-id="54b04-137">如果您的业务需求阻止您这样做，Exchange Online 会提供以下控件来帮助限制旧版身份验证协议的范围：</span><span class="sxs-lookup"><span data-stu-id="54b04-137">If your business requirements prevent you from doing so, Exchange Online offers the following controls to help limit the scope of legacy authentication protocols:</span></span>

- <span data-ttu-id="54b04-138">您可以使用 [Exchange](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) Online 中的身份验证策略和客户端访问 [规则](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 来阻止或允许特定用户使用基本身份验证和旧版身份验证协议（如 POP3、IMAP4 和经过身份验证的 SMTP）。</span><span class="sxs-lookup"><span data-stu-id="54b04-138">You can use [authentication policies](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) and [Client Access Rules](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online to block or allow Basic authentication and legacy authentication protocols like POP3, IMAP4, and authenticated SMTP for specific users.</span></span>

- <span data-ttu-id="54b04-139">可以在单个邮箱上禁用 POP3 和 IMAP4 访问。</span><span class="sxs-lookup"><span data-stu-id="54b04-139">You can disable POP3 and IMAP4 access on individual mailboxes.</span></span> <span data-ttu-id="54b04-140">您可以在组织级别禁用经过身份验证的 SMTP，并启用它，以在仍然需要它的特定邮箱上启用它。</span><span class="sxs-lookup"><span data-stu-id="54b04-140">You can disable authenticated SMTP at the organizational level and enable it on specific mailboxes that still require it.</span></span> <span data-ttu-id="54b04-141">有关说明，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="54b04-141">For instructions, see the following topics:</span></span>
  - [<span data-ttu-id="54b04-142">为用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="54b04-142">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [<span data-ttu-id="54b04-143">启用或禁用 SMTP AUTH (身份验证的客户端 SMTP) </span><span class="sxs-lookup"><span data-stu-id="54b04-143">Enable or disable authenticated client SMTP submission (SMTP AUTH)</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

<span data-ttu-id="54b04-144">还值得注意的是，Exchange Online for Exchange Web Services (EWS) 、Exchange ActiveSync、POP3、IMAP4 和远程 PowerShell 中正在弃用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="54b04-144">It's also worth noting that Basic authentication is in the process of being deprecated in Exchange Online for Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4, and remote PowerShell.</span></span> <span data-ttu-id="54b04-145">有关详细信息，请参阅此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。</span><span class="sxs-lookup"><span data-stu-id="54b04-145">For details, see this [blog post](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).</span></span>

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a><span data-ttu-id="54b04-146">对优先级帐户使用严格预设安全策略</span><span class="sxs-lookup"><span data-stu-id="54b04-146">Use Strict preset security policies for priority accounts</span></span>

<span data-ttu-id="54b04-147">优先级用户需要针对 Exchange Online Protection、EOP (和 Defender for Office 365) 中提供的各种保护执行更严格的操作。</span><span class="sxs-lookup"><span data-stu-id="54b04-147">Priority users require more stringent actions for the various protections that are available in Exchange Online Protection (EOP) and Defender for Office 365.</span></span>

<span data-ttu-id="54b04-148">例如，如果邮件用于优先级帐户，则不应将分类为垃圾邮件的邮件发送到"垃圾邮件"文件夹，而应隔离这些相同的邮件。</span><span class="sxs-lookup"><span data-stu-id="54b04-148">For example, instead of delivering messages that were classified as spam to the Junk Email folder, you should quarantine those same messages if they're intended for priority accounts.</span></span>

<span data-ttu-id="54b04-149">可以通过在预设安全策略中使用"严格"配置文件，为优先级帐户实施此严格的方法。</span><span class="sxs-lookup"><span data-stu-id="54b04-149">You can implement this stringent approach for priority accounts by using the Strict profile in preset security policies.</span></span>

<span data-ttu-id="54b04-150">预设安全策略是一个方便且集中的位置，用于将建议的严格策略设置应用于 EOP 和 Defender for Office 365 的所有保护。</span><span class="sxs-lookup"><span data-stu-id="54b04-150">Preset security policies are a convenient and central location to apply our recommended Strict policy settings for all of the protections in EOP and Defender for Office 365.</span></span> <span data-ttu-id="54b04-151">有关详细信息，请参阅 [EOP 和 Microsoft Defender for Office 365](preset-security-policies.md)中的预设安全策略。</span><span class="sxs-lookup"><span data-stu-id="54b04-151">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

<span data-ttu-id="54b04-152">有关严格策略设置与默认和标准策略设置之间如何不同的详细信息，请参阅 EOP 和 [Microsoft Defender for Office 365 安全推荐设置](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="54b04-152">For details about how the Strict policy settings differ from the the default and Standard policy settings, see [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="apply-user-tags-to-priority-accounts"></a><span data-ttu-id="54b04-153">将用户标记应用于优先级帐户</span><span class="sxs-lookup"><span data-stu-id="54b04-153">Apply user tags to priority accounts</span></span>

<span data-ttu-id="54b04-154">作为 Microsoft 365 E5 或附加订阅) 的一部分，Microsoft Defender for Office 365 计划 2 (中的用户标记是一种在报告和事件调查中快速识别和分类特定用户或用户组的方法。</span><span class="sxs-lookup"><span data-stu-id="54b04-154">User tags in Microsoft Defender for Office 365 Plan 2 (as part of Microsoft 365 E5 or an add-on subscription) are a way to quickly identify and classify specific users or groups of users in reports and incident investigations.</span></span>

<span data-ttu-id="54b04-155">**优先级帐户** 是一种内置用户标记 (称为系统标记) ，可用于标识涉及优先级帐户的事件和警报。</span><span class="sxs-lookup"><span data-stu-id="54b04-155">**Priority accounts** is a type of built-in user tag (known as a _system tag_) that you can use to identify incidents and alerts that involve priority accounts.</span></span> <span data-ttu-id="54b04-156">有关优先级帐户 **详细信息，请参阅** 管理和 [监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="54b04-156">For more information about **priority accounts**, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

<span data-ttu-id="54b04-157">您还可以创建自定义标记以进一步标识和分类优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="54b04-157">You can also create custom tags to further identify and classify your priority accounts.</span></span> <span data-ttu-id="54b04-158">有关详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="54b04-158">For more information, see [User tags](user-tags.md).</span></span> <span data-ttu-id="54b04-159">请注意，可以在自定义 **用户标记 (** 界面) 系统标记管理优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="54b04-159">Note that you can manage **priority accounts** (system tags) in the same interface as custom user tags.</span></span>

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a><span data-ttu-id="54b04-160">监视警报、报告和检测中的优先级帐户</span><span class="sxs-lookup"><span data-stu-id="54b04-160">Monitor priority accounts in alerts, reports, and detections</span></span>

<span data-ttu-id="54b04-161">保护优先级用户并标记用户后，可以使用 EOP 和 Office 365 Defender 中的可用报告、警报和调查来快速识别涉及优先级帐户的事件或检测。</span><span class="sxs-lookup"><span data-stu-id="54b04-161">After you secure and tag your priority users, you can use the available reports, alerts, and investigations in EOP and Defender for Office 365 to quickly identify incidents or detections that involve priority accounts.</span></span> <span data-ttu-id="54b04-162">下表介绍了支持用户标记的功能。</span><span class="sxs-lookup"><span data-stu-id="54b04-162">The features that support user tags are described in the following table.</span></span>

<br>

****

|<span data-ttu-id="54b04-163">功能</span><span class="sxs-lookup"><span data-stu-id="54b04-163">Feature</span></span>|<span data-ttu-id="54b04-164">说明</span><span class="sxs-lookup"><span data-stu-id="54b04-164">Description</span></span>|
|---|---|
|<span data-ttu-id="54b04-165">警报</span><span class="sxs-lookup"><span data-stu-id="54b04-165">Alerts</span></span>|<span data-ttu-id="54b04-166">受影响用户的用户标记在安全与合规中心的"查看警报"页上可见&筛选器。</span><span class="sxs-lookup"><span data-stu-id="54b04-166">The user tags of affected users are visible and available as filters on the **View alerts** page in the Security & Compliance Center.</span></span> <span data-ttu-id="54b04-167">有关详细信息，请参阅"[查看警报"。](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)</span><span class="sxs-lookup"><span data-stu-id="54b04-167">For more information, see [Viewing alerts](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).</span></span>|
|<span data-ttu-id="54b04-168">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="54b04-168">Threat Explorer</span></span> <p> <span data-ttu-id="54b04-169">实时检测</span><span class="sxs-lookup"><span data-stu-id="54b04-169">Real-time detections</span></span>|<span data-ttu-id="54b04-170">在威胁资源管理器 **(** Microsoft Defender for Office 365 计划 2) 或实时检测 **(** Microsoft Defender for Office 365 计划 1) 中，用户标记显示在电子邮件网格视图和电子邮件详细信息飞出中。</span><span class="sxs-lookup"><span data-stu-id="54b04-170">In **Threat Explorer** (Microsoft Defender for Office 365 Plan 2) or **Real-time detections** (Microsoft Defender for Office 365 Plan 1), user tags are visible in the Email grid view and the Email details flyout.</span></span> <span data-ttu-id="54b04-171">用户标记也可作为可筛选属性使用。</span><span class="sxs-lookup"><span data-stu-id="54b04-171">User tags are also available as a filterable property.</span></span> <span data-ttu-id="54b04-172">有关详细信息，请参阅威胁  [资源管理器中的标记](threat-explorer.md#tags-in-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="54b04-172">For more information, see  [Tags in Threat Explorer](threat-explorer.md#tags-in-threat-explorer).</span></span>|
|<span data-ttu-id="54b04-173">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="54b04-173">Campaign Views</span></span>|<span data-ttu-id="54b04-174">用户标记是 Microsoft Defender for Office 365 计划 2 的"市场活动视图"中的许多可筛选属性之一。</span><span class="sxs-lookup"><span data-stu-id="54b04-174">User tags are one of many filterable properties in Campaign Views in Microsoft Defender for Office 365 Plan 2.</span></span> <span data-ttu-id="54b04-175">有关详细信息，请参阅"[宣传活动视图"。](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="54b04-175">For more information, see [Campaign Views](campaigns.md).</span></span>|
|<span data-ttu-id="54b04-176">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="54b04-176">Threat protection status report</span></span>|<span data-ttu-id="54b04-177">在威胁防护状态报告中几乎所有视图和详细信息表中，可以按优先级帐户 **筛选结果**。</span><span class="sxs-lookup"><span data-stu-id="54b04-177">In virtually all of the views and detail tables in the **Threat protection status report**, you can filter the results by **priority accounts**.</span></span> <span data-ttu-id="54b04-178">有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="54b04-178">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="54b04-179">优先级帐户的电子邮件问题报告</span><span class="sxs-lookup"><span data-stu-id="54b04-179">Email issues for priority accounts report</span></span>|<span data-ttu-id="54b04-180">EAC **(** Exchange 管理中心中的"优先级帐户的电子邮件问题") 包含有关优先级帐户的未送达和延迟 **邮件的信息**。</span><span class="sxs-lookup"><span data-stu-id="54b04-180">The **Email issues for priority accounts** report in the Exchange admin center (EAC) contains information about undelivered and delayed messages for **priority accounts**.</span></span> <span data-ttu-id="54b04-181">有关详细信息，请参阅"优先级[帐户的电子邮件问题报告"。](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="54b04-181">For more information, see [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="54b04-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54b04-182">See also</span></span>

[<span data-ttu-id="54b04-183">宣布在 Microsoft Defender for Office 365 中提供优先帐户保护</span><span class="sxs-lookup"><span data-stu-id="54b04-183">Announcing Priority Account Protection in Microsoft Defender for Office 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
