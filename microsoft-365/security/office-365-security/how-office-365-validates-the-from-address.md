---
title: Office 365 如何通过验证发件人地址来防止钓鱼
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Lear：关于来自 Office 365 中的入站邮件的电子邮件地址的要求。 截至2017年11月，服务现在需要符合 RFC 规范的地址，以帮助防止欺骗。
ms.openlocfilehash: 4df073cfff3c36f60a013237d95548cb48fa7b5f
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528997"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 如何通过验证发件人地址来防止钓鱼

Office 365 电子邮件帐户会收到越来越多的网络钓鱼攻击。 除了使用[欺骗（伪造）发件人电子邮件地址](anti-spoofing-protection.md)之外，攻击者通常使用来自冲突 internet 标准的发件人地址中的值。 为了帮助阻止这种类型的网络钓鱼，Office 365 和 Outlook.com 现在要求入站邮件包含符合 RFC 标准的发件人地址，如本主题中所述。 此强制已于2017年11月启用。

**注意**：

- 如果您定期收到来自地址格式不正确（如本主题所述）的组织发来的电子邮件，则鼓励这些组织更新其电子邮件服务器以遵守新式安全标准。

- "相关发件人" 字段（由 "代表发送" 和 "邮寄列表" 使用）不受这些要求的影响。 有关详细信息，请参阅以下博客文章：[当我们引用电子邮件的 "发件人" 时，我们意味着什么？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)。

## <a name="an-overview-of-email-message-standards"></a>电子邮件标准概述

标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。 [Rfc 5321](https://tools.ietf.org/html/rfc5321)中介绍了邮件信封，并且[rfc 5322](https://tools.ietf.org/html/rfc5322)中介绍了邮件头。 收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，并且实际上并不是邮件的一部分。

- `5321.MailFrom`地址（也称为 "**发**件人地址"、"P1 发件人" 或 "信封发件人"）是在邮件的 SMTP 传输中使用的电子邮件地址。 此电子邮件地址通常记录在邮件标头中的 "**返回路径**标头" 字段中（尽管发件人可以指定不同的**返回路径**电子邮件地址）。

- `5322.From` （也称为 "来自地址" 或 "P2 发件人"）是 "**发**件人" 头字段中的电子邮件地址，是电子邮件客户端中显示的发件人的电子邮件地址。 "发件人" 地址是本主题中要求的重点。

"发件人" 地址在多个 Rfc 中进行了详细定义（例如，RFC 5322 节3.2.3、3.4 和3.4.1，以及[rfc 3696](https://tools.ietf.org/html/rfc3696)）。 寻址方面有很多变化，被视为有效或无效。 为简单起见，我们建议采用以下格式和定义：

`From: "Display Name" <EmailAddress>`

- **显示名称**：描述电子邮件地址所有者的可选短语。

  - 我们建议您始终将显示名称括在双引号（"）中，如下所示。 如果显示名称包含逗号，则_必须_将字符串括在每个 RFC 5322 的双引号中。
  - 如果 "发件人" 地址包含显示名称，则 EmailAddress 值必须括在尖括号（< >）中，如图所示。
  - Microsoft 强烈建议您在显示名称和电子邮件地址之间插入空格。

- **EmailAddress**：电子邮件地址使用以下格式`local-part@domain`：

  - **本地-部分**：标识与地址关联的邮箱的字符串。 此值在域中是唯一的。 通常，使用邮箱所有者的用户名或 GUID。
  - **domain**：电子邮件服务器的完全限定域名（FQDN），该域名托管由电子邮件地址的本地部分标识的邮箱。

  以下是 EmailAddress 值的一些额外注意事项：

  - 仅有一个电子邮件地址。
  - 建议不要用空格分隔尖括号。
  - 不要在电子邮件地址后面添加其他文本。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有效和无效发件人地址的示例

以下发件人的电子邮件地址是有效的：

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >`（不建议这样做，因为尖括号和电子邮件地址之间有空格。）

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Office 365" <sender@contoso.com>`

- `From: Office 365 <sender@contoso.com>`（不建议这样做，因为显示名称没有括在双引号内。）

以下发件人的电子邮件地址无效：

- **发件人地址不**是：某些自动邮件不包含发件人地址。 过去，当 Office 365 或 Outlook.com 收到不含发件人地址的邮件时，该服务会添加以下默认发件人： address，以使邮件可交付：

  `From: <>`

  现在，"发件人" 地址为空的邮件将不再被接受。

- `From: Office 365 sender@contoso.com`（显示名称存在，但电子邮件地址不是括在尖括号中。）

- `From: "Office 365" <sender@contoso.com> (Sent by a process)`（电子邮件地址后的文本。）

- `From: Sender, Example <sender.example@contoso.com>`（显示名称包含逗号，但未括在双引号内。）

- `From: "Office 365 <sender@contoso.com>"`（整数值不正确地括在双引号中。）

- `From: "Office 365 <sender@contoso.com>" sender@contoso.com`（显示名称存在，但电子邮件地址不是括在尖括号中。）

- `From: Office 365<sender@contoso.com>`（显示名称和左尖括号之间没有空格。）

- `From: "Office 365"<sender@contoso.com>`（右双引号和左尖括号之间没有空格。）

## <a name="suppress-auto-replies-to-your-custom-domain"></a>禁止对自定义域的自动答复

不能使用值`From: <>`来禁止显示自动答复。 相反，您需要为您的自定义域设置空的 MX 记录。 自动答复（和所有答复）将自然被隐含，因为响应服务器不会向其发送邮件的发布地址。

- 选择无法接收电子邮件的电子邮件域。 例如，如果您的主域是 contoso.com，则可以选择 noreply.contoso.com。

- 此域的 null MX 记录由一个句点组成。

例如：

```text
noreply.contoso.com IN MX .
```

有关设置 MX 记录的详细信息，请参阅[在任何 DNS 托管提供商处创建适用于 Office 365 的 dns 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

有关发布空 MX 的详细信息，请参阅[RFC 7505](https://tools.ietf.org/html/rfc7505)。

## <a name="override-from-address-enforcement"></a>从地址强制中覆盖

若要绕过入站电子邮件的发件人地址要求，可以使用 IP 允许列表（连接筛选）或邮件流规则（也称为传输规则），如在[Office 365 中创建安全发件人列表中](create-safe-sender-lists-in-office-365.md)所述。

您不能覆盖从 Office 365 发送出的出站电子邮件的发件人地址要求。 此外，Outlook.com 不允许覆盖任何种类，即使支持也是如此。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>阻止和防止 cybercrimes 在 Office 365 中的其他方法

有关如何加强组织抵御网络钓鱼、垃圾邮件、数据泄露和其他威胁的详细信息，请参阅[保护 Office 365 和 Microsoft 365 商业版计划](../../admin/security-and-compliance/secure-your-business-data.md)的十大方法。
