---
title: EOP 中的退信式垃圾邮件
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
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '在本文中，您将了解退信和 Microsoft Exchange Online Protection (EOP) '
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203583"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*退信* 是未送达报告 (也称为 "ndr" 或 "退回邮件") 您收到的邮件未发送。 垃圾邮件制造者伪造 (欺骗) 的发件人地址，它们通常使用真实的电子邮件地址对其邮件的可信度。 因此，垃圾邮件制造者不可避免地向不存在的收件人发送邮件时 (垃圾邮件是高容量操作) ，目标电子邮件服务器实质上欺骗将 NDR 中的未送达邮件返回到 "发件人：" 地址中的伪造发件人。

在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，EOP 将尽力标识和无提示地从可疑源中删除邮件，而不生成 NDR。 但是，根据大量通过服务传输的电子邮件，总是 EOP 会无意间发送退信的可能性。

Backscatterer.org 维护一个阻止列表 (也称为 "DNS 阻止列表" 或负责发送退信的电子邮件服务器的 DNSBL) ，并且 EOP 服务器可能显示在此列表中。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是由其自己的许可)  (的垃圾邮件制造者列表。

> [!TIP]
> Backscatter.org 网站 (<http://www.backscatterer.org/?target=usage>) 建议使用其服务以安全模式而不是拒绝模式检查传入电子邮件 (大型电子邮件服务几乎总是发送一些退信) 。
