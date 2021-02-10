---
title: EOP 如何验证"自"地址以防止钓鱼
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Outlook.com 接受或拒绝的电子邮件地址类型，以帮助防止网络钓鱼。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167511"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP 如何验证"自"地址以防止钓鱼

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

网络钓鱼攻击是任何电子邮件组织的一个持续威胁。 除了使用 [欺骗 (伪造) 电子邮件地址](anti-spoofing-protection.md)外，攻击者通常使用"发件人"地址中违反 Internet 标准的值。 为了帮助防止此类网络钓鱼，Exchange Online Protection (EOP) 和 Outlook.com 现在要求入站邮件包含与 RFC 兼容的"源"地址，如本文所述。 2017 年 11 月启用此强制。

**注意**：

- 如果您定期收到来自采用本文中所述的"发送地址"格式错误的组织的电子邮件，请鼓励这些组织更新其电子邮件服务器，以符合现代安全标准。

- "代表 (使用的发件人字段和邮件列表) 不受这些要求影响。 有关详细信息，请参阅以下博客文章：我们引用电子邮件的"发件人"时意味着什么[？。](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)

## <a name="an-overview-of-email-message-standards"></a>电子邮件标准概述

标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。 邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。 邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。 RFC [5321](https://tools.ietf.org/html/rfc5321)中描述了邮件信封，RFC [5322](https://tools.ietf.org/html/rfc5322)中描述了邮件头。 收件人永远不会看到实际的邮件信封，因为它由邮件传输进程生成，并且实际上并不是邮件的一部分。

- 地址 `5321.MailFrom` (**MAIL FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。 此电子邮件地址通常记录在邮件头的"返回路径"头字段中 (尽管发件人可以指定不同的"返回路径"电子邮件地址) 。 

- The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field， and is the sender's email address that is displayed in email clients. The From address is the focus of the requirements in this article.

"源"地址在若干 RFC (中详细定义，例如 RFC 5322 第 3.2.3、3.4 和 3.4.1 节和 [RFC 3696](https://tools.ietf.org/html/rfc3696)) 。 寻址和被视为有效或无效的寻址有很多不同。 为保持简单，我们建议采用以下格式和定义：

`From: "Display Name" <EmailAddress>`

- **显示名称**：描述电子邮件地址所有者的可选短语。

  - 我们建议您始终使用双引号显示名称 (") ，如下所示。 如果显示名称 _逗号，则必须_ 将每个 RFC 5322 的字符串用双引号括起来。
  - 如果"发送地址"显示名称，则 EmailAddress 值必须括在尖括号 (< >) 如下所示。
  - Microsoft 强烈建议你在电子邮件地址和显示名称之间插入空格。

- **EmailAddress**：电子邮件地址使用以下格式 `local-part@domain` ：

  - **local-part**： 一个标识与地址关联的邮箱的字符串。 此值在域中是唯一的。 通常，使用邮箱所有者的用户名或 GUID。
  - **域**：FQDN 的完全限定域名 (FQDN) 托管由电子邮件地址的本地部分标识的邮箱的电子邮件服务器的名称。

  这是 EmailAddress 值的一些额外注意事项：

  - 只有一个电子邮件地址。
  - 建议您不要用空格分隔尖括号。
  - 不要在电子邮件地址后添加其他文本。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有效和无效的 From 地址示例

以下"来源"电子邮件地址有效：

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (建议不要这样做，因为尖括号和电子邮件地址之间存在空格。) 

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (建议不要这样做，显示名称双引号括起来。) 

以下"来源"电子邮件地址无效：

- **No From address：** Some automated messages don't include a From address. 过去，当 Microsoft 365 或 Outlook.com收到没有"收件人"地址的邮件时，该服务添加了以下默认"自："地址，使邮件可交付：

  `From: <>`

  现在，不再接受地址为空的邮件。

- `From: Microsoft 365 sender@contoso.com` (显示名称，但电子邮件地址未括在尖括号中。) 

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (电子邮件地址后添加文本。) 

- `From: Sender, Example <sender.example@contoso.com>` (该显示名称包含逗号，但不括在双引号中。) 

- `From: "Microsoft 365 <sender@contoso.com>"` (整个值错误地用双引号括起来。) 

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (显示名称，但电子邮件地址未括在尖括号中。) 

- `From: Microsoft 365<sender@contoso.com>` (括号和左尖显示名称之间没有空格。) 

- `From: "Microsoft 365"<sender@contoso.com>` (双引号和左尖括号之间没有空格。) 

## <a name="suppress-auto-replies-to-your-custom-domain"></a>禁止自动答复自定义域

该值不能用于禁止 `From: <>` 自动答复。 相反，你需要为自定义域设置空 MX 记录。 自动答复 (响应) 自动答复，因为响应服务器没有可以发送邮件的已发布地址。

- 选择无法接收电子邮件的电子邮件域。 例如，如果你的主域contoso.com，你可能会选择noreply.contoso.com。

- 此域的空 MX 记录由单个时间段组成。

例如：

```text
noreply.contoso.com IN MX .
```

有关设置 MX 记录的信息，请参阅在任何 DNS 托管提供商为 [Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)创建 DNS 记录。

有关发布空 MX 的信息，请参阅[RFC 7505。](https://tools.ietf.org/html/rfc7505)

## <a name="override-from-address-enforcement"></a>替代从地址强制

若要绕过入站电子邮件的发件人地址要求，可以使用 IP 允许列表 (连接筛选) 或邮件流规则 (也称为传输规则) ，如 [Microsoft 365](create-safe-sender-lists-in-office-365.md)中的"创建安全发件人列表"中所述。

无法覆盖从 Microsoft 365 发送的出站电子邮件的"发送地址"要求。 此外，Outlook.com即使通过支持，也不允许进行任何类型的覆盖。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>在 Microsoft 365 中防止和防范威胁的其他方法

若要详细了解如何加强组织防御网络钓鱼、垃圾邮件、数据泄露和其他威胁，请参阅保护 [Microsoft 365](../../admin/security-and-compliance/secure-your-business-data.md)商业版计划的前 10 种方法。
