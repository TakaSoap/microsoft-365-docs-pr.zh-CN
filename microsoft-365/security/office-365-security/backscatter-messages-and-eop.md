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
description: '本文将介绍 EOP 服务中的退Microsoft Exchange Online和 (保护) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165951"
---
# <a name="backscatter-in-eop"></a>EOP 中的退信式垃圾邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

*退信* 式垃圾邮件是未送达 (报告，也称为未) 发送的邮件收到的邮件的未送达报告或退回邮件。 垃圾邮件制造者 (欺骗) 发件人：地址中伪造邮件，并且他们通常使用真实电子邮件地址为邮件提供信誉。 因此，当垃圾邮件制造者难以向不存在的收件人发送邮件时 (垃圾邮件是一项大量操作) ，则目标电子邮件服务器本质上会受欺骗，将 NDR 中的未送达邮件返回给发件人地址中的伪造发件人。

在具有 Exchange Online 邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 将尽一切努力识别可疑源中的邮件并静默地丢弃邮件，而不生成 NDR。 但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。

Backscatterer.org一个阻止列表 (也称为 DNS 阻止列表或负责发送退信的电子邮件服务器的 DNSBL) ，EOP 服务器可能显示在此列表上。 但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是通过自己的允许 (垃圾邮件制造者) 。

> [!TIP]
> Backscatter.org网站 () 建议使用其服务在安全模式（而不是拒绝模式）中检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信式垃圾邮件 <http://www.backscatterer.org/?target=usage>) 。
