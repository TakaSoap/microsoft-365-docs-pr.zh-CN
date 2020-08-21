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
description: '本文将介绍如何使用 Windows SharePoint Microsoft Exchange Online Protection (信息) '
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827781"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="3ced0-103">EOP 中的退信式垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="3ced0-103">Backscatter in EOP</span></span>

<span data-ttu-id="3ced0-104">*退信式垃圾邮件* 是未送达 (也称为 NDR，或是) 您收到未发送的邮件的退回邮件。</span><span class="sxs-lookup"><span data-stu-id="3ced0-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="3ced0-105">垃圾邮件制程序 (伪) 发件人： 地址的发件人：地址，并且通常使用真实的电子邮件地址来将邮件置信。</span><span class="sxs-lookup"><span data-stu-id="3ced0-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="3ced0-106">因此，如果垃圾邮件发送者不可从性上发送邮件 (垃圾邮件是一个高容量操作) ，则目标电子邮件服务器实际上会被阻止，在 NDR 中将未送达的邮件返回到"发件人： 地址"中的"到外部： 到外部： "发件人：</span><span class="sxs-lookup"><span data-stu-id="3ced0-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="3ced0-107">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 可借助 EOP 根据双重来源识别并自动删除邮件，而不会生成 NDR。</span><span class="sxs-lookup"><span data-stu-id="3ced0-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="3ced0-108">但是，根据通过服务传输的单单一批量电子邮件，EOP 始终会无意中发送退信式垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="3ced0-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="3ced0-109">Backscatterer.org保留一个阻止列表 (也称为负责发送退信的) 电子邮件服务器的 DNS 阻止列表或 DNSBL 名称，EOP 服务器可能出现在此列表中。</span><span class="sxs-lookup"><span data-stu-id="3ced0-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="3ced0-110">但是，我们不会尝试将我们自己从 Backscatterer.org 阻止列表中删除，因为它不是垃圾邮件制造者列表， (他们自身) 。</span><span class="sxs-lookup"><span data-stu-id="3ced0-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="3ced0-111">这Backscatter.org网站 () 建议使用其服务来检查安全模式下的传入电子邮件，而不是使用"拒绝 <http://www.backscatterer.org/?target=usage> "模式 (大的电子邮件服务几乎总是会发送一些退信) 。</span><span class="sxs-lookup"><span data-stu-id="3ced0-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
