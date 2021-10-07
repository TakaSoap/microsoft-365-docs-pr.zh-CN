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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '本文将介绍 EOP 服务中的退Microsoft Exchange Online (和) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 79a6dd1be6c33bdbfc3d87b834f231de7cd08a0c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199449"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*退信* 式垃圾邮件是未 (未发送) 发送的邮件的未送达报告，也称为"未送达报告"或退回邮件。 退信是由垃圾邮件制造者 (欺骗) 发件人 (也称为"或 P2 地址) `5322.From` 邮件中。 垃圾邮件制造者通常使用真实电子邮件地址作为发件人地址，以向邮件提供信誉。 将垃圾邮件发送到不存在的收件人时，目标电子邮件服务器实质上被欺骗，在 NDR 中将未送达的邮件返回给发件人地址中的伪造发件人。

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 会尽一切努力从可疑源中标识并静默地删除邮件，而不生成 NDR。 但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。

Backscatterer.org 阻止列表 (DNS 阻止列表或 DNSBL) 负责发送退信的电子邮件服务器，EOP 服务器可能显示在此列表上。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己， (允许) 列表不是垃圾邮件制造者列表。

> [!TIP]
> Backscatterer.org 网站 () 建议在 保险箱 模式而非拒绝模式下使用服务，因为大型电子邮件服务几乎总是发送一些退信 <http://www.backscatterer.org/?target=usage> 。
