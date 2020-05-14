---
title: Microsoft 365 中的电子邮件身份验证
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 管理员可了解 Exchange Online Protection (EOP) 如何使用电子邮件身份验证（SPF、DKIM 和 DMARC）来帮助防止欺骗、网络钓鱼和垃圾邮件。
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209495"
---
# <a name="email-authentication-in-eop"></a>EOP 中的电子邮件身份验证

电子邮件身份验证（也称为电子邮件验证）是一组尝试阻止欺骗（来自伪造发件人的电子邮件）的标准。 无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 都按照标准来验证入站电子邮件：

- [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)

- [DKIM](support-for-validation-of-dkim-signed-messages.md)

- [DMARC](use-dmarc-to-validate-email.md)

电子邮件身份验证会验证发件人的电子邮件（例如，laura@contoso.com）是否合法，是否来自该电子邮件域的预期来源（例如，contoso.com。）

本主题的其余部分将说明这些技术的工作原理，以及 EOP 如何使用它们来检查入站电子邮件。

## <a name="use-email-authentication-to-help-prevent-spoofing"></a>使用电子邮件身份验证帮助防止欺骗

DMARC 通过检查邮件中的**发件人**地址（用户在电子邮件客户端中看到的发件人电子邮件地址）来防止欺骗。 目标电子邮件组织还可以验证该域已通过 SPF 或 DKIM 检查，这意味着域已通过身份验证，因此未被欺骗。 

但是，问题是 DNS 中用于电子邮件身份验证的 SPF、DKIM 和 DMARC 记录（统称为电子邮件身份验证策略）完全是可选的。 因此，具有强电子邮件身份验证策略的域（如 microsoft.com 和 skype.com）可以防止欺骗，而发布较弱电子邮件身份验证策略或根本没有策略的域则是欺骗活动攻击的主要目标。

截至 2018 年 3 月，在财富 500 强企业中，只有 9% 的域发布了强电子邮件身份验证策略。 其余 91% 的公司可能被攻击者欺骗。 除非已落实其他某种电子邮件筛选机制，否则这些域中的欺骗发件人发送的电子邮件可能会送达用户。

![财富 500 强企业的 DMARC 策略](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

未跻身财富 500 强的已发布强电子邮件身份验证策略的中小型公司所占比例较小，而对于北美和西欧以外的电子邮件域，发布强策略的比例仍较小。

这是一个大问题，因为企业可能不知道电子邮件身份验证的工作方式，但攻击者完全了解这一点并且会加以利用。 由于网络钓鱼是一个大问题，并且强电子邮件身份验证策略的采用范围有限，因此 Microsoft 将使用*隐式电子邮件身份验证*来检查入站电子邮件。

隐式电子邮件身份验证建立在对常规电子邮件身份验证策略的各种扩展之上。 这些扩展包括发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技巧。 除非包含其他表明其为合法邮件的信号，否则从未使用电子邮件身份验证策略的域发送的邮件将被标记为欺骗邮件。

若要查看 Microsoft 的一般声明，请参阅[网络钓鱼第 2 部分 - Microsoft 365 中的增强反欺骗功能](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。

## <a name="composite-authentication"></a>复合身份验证

虽然 SPF、DKIM 和 DMARC 本身都很有用，但如果邮件没有明确的身份验证记录，它们就无法传递充足的身份验证状态。 为此，Microsoft 开发了一种适用于隐式电子邮件身份验证的算法，将多个信号组合成一个称为_复合身份验证_（或简称为“compauth”）的单一值。 可以在邮件头的“**Authentication-Results**”标头中标记 compauth 值。

> Authentication-Results:<br/>&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\>

[Authentication-results 邮件头](anti-spam-message-headers.md#authentication-results-message-header)对这些值进行了说明。

通过检查邮件头，管理员（或甚至是最终用户）可以确定 Microsoft 365 如何确定发件人是否是冒充的。

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>电子邮件身份验证为何并非总能阻止欺骗

仅依靠电子邮件身份验证记录来确定传入邮件是否是欺骗邮件具有以下限制：

- 发送域可能缺少所需的 DNS 记录，或者记录配置错误。

- 源域已正确配置 DNS 记录，但该域与“发件人”地址中的域不匹配。 SPF 和 DKIM 不需要在“发件人”地址中使用该域。 攻击者或合法服务部门可以注册一个域，为该域配置 SPF 和 DKIM，在“发件人”地址中使用一个完全不同的域，该邮件将通过 SPF 和 DKIM 验证。

复合身份验证可以让这些邮件通过检查（否则它们将无法通过电子邮件验证检查）来解决这些限制。

> [!NOTE]
> 正如前文所述，隐式电子邮件身份验证使用多个信号来确定邮件是否是合法邮件。 为简单起见，以下示例专注于电子邮件身份验证结果。 其他后端智能因素可以识别通过电子邮件身份验证的欺骗邮件，或未通过电子邮件身份验证的合法邮件。

例如，fabrikam.com 域没有 SPF、DKIM 或 DMARC 记录。 来自 fabrikam.com 域中的发件人的邮件可能无法通过复合身份验证（请注意 `compauth` 的值和理由）：

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

如果 fabrikam.com 配置了 SPF，但没有 DKIM 记录，邮件可通过复合身份验证，因为通过 SPF 验证的域与“发件人地址”中的域一致：

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

如果 fabrikam.com 配置了 SPF，但没有 DKIM 记录，邮件可通过复合身份验证，因为通过 SPF 验证的域与“发件人”地址中的域一致：

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

如果 SPF 中的域或 DKIM 签名与“发件人”地址中的域不一致，则该邮件可能无法通过复合身份验证：

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a>适用于发送未经身份验证的电子邮件的合法发件人的解决方案

Microsoft 365 跟踪谁在向你的组织发送未经身份验证的电子邮件。 如果服务部门认为该发件人不合法，则会将其标记为复合身份验证失败。 要避免这种情况，可使用本小节中的建议。

### <a name="configure-email-authentication-for-domains-you-own"></a>为你自己的域配置电子邮件身份验证

如果你拥有多个租户或与多个租户进行交互，则可使用此方法解决组织内欺骗和跨域欺骗。 它还有助于解决跨域欺骗，即你发送给 Microsoft 365 中的其他客户或由其他提供程序托管的第三方。

- [配置域的 SPF 记录](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

- [为主域配置 DKIM 记录](use-dkim-to-validate-outbound-email.md)。

- [考虑为你的域设置 DMARC 记录](use-dmarc-to-validate-email.md)，以确定合法发件人。

Microsoft 不提供针对 SPF、DKIM 和 DMARC 记录的详细实施指南。 但是，线上提供了很多信息。 此外，还有第三方公司致力于帮助你的组织设置电子邮件身份验证记录。

#### <a name="you-dont-know-all-sources-for-your-email"></a>你不知道电子邮件的所有来源

许多域不会发布 SPF 记录，因为它们不知道域中邮件的所有电子邮件来源。 首先发布一个 SPF 记录，其中包含你所知道的所有电子邮件来源（尤其是公司流量所在的位置），然后发布中性 SPF 策略 `?all`。 例如：

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

此示例意味着，来自公司基础结构的电子邮件将通过电子邮件身份验证，但来自未知来源的电子邮件将回退为中性。

Microsoft 365 会将来自你的企业基础结构的入站电子邮件视为已通过身份验证，但来自未识别来源的电子邮件可能仍被标记为欺骗（具体取决于 Microsoft 365 能否对它进行隐式身份验证）。 不过，这对于所有电子邮件都被 Microsoft 365 标记为欺骗邮件来说，仍是一项改进。

开始使用 `?all` 的 SPF 回退策略后，你可以逐步你的邮件发现和包含更多电子邮件来源，然后使用更严格的策略更新 SPF 记录。

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a>使用反欺骗智能保护配置允许发送未经身份验证的电子邮件的人员

你也可以使用[反欺骗智能保护](learn-about-spoof-intelligence.md)允许发件人将未经身份验证的邮件传送到你的组织。

对于外部域，欺骗用户是“发件人”地址中的域，而发送基础结构是源 IP 地址（分为 /24 个 CIDR 区域），或者是反向 DNS (PTR) 记录的组织域。

在下面的屏幕截图中，源 IP 可能是 131.107.18.4，PTR 记录为 outbound.mail.protection.outlook.com。 对于发送基础结构，这将显示为 outlook.com。

若要允许此发件人发送未经身份验证的电子邮件，请将“**否**”更改为“**是**”。

![设置反欺骗允许的发件人](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a>为发件人/收件人对创建允许条目

若要绕过垃圾邮件筛选、网络钓鱼筛选的某些部分，但不绕过针对特定发件人的恶意软件筛选，请参阅 [在 Microsoft 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a>要求发件人为不归你所有的域配置电子邮件身份验证

由于存在垃圾邮件和网络钓鱼问题，Microsoft 建议对所有电子邮件组织进行电子邮件身份验证。 无需在组织中配置手动替代，可让发送域中的管理员配置其电子邮件身份验证记录。

- 即使用户过去不需要发布电子邮件身份验证记录，也应在将电子邮件发送到 Microsoft 时执行此操作。

- 设置 SPF 以发布域的发送 IP 地址，并设置 DKIM（如果可用）以对邮件进行数字签名。 他们还可以考虑设置 DMARC 记录。

- 如果他们使用批量发件人代表他们发送电子邮件，请验证“发件人”地址（如果该地址属于他们）中的域是否与通过 SPF 或 DMARC 检查的域一致。

- 验证 SPF 记录中是否包括以下位置（如果他们使用了这些地址）：
  
  - 本地电子邮件服务器。
  - 通过软件即服务 (SaaS) 提供程序发送的电子邮件。
  - 通过云托管服务（Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 等）发送的电子邮件。

- 对于由 ISP 托管的小型域，请根据 ISP 提供的说明配置 SPF 记录。

虽然刚开始可能很难让发送域进行身份验证，但随着时间的推移，随着越来越多的电子邮件筛选器开始放弃甚至拒绝他们的电子邮件，这将使他们设置正确的记录以确保更好地交付。 此外，他们的参与有助于防止网络钓鱼，并且可以减少将电子邮件发送到的目标组织中出现欺骗的可能性。

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a>有关基础结构提供商（ISP、ESP 或云托管服务）的信息

如果你负责托管域的电子邮件或提供可以发送电子邮件的托管基础结构，则应执行以下操作：

- 确保你的客户拥有说明应如何配置其 SPF 记录的文档

- 考虑在出站电子邮件上进行 DKIM 签名，即使客户未明确设置它（使用默认域签名）。 你甚至可以使用 DKIM 签名对电子邮件进行双重签名（第一次使用客户的域进行签名（如果已设置该域），第二次使用你公司的 DKIM 签名）

即使你对来自平台的电子邮件进行身份验证，也无法保证向 Microsoft 的邮件传递，但至少可确保 Microsoft 不会因为未经过身份验证而将你的电子邮件标记为垃圾邮件。

有关服务提供商最佳实践的更多详细信息，请参阅[服务提供商的 M3AAWG 移动消息传递最佳实践](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。
