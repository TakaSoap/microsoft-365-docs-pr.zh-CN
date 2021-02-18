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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '本文将介绍 EOP 保护Microsoft Exchange Online退 (和) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286965"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*退信* 式垃圾邮件是未送达 (报告，也称为) 发送的邮件的退回邮件。 垃圾邮件制造者 (欺骗) 发件人：地址，他们通常使用真实的电子邮件地址来维护其邮件的信誉。 因此，当垃圾邮件制造者无法将邮件发送到不存在的收件人 (垃圾邮件是一项高容量操作) 时，目标电子邮件服务器本质上会受欺骗，在 NDR 中将未送达邮件返回给发件人地址中的伪造发件人。

在具有 Exchange Online 邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 会尽一切努力标识并静默地从可疑来源删除邮件，而不会生成 NDR。 但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。

Backscatterer.org一个阻止列表 (也称为 DNS 阻止列表或负责发送退信的电子邮件服务器的 DNS 阻止列表) DNSBL) ，EOP 服务器可能会出现在此列表上。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是由自己的允许 (垃圾邮件制造者) 。

> [!TIP]
> Backscatter.org网站 () 建议使用服务在安全模式下而不是拒绝模式下检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信 <http://www.backscatterer.org/?target=usage>) 。
