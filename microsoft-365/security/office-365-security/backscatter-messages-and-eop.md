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
# <a name="backscatter-in-eop"></a><span data-ttu-id="4d4a4-103">EOP 中的退信式垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4d4a4-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4d4a4-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4d4a4-104">**Applies to**</span></span>
- [<span data-ttu-id="4d4a4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4d4a4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4d4a4-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4d4a4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4d4a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d4a4-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4d4a4-108">*退信* 式垃圾邮件是未送达 (报告，也称为) 发送的邮件的退回邮件。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="4d4a4-109">垃圾邮件制造者 (欺骗) 发件人：地址，他们通常使用真实的电子邮件地址来维护其邮件的信誉。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="4d4a4-110">因此，当垃圾邮件制造者无法将邮件发送到不存在的收件人 (垃圾邮件是一项高容量操作) 时，目标电子邮件服务器本质上会受欺骗，在 NDR 中将未送达邮件返回给发件人地址中的伪造发件人。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="4d4a4-111">在具有 Exchange Online 邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 会尽一切努力标识并静默地从可疑来源删除邮件，而不会生成 NDR。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="4d4a4-112">但是，根据服务中大量的电子邮件流，EOP 始终有可能无意中发送退信。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="4d4a4-113">Backscatterer.org一个阻止列表 (也称为 DNS 阻止列表或负责发送退信的电子邮件服务器的 DNS 阻止列表) DNSBL) ，EOP 服务器可能会出现在此列表上。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="4d4a4-114">但是，我们不会尝试从 Backscatterer.org 阻止列表中删除自己，因为它不是由自己的允许 (垃圾邮件制造者) 。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="4d4a4-115">Backscatter.org网站 () 建议使用服务在安全模式下而不是拒绝模式下检查传入电子邮件 (大型电子邮件服务几乎始终会发送一些退信 <http://www.backscatterer.org/?target=usage>) 。</span><span class="sxs-lookup"><span data-stu-id="4d4a4-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
