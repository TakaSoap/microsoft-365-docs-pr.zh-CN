---
title: 退信和 EOP
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
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: 退信是发送到伪造的电子邮件地址的自动退回邮件。 退信 DNSBL 标识发送退信邮件（可能包含许多合法的电子邮件源）的服务器。 由于它不是垃圾邮件制造者列表，因此我们不会尝试从退信 DNSBL 中删除自己。
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895401"
---
# <a name="backscatter-and-eop"></a>退信和 EOP

*退信*是您收到的未发送邮件的未送达报告（也称为 "ndr" 或 "退回邮件"）。 垃圾邮件制造者伪造（欺骗）其邮件的发件人地址，通常使用真实电子邮件地址将可信度借给其邮件。 因此，当垃圾邮件制造者不可避免地向不存在的收件人发送邮件（垃圾邮件是高容量操作）时，目标电子邮件服务器实质上欺骗您将 NDR 中的未送达邮件返回到 "发件人：" 地址中的伪造的发件人。

Exchange Online Protection （EOP）尽一切努力识别可疑源中的邮件并无提示地将其丢弃，而不生成 NDR。 但是，根据大量通过服务传输的电子邮件，总是 EOP 会无意间发送退信的可能性。

Backscatterer.org 维护负责发送退信的电子邮件服务器的阻止列表（也称为 "DNS 阻止列表" 或 "DNSBL"），并且 EOP 服务器可能显示在此列表中。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是垃圾邮件制造者的列表（通过其自己的许可）。

> [!TIP]
> Backscatter.org 网站（<http://www.backscatterer.org/?target=usage>）建议使用其服务以安全模式（而不是拒绝模式）检查传入电子邮件（大型电子邮件服务几乎总是发送一些退信）。
