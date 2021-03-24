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
description: '本文将介绍 EOP 服务中的退Microsoft Exchange Online (和) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055756"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="52393-103">EOP 中的退信式垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="52393-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="52393-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="52393-104">**Applies to**</span></span>
- [<span data-ttu-id="52393-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="52393-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="52393-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="52393-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="52393-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52393-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="52393-108">*退信* 式垃圾邮件是未送达 (，也称为未送达报告) 未发送的邮件收到的退回邮件。</span><span class="sxs-lookup"><span data-stu-id="52393-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="52393-109">垃圾邮件发送者伪造（欺骗）邮件的发件人：地址，并且他们经常使用真实的电子邮件地址来增强邮件的信誉。</span><span class="sxs-lookup"><span data-stu-id="52393-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="52393-110">因此，当垃圾邮件制造者难以向不存在的收件人发送邮件时 (垃圾邮件是一项大量操作) ，目标电子邮件服务器实质上被欺骗，在 NDR 中将未送达邮件返回给发件人地址中的伪造发件人。</span><span class="sxs-lookup"><span data-stu-id="52393-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="52393-111">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 会尽一切努力标识并静默地从可疑来源删除邮件，而不生成 NDR。</span><span class="sxs-lookup"><span data-stu-id="52393-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="52393-112">但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。</span><span class="sxs-lookup"><span data-stu-id="52393-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="52393-113">Backscatterer.org 阻止列表 (DNS 阻止列表或 DNSBL) 的电子邮件服务器负责发送退信，EOP 服务器可能出现在此列表中。</span><span class="sxs-lookup"><span data-stu-id="52393-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="52393-114">但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是由自己的允许 (垃圾邮件制造者) 。</span><span class="sxs-lookup"><span data-stu-id="52393-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="52393-115">Backscatter.org 网站 () 建议其服务在安全模式下（而不是拒绝模式）检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信 <http://www.backscatterer.org/?target=usage>) 。</span><span class="sxs-lookup"><span data-stu-id="52393-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
