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
description: '本文将介绍 EOP 服务中的退Microsoft Exchange Online和 () '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ae3cf89171f7da89ea1821c693152cdd0e3bf968f3e9ff73d517aecad2de7a5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "56826395"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*退信* 式垃圾邮件是未送达 (报告，也称为未) 发送的邮件收到的未送达报告或退回邮件。 垃圾邮件发送者伪造（欺骗）邮件的发件人：地址，并且他们经常使用真实的电子邮件地址来增强邮件的信誉。 因此，当垃圾邮件制造者难以向不存在的收件人发送邮件时 (垃圾邮件是一项大量操作) ，目标电子邮件服务器实质上被欺骗，在 NDR 中将未送达邮件返回给发件人地址中的伪造发件人。

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 会尽一切努力从可疑源中标识并静默地删除邮件，而不生成 NDR。 但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。

Backscatterer.org 阻止列表 (DNS 阻止列表或 DNSBL) 的电子邮件服务器负责发送退信，EOP 服务器可能显示在此列表上。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是由自己的允许 (垃圾邮件制造者) 。

> [!TIP]
> Backscatter.org 网站 () 建议使用其服务在 保险箱 模式下（而不是拒绝模式）检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信 <http://www.backscatterer.org/?target=usage>) 。
