---
title: 使用 DMARC 验证电子邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: 了解如何配置基于域的邮件身份验证、报告和一致性 (DMARC) 以验证从你的组织发送的邮件。
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016316"
---
# <a name="use-dmarc-to-validate-email"></a>使用 DMARC 验证电子邮件

基于域的邮件身份验证、报告和一致性 ([DMARC](https://dmarc.org)) 与发件人策略框架 (SPF) 和域密钥识别邮件 (DKIM) 结合使用，以验证邮件发件人并确保目标电子邮件系统信任从你的域发送的邮件。 实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。 DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。

> [!TIP]
> 请访问 [Microsoft 智能安全协会 (MISA)](https://www.microsoft.com/misapartnercatalog) 目录，查看哪些第三方供应商提供 Microsoft 365 的 DMARC 报告。

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>SPF 和 DMARC 如何协同工作来保护 Microsoft 365 中的电子邮件？

 电子邮件可能包含多个发送方、发件人或地址。 这些地址用于不同用途。 例如，以下列地址为例：

- **“邮件发件人”地址**：标识发件人，并指定在传送邮件过程中出现任何问题（例如未送达通知）时发送返回通知的地址。 该地址出现在电子邮件的信封部分，而电子邮件应用程序通常不显示此地址。 有时称其为" 5321.MailFrom 地址"或"反向路径地址"。

- **“发件人”地址**：由邮件应用程序显示为发件人地址的地址。 此地址标识电子邮件的作者。 即，负责撰写邮件的个人或系统的邮箱。 有时也称其为"5322.From 地址"。

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

在此脚本中，发件人地址如下所示：

- 邮件发件人地址 (5321.MailFrom)：phish@phishing.contoso.com

- 发件人地址 (5322.From)：security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>什么是 DMARC TXT 记录？

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Microsoft 的 DMARC TXT 记录如下所示：

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft 将其 DMARC 报告发送至 [Agari](https://agari.com)（第三方）。 Agari 收集并分析 DMARC 报告。 请访问 [MISA 目录](https://www.microsoft.com/misapartnercatalog)，查看有哪些更多的第三方供应商提供 Microsoft 365 的 DMARC 报告。

## <a name="implement-dmarc-for-inbound-mail"></a>为入站邮件实现 DMARC

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>从 Microsoft 365 中为出站邮件实现 DMARC

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [步骤 1：为域标识邮件的有效源](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [步骤 2：为域设置 SPF](#step-2-set-up-spf-for-your-domain)

- [步骤3：为自定义域设置 DKIM](#step-3-set-up-dkim-for-your-custom-domain)

- [步骤 4：为域生成 DMARC TXT 记录](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>步骤 1：为域标识邮件的有效源

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- 哪些 IP 地址从我的域发送邮件？

- 对于第三方代表我发送的邮件，5321.MailFrom 和 5322.From 域会匹配吗？

### <a name="step-2-set-up-spf-for-your-domain"></a>步骤 2：为域设置 SPF

既然你拥有了所有的有效发件人的列表，你可以按照步骤[设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

例如，假定 contoso.com 从 Exchange Online 中发送邮件，本地 Exchange 服务器的 IP 地址是 192.168.0.1，并且 Web 应用程序的 IP 地址是 192.168.100.100，则 SPF TXT 记录将如下所示：

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

作为最佳做法，请确保 SPF TXT 记录考虑第三方发件人。

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>步骤 3：为自定义域设置 DKIM

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

有关为域设置 DKIM 的说明，包括如何为第三方发件人设置 DKIM，以便他们可以欺骗你的域，请参阅[使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>步骤 4：为域生成 DMARC TXT 记录

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

其中：

- *域*是你想要保护的域。 默认情况下，该记录可保护从该域和所有子域发送的邮件。 例如，如果指定 \_dmarc.contoso.com，那么 DMARC 会保护从该域和所有子域（例如 housewares.contoso.com 或 plumbing.contoso.com）发送的邮件。

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- pct=100** 表示此规则应该用于所有的电子邮件。

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

有关要使用的选项的信息，请熟悉[在 Microsoft 365 中实现 DMARC 的最佳做法](#best-practices-for-implementing-dmarc-in-microsoft-365)中的概念。

示例：

- 策略设置为无

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- 策略设置为隔离

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- 策略设置为拒绝

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>在 Microsoft 365 中实现 DMARC 的最佳做法

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. 监视实现 DMARC 的影响

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. 请求外部邮件系统隔离未通过 DMARC 的邮件

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. 请求外部邮件系统不接受未通过 DMARC 的邮件

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Microsoft 365 如何处理未通过 DMARC 的出站电子邮件

如果邮件是从 Microsoft 365 出站的而且未通过 DMARC，并且你已将策略设置为 p=quarantine 或 p=reject，则该邮件通过[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)进行路由。 出站电子邮件不存在任何替代方法。

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Microsoft 365 如何处理未通过 DMARC 的入站电子邮件

如果发送服务器的 DMARC 策略是 `p=reject`，则 EOP 会将该邮件标记为欺骗，而不是拒绝它。 换句话说，对于入站电子邮件，Microsoft 365 将 `p=reject` 和 `p=quarantine` 视为相同方式。 管理员可以定义对[反网络钓鱼策略](set-up-anti-phishing-policies.md)中分类为欺骗的邮件执行的操作。

之所以像这样配置 Microsoft 365，是因为某些合法的电子邮件可能会无法通过 DMARC。 例如，如果将邮件发送到一个邮件列表，然后将其中继到所有列表参与者，则该邮件可能无法通过 DMARC。 如果 Microsoft 365 拒绝这些邮件，人们可能会丢失合法的电子邮件，而且无法进行检索。 相反，这些邮件仍然无法通过 DMARC，但会将其标记为垃圾邮件而不是拒绝。 如果需要，用户仍可以在其收件箱中获得这些邮件，方法如下：

- 用户使用其电子邮件客户端分别添加安全发件人。

- 管理员可更新[欺骗智能](learn-about-spoof-intelligence.md)报告，以允许欺骗邮件。

- 管理员创建一个适用于所有用户的 Exchange 邮件流规则（也称为传输规则），允许那些特定发件人的邮件。

有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Microsoft 365 如何使用经过身份验证的接收链 (ARC)

Microsoft 365 中的所有托管邮箱都将获得 ARC 的优势，实现改进的邮件可传递性和增强的反欺骗保护。 当电子邮件从始发服务器路由到收件人邮箱时，ARC 将保留来自所有参与中介或跃点的电子邮件身份验证结果。 在采用 ARC 之前，电子邮件路由中的中介执行的修改（如转发规则或自动签名）可能会在电子邮件到达收件人邮箱时导致 DMARC 故障。 有了 ARC 之后，身份验证结果的加密保留使得 Microsoft 365 能够验证电子邮件发件人的真伪。

目前，当 Microsoft 是 ARC 保护方时，Microsoft 365 会利用 ARC 来验证身份验证结果，但计划在将来添加对第三方 ARC 保护方的支持。

## <a name="troubleshooting-your-dmarc-implementation"></a>DMARC 实现疑难解答

如果你已配置了域的 MX 记录，其中 EOP 不是第一项，将不会为你的域强制执行 DMARC 失败。

如果你是 客户，并且你的域的主 MX 记录不指向 EOP，你将不会获得 DMARC 的好处。 例如，如果你将 MX 记录指向你的本地邮件服务器，然后使用连接器将电子邮件路由到 EOP，则 DMARC 将不起作用。 在这种情况下，接收域是一个接受的域，但 EOP 不是主 MX。 例如，假设 contoso.com 本身指向其 MX 并将 EOP 用作辅助 MX 记录，contoso.com 的 MX 记录将如下所示：

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

由于它是主 MX，全部或大部分电子邮件将首先被路由到 mail.contoso.com，然后将邮件路由到 EOP。 在某些情况下，你甚至不可能将 EOP 列为 MX 记录，并直接挂接连接器来路由你的电子邮件。 EOP 不必是执行 DMARC 验证的第一个条目。 它只是确保验证，因为我们不能确定所有本地/非 O365 服务器都将执行 DMARC 检查。  设置 DMARC TXT 记录时，可以对客户的域（而不是服务器）强制执行 DMARC，但是实际上强制执行取决于接收服务器。  如果将 EOP 设置为接收服务器，那么 EOP 强制执行 DMARC。

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC 的疑难解答图形，由 Daniel Mande 提供":::

## <a name="for-more-information"></a>详细信息

Want more information about DMARC? These resources can help.

- [反垃圾邮件邮件头](anti-spam-message-headers.md) 包括 Microsoft 365 执行 DMARC 检查时使用的语法和标头字段。

- 参加 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG（消息、恶意软件、移动反滥用工作组）提供的 <sup>DMARC 培训系列</sup>。

- 使用检查表，位于 [dmarcian](https://space.dmarcian.com/deployment/)。

- 直接访问源，位于 [DMARC.org](https://dmarc.org)。

## <a name="see-also"></a>另请参阅

[Microsoft 365 如何使用发件人策略框架 (SPF) 来防止欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)

[在 Microsoft 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[使用 DKIM 在 Microsoft 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)
