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
# <a name="backscatter-in-eop"></a><span data-ttu-id="59822-103">EOP 中的退信式垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="59822-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="59822-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="59822-104">**Applies to**</span></span>
- [<span data-ttu-id="59822-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="59822-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="59822-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="59822-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="59822-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59822-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="59822-108">*退信* 式垃圾邮件是未送达 (报告，也称为未) 发送的邮件收到的邮件的未送达报告或退回邮件。</span><span class="sxs-lookup"><span data-stu-id="59822-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="59822-109">垃圾邮件制造者 (欺骗) 发件人：地址中伪造邮件，并且他们通常使用真实电子邮件地址为邮件提供信誉。</span><span class="sxs-lookup"><span data-stu-id="59822-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="59822-110">因此，当垃圾邮件制造者难以向不存在的收件人发送邮件时 (垃圾邮件是一项大量操作) ，则目标电子邮件服务器本质上会受欺骗，将 NDR 中的未送达邮件返回给发件人地址中的伪造发件人。</span><span class="sxs-lookup"><span data-stu-id="59822-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="59822-111">在具有 Exchange Online 邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 将尽一切努力识别可疑源中的邮件并静默地丢弃邮件，而不生成 NDR。</span><span class="sxs-lookup"><span data-stu-id="59822-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="59822-112">但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。</span><span class="sxs-lookup"><span data-stu-id="59822-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="59822-113">Backscatterer.org一个阻止列表 (也称为 DNS 阻止列表或负责发送退信的电子邮件服务器的 DNSBL) ，EOP 服务器可能显示在此列表上。</span><span class="sxs-lookup"><span data-stu-id="59822-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="59822-114">但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是通过自己的允许 (垃圾邮件制造者) 。</span><span class="sxs-lookup"><span data-stu-id="59822-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="59822-115">Backscatter.org网站 () 建议使用其服务在安全模式（而不是拒绝模式）中检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信式垃圾邮件 <http://www.backscatterer.org/?target=usage>) 。</span><span class="sxs-lookup"><span data-stu-id="59822-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
