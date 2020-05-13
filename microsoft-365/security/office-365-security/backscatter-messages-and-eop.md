---
title: EOP 中的退信
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
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解退信和 Microsoft Exchange Online Protection （EOP）
ms.openlocfilehash: e30fa27ac359ad28e042b2d4bd446d34a2e4f1e9
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209627"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信

*退信*是您收到的未发送邮件的未送达报告（也称为 "ndr" 或 "退回邮件"）。 垃圾邮件制造者伪造（欺骗）其邮件的发件人地址，通常使用真实电子邮件地址将可信度借给其邮件。 因此，当垃圾邮件制造者不可避免地向不存在的收件人发送邮件（垃圾邮件是高容量操作）时，目标电子邮件服务器实质上欺骗您将 NDR 中的未送达邮件返回到 "发件人：" 地址中的伪造的发件人。

在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online 保护（EOP）组织中具有邮箱的 Microsoft 365 组织中，EOP 将尽力标识和无提示地从可疑源中删除邮件，而不生成 NDR。 但是，根据大量通过服务传输的电子邮件，总是 EOP 会无意间发送退信的可能性。

Backscatterer.org 维护负责发送退信的电子邮件服务器的阻止列表（也称为 "DNS 阻止列表" 或 "DNSBL"），并且 EOP 服务器可能显示在此列表中。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是垃圾邮件制造者的列表（通过其自己的许可）。

> [!TIP]
> Backscatter.org 网站（ <http://www.backscatterer.org/?target=usage> ）建议使用其服务以安全模式（而不是拒绝模式）检查传入电子邮件（大型电子邮件服务几乎总是发送一些退信）。
