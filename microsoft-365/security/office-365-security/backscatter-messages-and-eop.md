---
title: 退信消息和 EOP
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
description: 退信邮件是发送到伪造的电子邮件地址的自动退回邮件。 退信 DNSBL 标识发送退信邮件（可能包含许多合法的电子邮件源）的服务器。 由于它不是垃圾邮件制造者列表，因此我们不会尝试从退信 DNSBL 中删除自己。
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599729"
---
# <a name="backscatter-messages-and-eop"></a>退信式垃圾邮件和 EOP

*退信邮件*是您收到的未发送邮件的未送达报告（也称为 "ndr" 或 "退回邮件"）。 垃圾邮件制造者伪造（欺骗）其邮件的发件人地址，通常使用真实电子邮件地址将可信度借给其邮件。 因此，当他们不能避免向不存在的收件人发送邮件（垃圾邮件是一项高容量操作）时，目标电子邮件服务器可能 dutifully 以 NDR 的形式发送到 "发件人：" 地址中的伪造发件人。

Exchange Online Protection （EOP）尽一切努力识别可疑源中的邮件并无提示地将其丢弃，而不生成 NDR。 但根据大量通过服务传输的电子邮件数量，EOP 可能会无意间发送退信邮件。

Backscatterer.org 维护负责发送退信邮件的电子邮件服务器的阻止列表（也称为 "DNS 阻止列表" 或 "DNSBL"），并且 EOP 服务器可能显示在此列表中。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是垃圾邮件制造者的列表（通过其自己的许可）。

> [!TIP]
> 根据退信或网站（`http://www.backscatterer.org/?target=usage`），他们建议使用其服务以安全模式（而不是拒绝模式）检查传入电子邮件（大型电子邮件服务几乎总是发送一些退信邮件）。
