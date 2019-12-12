---
title: 管理邮件群发程序的白名单
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970298"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>管理邮件群发程序的安全发件人列表

如果要使用安全发件人列表，则应知道 Exchange Online Protection （EOP）和 Outlook 处理的处理方式不同。 Office 365 服务通过检查`RFC 5321.MailFrom`地址和`RFC 5322.From`地址来尊重安全发件人和域，而 Outlook 将`RFC 5322.From`地址添加到用户的安全发件人列表中。 （注意：该服务将检查阻止`5321.MailFrom`的发`5322.From`件人和域的地址和地址。）

`SMTP MAIL FROM`地址（也称为`RFC 5321.MailFrom address`）是用于执行 SPF 检查的电子邮件地址，如果无法传递邮件，则会将退回邮件传递到的路径。 默认情况下，这是`Return-Path`在邮件头中放置的此电子邮件地址，但发件人可以指定不同`Return-Path`的地址。

邮件`From:`头中的地址（也称为`RFC 5322.From`地址）是显示在邮件客户端（如 Outlook）中的电子邮件地址。

大部分时间、 `5321.MailFrom`和`5322.From`地址相同。 这是典型的个人到个人的通信。 但是，当代表其他人发送电子邮件时，地址往往是不同。 通常这对于批量电子邮件是经常发生的。

例如，假设蓝色 Yonder 航空公司已雇用玛吉的旅行，发出电子邮件广告。 然后，您会在收件箱中收到一封来自发件人 blueyonder@news.blueyonderairlines.com 的邮件。 在此示例中：

- `5321.MailFrom`地址为 blueyonder.airlines@margiestravel.com。

- `5322.From`地址为 blueyonder@news.blueyonderairlines.com，这就是您在 Outlook 中看到的内容。

若要阻止筛选此邮件，您可以执行以下操作：

- **作为用户**：在 Outlook 中`RFC 5322.From`将地址添加为安全发件人。

- **作为管理员**：设置[邮件流规则](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)（也称为传输规则）。
