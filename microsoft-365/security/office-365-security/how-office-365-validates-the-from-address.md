---
title: EOP 如何通过验证发件人地址来防止钓鱼
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection (EOP 功能接收或拒绝的电子邮件地址) ，以及Outlook.com防止网络钓鱼。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c67cf5855f2b0a99cf8d03bb6d7ba8557329b300
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827417"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP 如何通过验证发件人地址来防止钓鱼

网络钓鱼攻击是对任何电子邮件组织的持续威胁。 除了在发件人 [电子邮件地址 (伪) 外，](anti-spoofing-protection.md)攻击者通常会使用违反 Internet 标准的发件人地址中的值。 为了帮助防止此类网络钓鱼，Exchange Online Protection (EOP) 和Outlook.com现在要求入站邮件包括符合 RFC 的"发件人"地址，如本主题中所述。 2017 年 11 月已启用此强制执行。

**注意**：

- 如果经常接收来自已使用本主题中描述的地址正确的组织发送的电子邮件，请鼓励这些组织更新其电子邮件服务器，以符合新式安全标准。

- 由"代表发送 (发件人"和"发送"列表) 不受这些要求的影响。 有关详细信息，请参阅以下博客文章：[如果我们引用电子邮件的"发件人"，我们的意思是什么？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)

## <a name="an-overview-of-email-message-standards"></a>电子邮件标准概述

标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。 [RFC 5321 中介绍了邮件信封，RFC 5322](https://tools.ietf.org/html/rfc5321)中[介绍了邮件头](https://tools.ietf.org/html/rfc5322)。 收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，实际上并不是邮件的一部分。

- 地址 `5321.MailFrom` (也称为 **"MAIL FROM** 地址、P1 发件人"或"信封发件人) "的电子邮件地址是邮件 SMTP 传输中使用的电子邮件地址。 通常，此电子邮件地址记录在邮件头 (中的 **"返回** 路径"标头字段中，尽管发件人可以指定不同的 **返回** 路径电子邮件地址) 。

- 该 `5322.From` (也称为发件人地址或 P2 发件人) 是 **"发件人"** 标头字段中的电子邮件地址，也是电子邮件客户端中显示的发件人电子邮件地址。 "发件人"地址是本主题中的要求的重点。

"发件人"地址在多个 RFC (例如，RFC 5322 部分 3.2.3、3.4 和 3.4.1 和 [RFC 3696](https://tools.ietf.org/html/rfc3696) 一节中进行了详细) 。 寻址有很多变化，以及视为有效或无效内容的因素。 建议简单起来，建议使用以下格式和定义：

`From: "Display Name" <EmailAddress>`

- **显示**名称：描述电子邮件地址所有者的可选短语。

  - 建议您始终将要显示名称双引号引起来 (") 如下所示。 如果名称显示名称包含逗号，则必须 _用_ RFC 5322 的双引号将该字符串括起来。
  - 如果发件人地址中包含的 显示名称，则 EmailAddress 值必须括在 < > (以) 中，如下所示。
  - Microsoft 强烈建议您在电子邮件地址的 显示名称之间的空格。

- **EmailAddress**： 电子邮件地址使用以下格式 `local-part@domain` ：

  - **local-part：** 标识与地址关联的邮箱的字符串。 此值在域中是唯一的。 通常使用邮箱所有者的用户名或 GUID。
  - **domain：** 托管由电子邮件地址 (部分标识的邮箱的电子邮件服务器的) 完全限定域名域名。

  下面是 EmailAddress 值的其他一些注意事项：

  - 仅一个电子邮件地址。
  - 建议不要将角括号与空格分隔开。
  - 不要在电子邮件地址后包含其他文本。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有效的"收件人地址"和"无效"地址的示例

以下发件人电子邮件地址有效：

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (个直括号和电子邮件地址之间存在空格，是不推荐的) 

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (个字符，因为显示名称不用双引号.) 中括起来

以下"发件人"电子邮件地址无效：

- **无发件人地址**：某些自动邮件不包括发件人地址。 在过去，当 Microsoft 365 或 Outlook.com收到不含"发件人"地址的邮件时，该服务添加了以下默认发件人：地址以使邮件可传递：

  `From: <>`

  现在不再接受具有空白发件人地址的邮件。

- `From: Microsoft 365 sender@contoso.com` (该显示名称，但电子邮件地址未括在 angle brackets.) 

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (电子邮件地址之后插入文本) 

- `From: Sender, Example <sender.example@contoso.com>` (用户显示名称包含一个逗号，但不用双引号将该文本括起 ) 来

- `From: "Microsoft 365 <sender@contoso.com>"` (使用双引号.) 

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (该显示名称，但电子邮件地址未括在 angle brackets.) 

- `From: Microsoft 365<sender@contoso.com>` (右的 显示名称 bracket.) 之间不) 

- `From: "Microsoft 365"<sender@contoso.com>` (左双引号和左角括号之间没有空格) 

## <a name="suppress-auto-replies-to-your-custom-domain"></a>禁止自动答复你的自定义域

不能使用该值 `From: <>` 来禁止自动答复。 而需要为自定义域设置一个空的 MX 记录。 自动答 (以及所有答复都不会) 自然抑制，因为响应服务器无法将消息发送到任何已发布地址。

- 选择无法接收电子邮件的电子邮件域。 例如，如果您的是主域contoso.com，您可以选择noreply.contoso.com。

- 此域的 Null MX 记录由单个时间点完成。

例如：

```text
noreply.contoso.com IN MX .
```

有关设置 MX 记录的详细信息，请参阅任何 [DNS 托管提供商处的 Microsoft 365 创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

有关发布 null MX 的详细信息，请参阅[RFC 7505。](https://tools.ietf.org/html/rfc7505)

## <a name="override-from-address-enforcement"></a>替代地址强制

要绕过入站电子邮件的"发件人地址"要求，可以使用 IP 允许列表 (连接筛选) 或邮件流规则 (又称为传输规则) 如 Microsoft [365](create-safe-sender-lists-in-office-365.md)中创建安全发件人列表所述。

不能替代从 Microsoft 365 发送的出站电子邮件的发件人地址要求。 此外，Outlook.com允许通过支持覆盖任何类型。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>防止和防范 Microsoft 365 网络设备的其他方法

有关如何保护组织免受网络钓鱼、垃圾邮件、数据泄露和其他威胁的更多信息，请参阅 [最常见的方法来保护 Microsoft 365 商业版计划](../../admin/security-and-compliance/secure-your-business-data.md)。
