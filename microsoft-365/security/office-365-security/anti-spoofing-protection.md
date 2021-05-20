---
title: 防欺骗保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: 管理员可以了解 Exchange Online Protection (EOP) 中提供的防欺骗功能，该功能有助于缓解来自虚假发件人和域的网络钓鱼攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7680c2f4eae54aa53eba72b328baf1bf92fbcf98
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537963"
---
# <a name="anti-spoofing-protection-in-eop"></a><span data-ttu-id="d0593-103">EOP 中的防欺骗防护</span><span class="sxs-lookup"><span data-stu-id="d0593-103">Anti-spoofing protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d0593-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="d0593-104">**Applies to**</span></span>
- [<span data-ttu-id="d0593-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d0593-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d0593-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="d0593-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d0593-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0593-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d0593-108">无论是针对拥有 Exchange Online 邮箱的 Microsoft 365 组织，还是没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织，EOP 都将提供帮助保护你的组织免受虚假（伪造）发件人威胁的功能。</span><span class="sxs-lookup"><span data-stu-id="d0593-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>

<span data-ttu-id="d0593-109">在为用户提供保护方面，Microsoft 非常重视网络钓鱼的威胁。</span><span class="sxs-lookup"><span data-stu-id="d0593-109">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="d0593-110">欺骗是黑客使用的一种常见技术。</span><span class="sxs-lookup"><span data-stu-id="d0593-110">Spoofing is a common technique that's used by attackers.</span></span> <span data-ttu-id="d0593-111">**欺骗邮件看似来自某人或某处，其实并非其真实来源**。</span><span class="sxs-lookup"><span data-stu-id="d0593-111">**Spoofed messages appear to originate from someone or somewhere other than the actual source**.</span></span> <span data-ttu-id="d0593-112">此技术通常在专门获取用户凭据的网络钓鱼活动中使用。</span><span class="sxs-lookup"><span data-stu-id="d0593-112">This technique is often used in phishing campaigns that are designed to obtain user credentials.</span></span> <span data-ttu-id="d0593-113">EOP 中的反欺骗技术专门检查邮件正文中的“发件人”标头（用于显示电子邮件客户端中的邮件发件人）。</span><span class="sxs-lookup"><span data-stu-id="d0593-113">The anti-spoofing technology in EOP specifically examines forgery of the From header in the message body (used to display the message sender in email clients).</span></span> <span data-ttu-id="d0593-114">如果 EOP 高度确信“发件人”标头是伪造的，该邮件将被识别为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="d0593-114">When EOP has high confidence that the From header is forged, the message is identified as spoofed.</span></span>

<span data-ttu-id="d0593-115">EOP 中提供了以下反欺骗技术：</span><span class="sxs-lookup"><span data-stu-id="d0593-115">The following anti-spoofing technologies are available in EOP:</span></span>

- <span data-ttu-id="d0593-116">**电子邮件身份验证**：DNS 中的 SPF、DKIM 和 DMARC 记录使用的电子邮件身份验证（也称为电子邮件验证）是任何反欺骗工作必不可少的一部分。</span><span class="sxs-lookup"><span data-stu-id="d0593-116">**Email authentication**: An integral part of any anti-spoofing effort is the use of email authentication (also known as email validation) by SPF, DKIM, and DMARC records in DNS.</span></span> <span data-ttu-id="d0593-117">可以为你的域配置这些记录，以便目标电子邮件系统能够检查声称来自域中发件人的邮件的有效性。</span><span class="sxs-lookup"><span data-stu-id="d0593-117">You can configure these records for your domains so destination email systems can check the validity of messages that claim to be from senders in your domains.</span></span> <span data-ttu-id="d0593-118">对于入站邮件，Microsoft 365 需要针对发件人域的电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0593-118">For inbound messages, Microsoft 365 requires email authentication for sender domains.</span></span> <span data-ttu-id="d0593-119">有关详细信息，请参阅 [Microsoft 365 中的电子邮件身份验证](email-validation-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-119">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

  <span data-ttu-id="d0593-120">EOP 可分析并阻止标准电子邮件身份验证方法和发件人信誉技术组合无法验证的邮件。</span><span class="sxs-lookup"><span data-stu-id="d0593-120">EOP analyzes and blocks messages that can't be authenticated by the combination of standard email authentication methods and sender reputation techniques.</span></span>

  ![EOP 反欺骗检查](../../media/eop-anti-spoofing-protection.png)

- <span data-ttu-id="d0593-122">**欺骗智能保护**：审查最近 7 天内来自内外部域发件人的欺骗邮件，并允许或阻止这些发件人。</span><span class="sxs-lookup"><span data-stu-id="d0593-122">**Spoof intelligence insight**: Review spoofed messages from senders in internal and external domains during the last 7 days, and allow or block those senders.</span></span> <span data-ttu-id="d0593-123">有关详细信息，请参阅[在 EOP 中配置欺骗智能保护](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-123">For more information, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="d0593-124">**在“租户允许/阻止列表”中允许或阻止欺骗发件人**：如果替代欺骗智能保护中的漏洞，欺骗发件人将成为仅在“租户允许/阻止列表”的“**欺骗**”选项卡上显示的手动允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="d0593-124">**Allow or block spoofed senders in the Tenant Allow/Block List**: When you override the verdict in the spoof intelligence insight, the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="d0593-125">在欺骗智能保护检测到欺骗发件人之前，还可手动为其创建允许或阻止条目。</span><span class="sxs-lookup"><span data-stu-id="d0593-125">You can also manually create allow or block entries for spoof senders before they're detected by spoof intelligence.</span></span> <span data-ttu-id="d0593-126">有关详细信息，请参阅[管理 EOP 中的租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-126">For more information, see [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="d0593-127">**反钓鱼策略**：在 EOP 中，反钓鱼策略包含以下反欺骗设置：</span><span class="sxs-lookup"><span data-stu-id="d0593-127">**Anti-phishing policies**: In EOP, anti-phishing policies contain the following anti-spoofing settings:</span></span>
  - <span data-ttu-id="d0593-128">打开或关闭欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="d0593-128">Turn spoof intelligence on or off.</span></span>
  - <span data-ttu-id="d0593-129">打开或关闭 Outlook 中未经身份验证的发件人标识。</span><span class="sxs-lookup"><span data-stu-id="d0593-129">Turn unauthenticated sender identification in Outlook on or off.</span></span>
  - <span data-ttu-id="d0593-130">指定对阻止的欺骗发件人的操作。</span><span class="sxs-lookup"><span data-stu-id="d0593-130">Specify the action for blocked spoofed senders.</span></span>

  <span data-ttu-id="d0593-131">有关详细信息，请参阅[反钓鱼策略中的“欺骗”设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="d0593-131">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

  <span data-ttu-id="d0593-132">**注意**：Microsoft Defender for Office 365 中的反钓鱼策略包含添加保护，包括 **模拟** 保护。</span><span class="sxs-lookup"><span data-stu-id="d0593-132">**Note**: Anti-phishing policies in Microsoft Defender for Office 365 contain addition protections, including **impersonation** protection.</span></span> <span data-ttu-id="d0593-133">有关详细信息，请参阅 [Microsoft Defender for Office 365 中反钓鱼策略中的“独占”设置](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="d0593-133">For more information, see [Exclusive settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="d0593-134">**欺骗检测报告**：有关详细信息，请参阅[欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="d0593-134">**Spoof detections report**: For more information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

  <span data-ttu-id="d0593-135">**注意**：Defender for Office 365 组织也可使用实时检测（计划 1）或威胁资源管理器（计划 2）查看有关钓鱼尝试的信息。</span><span class="sxs-lookup"><span data-stu-id="d0593-135">**Note**: Defender for Office 365 organizations can also use Real-time detections (Plan 1) or Threat Explorer (Plan 2) to view information about phishing attempts.</span></span> <span data-ttu-id="d0593-136">有关详细信息，请参阅 [Microsoft 365 威胁调查和响应](office-365-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-136">For more information, see [Microsoft 365 threat investigation and response](office-365-ti.md).</span></span>

## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="d0593-137">如何在网络钓鱼攻击中使用欺骗</span><span class="sxs-lookup"><span data-stu-id="d0593-137">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="d0593-138">欺骗邮件会对用户造成以下负面影响：</span><span class="sxs-lookup"><span data-stu-id="d0593-138">Spoofing messages have the following negative implications for users:</span></span>

- <span data-ttu-id="d0593-139">**欺骗邮件设备用户**：欺骗邮件可能会欺骗收件人点击链接并放弃使用其凭据、下载恶意软件或向邮件回复敏感内容（称为商务电子邮件入侵或 BEC）。</span><span class="sxs-lookup"><span data-stu-id="d0593-139">**Spoofed messages deceive users**: A spoofed message might trick the recipient into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (known as a business email compromise or BEC).</span></span>

  <span data-ttu-id="d0593-140">以下是一封具有伪造发件人 msoutlook94@service.outlook.com 的网络钓鱼邮件示例：</span><span class="sxs-lookup"><span data-stu-id="d0593-140">The following message is an example of phishing that uses the spoofed sender msoutlook94@service.outlook.com:</span></span>

  ![冒充 service.outlook.com 的网络钓鱼邮件](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  <span data-ttu-id="d0593-142">此邮件并非来自 service.outlook.com，而是攻击者伪造“**发件人**”标头字段，使它看起来像是这样。</span><span class="sxs-lookup"><span data-stu-id="d0593-142">This message didn't come from service.outlook.com, but the attacker spoofed the **From** header field to make it look like it did.</span></span> <span data-ttu-id="d0593-143">这种做法试图欺骗收件人单击“**更改密码**”链接并放弃使用其凭据。</span><span class="sxs-lookup"><span data-stu-id="d0593-143">This was an attempt to trick the recipient into clicking the **change your password** link and giving up their credentials.</span></span>

  <span data-ttu-id="d0593-144">以下邮件是使用欺骗电子邮件域 contoso.com 的 BEC 示例：</span><span class="sxs-lookup"><span data-stu-id="d0593-144">The following message is an example of BEC that uses the spoofed email domain contoso.com:</span></span>

  ![网络钓鱼邮件 - 商务电子邮件入侵](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  <span data-ttu-id="d0593-146">该邮件看似合法，但发件人其实是伪造的。</span><span class="sxs-lookup"><span data-stu-id="d0593-146">The message looks legitimate, but the sender is spoofed.</span></span>

- <span data-ttu-id="d0593-147">**用户混淆了真实邮件和虚假邮件**：即使是知道网络钓鱼的用户也可能很难看出真实邮件与欺骗邮件之间的差异。</span><span class="sxs-lookup"><span data-stu-id="d0593-147">**Users confuse real messages for fake ones**: Even users who know about phishing might have difficulty seeing the differences between real messages and spoofed messages.</span></span>

  <span data-ttu-id="d0593-148">例如，以下是来自 Microsoft 安全帐户部门的真实密码重置邮件的示例：</span><span class="sxs-lookup"><span data-stu-id="d0593-148">The following message is an example of a real password reset message from the Microsoft Security account:</span></span>

  ![Microsoft 合法密码重置](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  <span data-ttu-id="d0593-p108">邮件确实来自 Microsoft，但用户已经习惯于持怀疑态度。因为难以区分真正的密码重置邮件和伪造的邮件，用户可能会忽略该消息，而将其报告为垃圾邮件，或者不必要地将该消息作为网络钓鱼报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d0593-p108">The message really did come from Microsoft, but users have been conditioned to be suspicious. Because it's difficult to the difference between a real password reset message and a fake one, users might ignore the message, report it as spam, or unnecessarily report the message to Microsoft as phishing.</span></span>

## <a name="different-types-of-spoofing"></a><span data-ttu-id="d0593-152">不同类型的欺骗</span><span class="sxs-lookup"><span data-stu-id="d0593-152">Different types of spoofing</span></span>

<span data-ttu-id="d0593-153">Microsoft 区分两种不同类型的欺骗邮件：</span><span class="sxs-lookup"><span data-stu-id="d0593-153">Microsoft differentiates between two different types of spoofed messages:</span></span>

- <span data-ttu-id="d0593-154">**组织内欺骗**：也称为 _自我欺骗_。</span><span class="sxs-lookup"><span data-stu-id="d0593-154">**Intra-org spoofing**: Also known as _self-to-self_ spoofing.</span></span> <span data-ttu-id="d0593-155">例如：</span><span class="sxs-lookup"><span data-stu-id="d0593-155">For example:</span></span>

  - <span data-ttu-id="d0593-156">发件人和收件人位于同一域：</span><span class="sxs-lookup"><span data-stu-id="d0593-156">The sender and recipient are in the same domain:</span></span>
    > <span data-ttu-id="d0593-157">发件人：chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0593-157">From: chris@contoso.com</span></span> <br> <span data-ttu-id="d0593-158">收件人：michelle@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0593-158">To: michelle@contoso.com</span></span>

  - <span data-ttu-id="d0593-159">发件人和收件人位于同一域的子域：</span><span class="sxs-lookup"><span data-stu-id="d0593-159">The sender and the recipient are in subdomains of the same domain:</span></span>
    > <span data-ttu-id="d0593-160">发件人：laura@marketing.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d0593-160">From: laura@marketing.fabrikam.com</span></span> <br> <span data-ttu-id="d0593-161">收件人：julia@engineering.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d0593-161">To: julia@engineering.fabrikam.com</span></span>

  - <span data-ttu-id="d0593-162">发件人和收件人位于属于同一组织的不同域（即，两个域均配置为同一组织中的[接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)）：</span><span class="sxs-lookup"><span data-stu-id="d0593-162">The sender and recipient are in different domains that belong to the same organization (that is, both domains are configured as [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the same organization):</span></span>
    > <span data-ttu-id="d0593-163">发件人：sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d0593-163">From: sender @ microsoft.com</span></span> <br> <span data-ttu-id="d0593-164">收件人：recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="d0593-164">To: recipient @ bing.com</span></span>

    <span data-ttu-id="d0593-165">电子邮件地址中使用空格，以防垃圾邮件机器人收集邮件。</span><span class="sxs-lookup"><span data-stu-id="d0593-165">Spaces are used in the email addresses to prevent spambot harvesting.</span></span>

  <span data-ttu-id="d0593-166">由于组织内欺骗而导致未通过[复合身份验证](email-validation-and-authentication.md#composite-authentication)的邮件包含以下标头值：</span><span class="sxs-lookup"><span data-stu-id="d0593-166">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to intra-org spoofing contain the following header values:</span></span>

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - <span data-ttu-id="d0593-167">`reason=6xx` 表示组织内欺骗。</span><span class="sxs-lookup"><span data-stu-id="d0593-167">`reason=6xx` indicates intra-org spoofing.</span></span>

  - <span data-ttu-id="d0593-168">SFTY 是邮件的安全级别。</span><span class="sxs-lookup"><span data-stu-id="d0593-168">SFTY is the safety level of the message.</span></span> <span data-ttu-id="d0593-169">9 表示网络钓鱼，11 表示组织内欺骗。</span><span class="sxs-lookup"><span data-stu-id="d0593-169">9 indicates phishing, .11 indicates intra-org spoofing.</span></span>

- <span data-ttu-id="d0593-170">**跨域欺骗**：发件人和收件人域不同，相互之间没有任何关系（也称为外部域）。</span><span class="sxs-lookup"><span data-stu-id="d0593-170">**Cross-domain spoofing**: The sender and recipient domains are different, and have no relationship to each other (also known as external domains).</span></span> <span data-ttu-id="d0593-171">例如：</span><span class="sxs-lookup"><span data-stu-id="d0593-171">For example:</span></span>
    > <span data-ttu-id="d0593-172">发件人：chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d0593-172">From: chris@contoso.com</span></span> <br> <span data-ttu-id="d0593-173">收件人：michelle@tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="d0593-173">To: michelle@tailspintoys.com</span></span>

  <span data-ttu-id="d0593-174">由于跨域欺骗而导致未通过[复合身份验证](email-validation-and-authentication.md#composite-authentication)的邮件包含以下标头值：</span><span class="sxs-lookup"><span data-stu-id="d0593-174">Messages that fail [composite authentication](email-validation-and-authentication.md#composite-authentication) due to cross-domain spoofing contain the following headers values:</span></span>

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - <span data-ttu-id="d0593-175">`reason=000` 表示邮件未通过显式电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0593-175">`reason=000` indicates the message failed explicit email authentication.</span></span> <span data-ttu-id="d0593-176">`reason=001` 表示邮件未通过隐式电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0593-176">`reason=001` indicates the message failed implicit email authentication.</span></span>

  - <span data-ttu-id="d0593-177">`SFTY` SFTY 是邮件的安全级别。</span><span class="sxs-lookup"><span data-stu-id="d0593-177">`SFTY` is the safety level of the message.</span></span> <span data-ttu-id="d0593-178">9 表示网络钓鱼，22 表示跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="d0593-178">9 indicates phishing, .22 indicates cross-domain spoofing.</span></span>

> [!NOTE]
> <span data-ttu-id="d0593-179">如果您收到了类似 \***compauth=fail reason=###** _ 且需要知道组合身份验证 （compauth） 和欺骗相关值的消息，请参阅 [_Anti-spam message headers in Microsoft 365\*](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-179">If you've gotten a message like \***compauth=fail reason=###** _ and need to know about composite authentication (compauth), and the values related to spoofing, see [_Anti-spam message headers in Microsoft 365\*](anti-spam-message-headers.md).</span></span> <span data-ttu-id="d0593-180">或者直接转到 [*原因*](anti-spam-message-headers.md)代码。</span><span class="sxs-lookup"><span data-stu-id="d0593-180">Or go directly to the [*reason*](anti-spam-message-headers.md) codes.</span></span>

<span data-ttu-id="d0593-181">有关 DMARC 的详细信息，请参阅[在 Microsoft 365 中使用 DMARC 来验证电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-181">For more information about DMARC, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="problems-with-anti-spoofing-protection"></a><span data-ttu-id="d0593-182">反欺骗防护方面的问题</span><span class="sxs-lookup"><span data-stu-id="d0593-182">Problems with anti-spoofing protection</span></span>

<span data-ttu-id="d0593-183">由于转发和修改邮件的方式，邮件列表（也称为讨论列表）存在反欺骗问题。</span><span class="sxs-lookup"><span data-stu-id="d0593-183">Mailing lists (also known as discussion lists) are known to have problems with anti-spoofing due to the way they forward and modify messages.</span></span>

<span data-ttu-id="d0593-184">例如，Gabriela Laureano (glaureano@contoso.com) 有兴趣赏鸟，他加入了邮件列表 birdwatchers@fabrikam.com，并向列表发送了以下邮件：</span><span class="sxs-lookup"><span data-stu-id="d0593-184">For example, Gabriela Laureano (glaureano@contoso.com) is interested in bird watching, joins the mailing list birdwatchers@fabrikam.com, and sends the following message to the list:</span></span>

> <span data-ttu-id="d0593-185">**发件人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="d0593-185">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="d0593-186">**收件人:** 赏鸟者讨论列表\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="d0593-186">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="d0593-187">**主题：** 本周到瑞尼尔山顶</span><span class="sxs-lookup"><span data-stu-id="d0593-187">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="d0593-188">观赏蓝鸟</span><span class="sxs-lookup"><span data-stu-id="d0593-188">Rainier this week</span></span> <p> <span data-ttu-id="d0593-p116">有人想本周去雷尼尔山看风景吗？</span><span class="sxs-lookup"><span data-stu-id="d0593-p116">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>

<span data-ttu-id="d0593-191">邮件列表服务器接收邮件，修改其内容并将其重播给列表中的成员。</span><span class="sxs-lookup"><span data-stu-id="d0593-191">The mailing list server receives the message, modifies its content, and replays it to the members of list.</span></span> <span data-ttu-id="d0593-192">重播的邮件具有相同的“发件人”地址 (glaureano @ contoso.com)，但向主题行添加了标记并在邮件底部添加了页脚。</span><span class="sxs-lookup"><span data-stu-id="d0593-192">The replayed message has the same From address (glaureano@contoso.com), but a tag is added to the subject line, and a footer is added to the bottom of the message.</span></span> <span data-ttu-id="d0593-193">这种类型的修改在邮件列表中很常见，并且可能导致欺骗误报。</span><span class="sxs-lookup"><span data-stu-id="d0593-193">This type of modification is common in mailing lists, and may result in false positives for spoofing.</span></span>

> <span data-ttu-id="d0593-194">**发件人:** "Gabriela Laureano" \<glaureano@contoso.com\></span><span class="sxs-lookup"><span data-stu-id="d0593-194">**From:** "Gabriela Laureano" \<glaureano@contoso.com\></span></span> <br> <span data-ttu-id="d0593-195">**收件人:** 赏鸟者讨论列表\<birdwatchers@fabrikam.com\></span><span class="sxs-lookup"><span data-stu-id="d0593-195">**To:** Birdwatcher's Discussion List \<birdwatchers@fabrikam.com\></span></span> <br> <span data-ttu-id="d0593-196">**主题：**[赏鸟者]本周到瑞尼尔山顶</span><span class="sxs-lookup"><span data-stu-id="d0593-196">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="d0593-197">观赏蓝鸟</span><span class="sxs-lookup"><span data-stu-id="d0593-197">Rainier this week</span></span> <p> <span data-ttu-id="d0593-p119">有人想本周去雷尼尔山看风景吗？ </span><span class="sxs-lookup"><span data-stu-id="d0593-p119">Anyone want to check out the viewing this week from Mt. Rainier? </span></span><p> <span data-ttu-id="d0593-200">此邮件已发送到赏鸟者讨论列表。</span><span class="sxs-lookup"><span data-stu-id="d0593-200">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="d0593-201">可随时取消订阅。</span><span class="sxs-lookup"><span data-stu-id="d0593-201">You can unsubscribe at any time.</span></span>

<span data-ttu-id="d0593-202">要帮助邮件列表邮件通过反欺骗检查，请根据是否控制邮件列表执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0593-202">To help mailing list messages pass anti-spoofing checks, do following steps based on whether you control the mailing list:</span></span>

- <span data-ttu-id="d0593-203">组织拥有邮件列表：</span><span class="sxs-lookup"><span data-stu-id="d0593-203">Your organization owns the mailing list:</span></span>

  - <span data-ttu-id="d0593-204">查看 DMARC.org 上的常见问题解答：[我在操作邮件列表时想与 DMARC 进行交互，应该怎么办？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)。</span><span class="sxs-lookup"><span data-stu-id="d0593-204">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).</span></span>

  - <span data-ttu-id="d0593-205">阅读此博客文章中的说明：[关于邮件列表操作员与 DMARC 进行交互以避免失败的提示](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures)。</span><span class="sxs-lookup"><span data-stu-id="d0593-205">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures).</span></span>

  - <span data-ttu-id="d0593-206">考虑在邮件列表服务器上安装更新以支持 ARC，请参阅 <http://arc-spec.org></span><span class="sxs-lookup"><span data-stu-id="d0593-206">Consider installing updates on your mailing list server to support ARC, see <http://arc-spec.org>.</span></span>

- <span data-ttu-id="d0593-207">组织不拥有邮件列表：</span><span class="sxs-lookup"><span data-stu-id="d0593-207">Your organization doesn't own the mailing list:</span></span>

  - <span data-ttu-id="d0593-208">请求邮件列表的维护人员为从中中继邮件列表的域配置电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0593-208">Ask the maintainer of the mailing list to configure email authentication for the domain that the mailing list is relaying from.</span></span>

    <span data-ttu-id="d0593-209">如果有足够多的发件人向域所有者反映他们应该设置电子邮件身份验证记录，这会促使他们采取行动。</span><span class="sxs-lookup"><span data-stu-id="d0593-209">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="d0593-210">虽然 Microsoft 也可与域所有者合作发布所需的记录，但当个人用户提出请求时，它可以提供更多帮助。</span><span class="sxs-lookup"><span data-stu-id="d0593-210">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

  - <span data-ttu-id="d0593-211">在电子邮件客户端中创建邮箱规则，以将邮件移动到收件箱。</span><span class="sxs-lookup"><span data-stu-id="d0593-211">Create inbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="d0593-212">此外，还可以要求管理员按照 [EOP 中的欺骗智能保护](learn-about-spoof-intelligence.md)和[管理租户允许/阻止列表](tenant-allow-block-list.md)部分的说明配置替代。</span><span class="sxs-lookup"><span data-stu-id="d0593-212">You can also ask your admins to configure overrides as described in [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) and [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

  - <span data-ttu-id="d0593-213">使用 Microsoft 365 创建支持票证，以便为邮件列表创建替代，以将其视为合法邮件。</span><span class="sxs-lookup"><span data-stu-id="d0593-213">Create a support ticket with Microsoft 365 to create an override for the mailing list to treat it as legitimate.</span></span> <span data-ttu-id="d0593-214">有关详细信息，请参阅[就商业版产品问题联系支持人员 - 管理员帮助](../../business-video/get-help-support.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-214">For more information, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="d0593-215">如果其他所有操作均失败，则可以向 Microsoft 报告该邮件为误报。</span><span class="sxs-lookup"><span data-stu-id="d0593-215">If all else fails, you can report the message as a false positive to Microsoft.</span></span> <span data-ttu-id="d0593-216">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="d0593-216">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="d0593-217">你也可以联系管理员，他可以将其作为支持票证向 Microsoft 提出。</span><span class="sxs-lookup"><span data-stu-id="d0593-217">You may also contact your admin who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="d0593-218">Microsoft 工程团队将调查邮件被标记为欺骗邮件的原因。</span><span class="sxs-lookup"><span data-stu-id="d0593-218">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

## <a name="considerations-for-anti-spoofing-protection"></a><span data-ttu-id="d0593-219">反欺骗防护注意事项</span><span class="sxs-lookup"><span data-stu-id="d0593-219">Considerations for anti-spoofing protection</span></span>

<span data-ttu-id="d0593-220">如果你是当前向 Microsoft 365 发送邮件的管理员，则需要确保你的电子邮件经过了正确的身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0593-220">If you're an admin who currently sends messages to Microsoft 365, you need to ensure that your email is properly authenticated.</span></span> <span data-ttu-id="d0593-221">否则，它可能被标记为垃圾邮件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="d0593-221">Otherwise, it might be marked as spam or phishing.</span></span> <span data-ttu-id="d0593-222">有关详细信息，请参阅[适用于发送未经身份验证的电子邮件的合法发件人的解决方案](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email)。</span><span class="sxs-lookup"><span data-stu-id="d0593-222">For more information, see [Solutions for legitimate senders who are sending unauthenticated email](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).</span></span>

<span data-ttu-id="d0593-223">单个用户（或管理员）“安全发件人”列表中的发件人将绕过部分筛选堆栈，包括欺骗防护。</span><span class="sxs-lookup"><span data-stu-id="d0593-223">Senders in an individual user's (or admin's) Safe Senders list will bypass parts of the filtering stack, including spoof protection.</span></span> <span data-ttu-id="d0593-224">有关详细信息，请参阅 [Outlook 安全发件人](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders)。</span><span class="sxs-lookup"><span data-stu-id="d0593-224">For more information, see [Outlook Safe Senders](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).</span></span>

<span data-ttu-id="d0593-225">管理员应避免（如果可能）使用允许的发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="d0593-225">Admins should avoid (when possible) using allowed sender lists or allowed domain lists.</span></span> <span data-ttu-id="d0593-226">这些发件人将绕过所有垃圾邮件、欺骗和网络钓鱼防护以及发件人身份验证（SPF、DKIM、DMARC）。</span><span class="sxs-lookup"><span data-stu-id="d0593-226">These senders bypass all spam, spoofing, and phishing protection, and also sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="d0593-227">有关详细信息，请参阅[使用允许的发件人列表或允许的域列表](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists)。</span><span class="sxs-lookup"><span data-stu-id="d0593-227">For more information, see [Use allowed sender lists or allowed domain lists](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).</span></span>
