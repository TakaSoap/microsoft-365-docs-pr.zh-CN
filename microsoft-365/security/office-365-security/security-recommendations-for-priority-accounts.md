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
description: 管理员可以了解如何提升安全设置，并使用其 Microsoft 365 组织中优先级帐户的报告、警报和调查。
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769240"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a><span data-ttu-id="0d3bd-103">Microsoft 365 中优先级帐户的安全建议</span><span class="sxs-lookup"><span data-stu-id="0d3bd-103">Security recommendations for priority accounts in Microsoft 365</span></span>

<span data-ttu-id="0d3bd-104">如果收到来自组织主管的紧急消息，要求您执行某些操作，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="0d3bd-104">What would you do if you received an urgent message from an executive in your organization that asked you to do something?</span></span> <span data-ttu-id="0d3bd-105">是否执行？</span><span class="sxs-lookup"><span data-stu-id="0d3bd-105">Would you do it?</span></span> <span data-ttu-id="0d3bd-106">大多数用户都会遵守该请求。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-106">Most people would comply with the request.</span></span>

<span data-ttu-id="0d3bd-107">对于攻击者，通过转换随机网络获取随机或未知用户的凭据的普通网络钓鱼攻击效率低下。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-107">For attackers, ordinary phishing attacks that cast a random net to get the credentials of random or unknown users are inefficient.</span></span> <span data-ttu-id="0d3bd-108">另一方面，以职位或权威职位的用户为目标的网络钓鱼或钓鱼攻击对攻击者来说更加具有攻击性。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-108">On the other hand, _spear phishing_ or _whaling_ attacks that target users in positions of power or authority are much more rewarding for attackers.</span></span> <span data-ttu-id="0d3bd-109">如果这些优先级帐户遭到入侵，攻击者可能会使用组织中管理员、财务、产品甚至物理访问功能获取对帐户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-109">If these priority accounts are compromised, the attacker might gain access to accounts with admin, financial, product, or even physical access capabilities within the organization.</span></span>

<span data-ttu-id="0d3bd-110">Microsoft 365 和 Microsoft Defender for Office 365 包含许多不同的功能，可帮助你为优先帐户提供其他安全层。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-110">Microsoft 365 and Microsoft Defender for Office 365 contain many different features that can help you to provided additional layers of security for your priority accounts.</span></span> <span data-ttu-id="0d3bd-111">本文讨论了可用功能及其使用方法。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-111">The available features and how to use them are discussed in this article.</span></span>

![图标表单中的安全建议摘要](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a><span data-ttu-id="0d3bd-113">提高优先级帐户的登录安全性</span><span class="sxs-lookup"><span data-stu-id="0d3bd-113">Increase sign-in security for priority accounts</span></span>

<span data-ttu-id="0d3bd-114">优先级帐户要求提高登录安全性。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-114">Priority accounts require increased sign-in security.</span></span> <span data-ttu-id="0d3bd-115">通过要求使用多重身份验证和禁用传统身份验证协议， (MFA) 提高登录安全性。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-115">You can increase their sign-in security by requiring multi-factor authentication (MFA) and disabling legacy authentication protocols.</span></span>

<span data-ttu-id="0d3bd-116">有关说明，请参阅 [步骤 1。使用 MFA 提高远程工作者的登录安全性](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-116">For instructions, see [Step 1. Increase sign-in security for remote workers with MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in).</span></span> <span data-ttu-id="0d3bd-117">虽然本文介绍的是远程工作者，但相同的概念也适用于优先用户。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-117">Although this article is about remote workers, the same concepts apply to priority users.</span></span>

<span data-ttu-id="0d3bd-118">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0d3bd-118">**Notes**:</span></span>

- <span data-ttu-id="0d3bd-119">Exchange Online for Exchange Web Services (EWS) 、Exchange ActiveSync、POP3、IMAP4 和远程 PowerShell 正在弃用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-119">Basic authentication is in the process of being deprecated in Exchange Online for Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4, and remote PowerShell.</span></span> <span data-ttu-id="0d3bd-120">有关详细信息，请参阅此 [博客文章](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-120">For details, see this [blog post](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).</span></span>

- <span data-ttu-id="0d3bd-121">您可以使用 Exchange Online 中的 [身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 策略和 [客户端访问规则](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 来阻止基本身份验证和旧版身份验证协议，如 POP3、IMAP4 和经过身份验证的 SMTP。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-121">You can use [authentication policies](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) and [Client Access Rules](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online to block Basic authentication and legacy authentication protocols like POP3, IMAP4, and authenticated SMTP.</span></span>

- <span data-ttu-id="0d3bd-122">可以在单个邮箱上禁用 POP3 和 IMAP4 访问。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-122">You can disable POP3 and IMAP4 access on individual mailboxes.</span></span> <span data-ttu-id="0d3bd-123">您可以在组织级别禁用经过身份验证的 SMTP，并启用它，以在仍然需要它的特定邮箱上启用它。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-123">You can disable authenticated SMTP at the organizational level and enable it on specific mailboxes that still require it.</span></span> <span data-ttu-id="0d3bd-124">有关说明，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="0d3bd-124">For instructions, see the following topics:</span></span>
  - [<span data-ttu-id="0d3bd-125">为用户启用或禁用 POP3 或 IMAP4 访问</span><span class="sxs-lookup"><span data-stu-id="0d3bd-125">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [<span data-ttu-id="0d3bd-126">启用或禁用 SMTP AUTH (身份验证的客户端 SMTP) </span><span class="sxs-lookup"><span data-stu-id="0d3bd-126">Enable or disable authenticated client SMTP submission (SMTP AUTH)</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a><span data-ttu-id="0d3bd-127">对优先级帐户使用严格预设安全策略</span><span class="sxs-lookup"><span data-stu-id="0d3bd-127">Use Strict preset security policies for priority accounts</span></span>

<span data-ttu-id="0d3bd-128">优先级用户需要针对 Exchange Online Protection、EOP (和 Defender for Office 365) 中提供的各种保护执行更严格的操作。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-128">Priority users require more stringent actions for the various protections that are available in Exchange Online Protection (EOP) and Defender for Office 365.</span></span>

<span data-ttu-id="0d3bd-129">例如，如果邮件用于优先级帐户，则不应将分类为垃圾邮件的邮件发送到"垃圾邮件"文件夹，而应隔离这些相同的邮件。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-129">For example, instead of delivering messages that were classified as spam to the Junk Email folder, you should quarantine those same messages if they're intended for priority accounts.</span></span>

<span data-ttu-id="0d3bd-130">可以使用预设安全策略中的"严格"配置文件为优先级帐户实施此严格方法。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-130">You can implement this stringent approach for priority accounts by using the Strict profile in preset security policies.</span></span>

<span data-ttu-id="0d3bd-131">预设安全策略是一个方便且集中的位置，用于将建议的严格策略设置应用于 EOP 和 Defender for Office 365 的所有保护。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-131">Preset security policies are a convenient and central location to apply our recommended Strict policy settings for all of the protections in EOP and Defender for Office 365.</span></span> <span data-ttu-id="0d3bd-132">有关详细信息，请参阅 [EOP 和 Microsoft Defender for Office 365](preset-security-policies.md)中的预设安全策略。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-132">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

<span data-ttu-id="0d3bd-133">有关严格策略设置与默认和标准策略设置的区别的详细信息，请参阅 EOP 和 [Microsoft Defender for Office 365 安全性的推荐设置](recommended-settings-for-eop-and-office365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-133">For details about how the Strict policy settings differ from the the default and Standard policy settings, see [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="apply-user-tags-to-priority-accounts"></a><span data-ttu-id="0d3bd-134">将用户标记应用于优先级帐户</span><span class="sxs-lookup"><span data-stu-id="0d3bd-134">Apply user tags to priority accounts</span></span>

<span data-ttu-id="0d3bd-135">Microsoft Defender for Office 365 计划 2 (中的用户标记作为 Microsoft 365 E5 或附加订阅) 的一部分，是一种在报告和事件调查中快速标识特定用户或用户组并进行分类的方法。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-135">User tags in Microsoft Defender for Office 365 Plan 2 (as part of Microsoft 365 E5 or an add-on subscription) are a way to quickly identify and classify specific users or groups of users in reports and incident investigations.</span></span>

<span data-ttu-id="0d3bd-136">**优先级帐户** 是一种内置用户标记 (称为系统标记) ，可用于标识涉及优先级帐户的事件和警报。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-136">**Priority accounts** is a type of built-in user tag (known as a _system tag_) that you can use to identify incidents and alerts that involve priority accounts.</span></span> <span data-ttu-id="0d3bd-137">有关优先级帐户 **详细信息，请参阅** 管理和 [监视优先级帐户](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-137">For more information about **priority accounts**, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

<span data-ttu-id="0d3bd-138">您还可以创建自定义标记以进一步标识优先级帐户并进行分类。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-138">You can also create custom tags to further identify and classify your priority accounts.</span></span> <span data-ttu-id="0d3bd-139">有关详细信息，请参阅用户 [标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-139">For more information, see [User tags](user-tags.md).</span></span> <span data-ttu-id="0d3bd-140">请注意，可以在自定义 **用户标记 (** 界面) 系统标记管理优先级帐户。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-140">Note that you can manage **priority accounts** (system tags) in the same interface as custom user tags.</span></span>

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a><span data-ttu-id="0d3bd-141">监视警报、报告和检测中的优先级帐户</span><span class="sxs-lookup"><span data-stu-id="0d3bd-141">Monitor priority accounts in alerts, reports, and detections</span></span>

<span data-ttu-id="0d3bd-142">保护优先级用户并标记用户后，可以使用 EOP 和 Office 365 Defender 中的可用报告、警报和调查来快速识别涉及优先级帐户的事件或检测。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-142">After you secure and tag your priority users, you can use the available reports, alerts, and investigations in EOP and Defender for Office 365 to quickly identify incidents or detections that involve priority accounts.</span></span> <span data-ttu-id="0d3bd-143">下表介绍了支持用户标记的功能。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-143">The features that support user tags are described in the following table.</span></span>

<br>

****

|<span data-ttu-id="0d3bd-144">功能</span><span class="sxs-lookup"><span data-stu-id="0d3bd-144">Feature</span></span>|<span data-ttu-id="0d3bd-145">说明</span><span class="sxs-lookup"><span data-stu-id="0d3bd-145">Description</span></span>|
|---|---|
|<span data-ttu-id="0d3bd-146">警报</span><span class="sxs-lookup"><span data-stu-id="0d3bd-146">Alerts</span></span>|<span data-ttu-id="0d3bd-147">受影响用户的用户标记在安全与合规中心的"查看警报"页上可见并&筛选器。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-147">The user tags of affected users are visible and available as filters on the **View alerts** page in the Security & Compliance Center.</span></span> <span data-ttu-id="0d3bd-148">有关详细信息，请参阅"[查看警报"。](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)</span><span class="sxs-lookup"><span data-stu-id="0d3bd-148">For more information, see [Viewing alerts](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).</span></span>|
|<span data-ttu-id="0d3bd-149">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="0d3bd-149">Threat Explorer</span></span> <p> <span data-ttu-id="0d3bd-150">实时检测</span><span class="sxs-lookup"><span data-stu-id="0d3bd-150">Real-time detections</span></span>|<span data-ttu-id="0d3bd-151">在威胁资源管理器 **(** Microsoft Defender for Office 365 计划 2) 或实时检测 **(** Microsoft Defender for Office 365 计划 1) 中，用户标记显示在电子邮件网格视图和电子邮件详细信息飞出中。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-151">In **Threat Explorer** (Microsoft Defender for Office 365 Plan 2) or **Real-time detections** (Microsoft Defender for Office 365 Plan 1), user tags are visible in the Email grid view and the Email details flyout.</span></span> <span data-ttu-id="0d3bd-152">用户标记也可作为可筛选属性使用。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-152">User tags are also available as a filterable property.</span></span> <span data-ttu-id="0d3bd-153">有关详细信息，请参阅威胁  [资源管理器中的标记](threat-explorer.md#tags-in-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-153">For more information, see  [Tags in Threat Explorer](threat-explorer.md#tags-in-threat-explorer).</span></span>|
|<span data-ttu-id="0d3bd-154">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="0d3bd-154">Campaign Views</span></span>|<span data-ttu-id="0d3bd-155">用户标记是 Microsoft Defender for Office 365 计划 2 的"市场活动视图"中的许多可筛选属性之一。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-155">User tags are one of many filterable properties in Campaign Views in Microsoft Defender for Office 365 Plan 2.</span></span> <span data-ttu-id="0d3bd-156">有关详细信息，请参阅"[宣传活动视图"。](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="0d3bd-156">For more information, see [Campaign Views](campaigns.md).</span></span>|
|<span data-ttu-id="0d3bd-157">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="0d3bd-157">Threat protection status report</span></span>|<span data-ttu-id="0d3bd-158">在威胁防护状态报告中几乎所有视图和详细信息表中，你可以按优先级帐户 **筛选结果**。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-158">In virtually all of the views and detail tables in the **Threat protection status report**, you can filter the results by **priority accounts**.</span></span> <span data-ttu-id="0d3bd-159">有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-159">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="0d3bd-160">优先级帐户的电子邮件问题报告</span><span class="sxs-lookup"><span data-stu-id="0d3bd-160">Email issues for priority accounts report</span></span>|<span data-ttu-id="0d3bd-161">EAC **管理中心** 中的"优先级帐户的电子邮件问题" (EAC) 包含有关优先级帐户的未送达和延迟 **邮件的信息**。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-161">The **Email issues for priority accounts** report in the Exchange admin center (EAC) contains information about undelivered and delayed messages for **priority accounts**.</span></span> <span data-ttu-id="0d3bd-162">有关详细信息，请参阅"优先级 [帐户的电子邮件问题"报告](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)。</span><span class="sxs-lookup"><span data-stu-id="0d3bd-162">For more information, see [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="0d3bd-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3bd-163">See also</span></span>

[<span data-ttu-id="0d3bd-164">宣布在 Microsoft Defender for Office 365 中提供优先帐户保护</span><span class="sxs-lookup"><span data-stu-id="0d3bd-164">Announcing Priority Account Protection in Microsoft Defender for Office 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
