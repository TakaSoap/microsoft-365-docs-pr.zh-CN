---
title: 批量投诉级别值
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理员可以了解批量投诉级别 (BCL) EOP Exchange Online Protection (中使用的 BCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537939"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c9bef-103">EOP 中的批量 (BCL) 级别</span><span class="sxs-lookup"><span data-stu-id="c9bef-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c9bef-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="c9bef-104">**Applies to**</span></span>
- [<span data-ttu-id="c9bef-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c9bef-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c9bef-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="c9bef-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c9bef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9bef-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c9bef-108">在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 将批量投诉级别 (BCL) 分配给来自群发邮件的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="c9bef-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c9bef-109">BCL 添加到邮件的 X 标头中，类似于垃圾邮件可信度 ([SCL ](spam-confidence-levels.md)) 用于将邮件标识为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c9bef-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c9bef-110">BCL 越高，表明批量邮件在邮件中 (产生投诉的可能性更大，因此更可能是垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="c9bef-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c9bef-111">Microsoft 使用内部源和第三方源来标识批量邮件并确定相应的 BCL。</span><span class="sxs-lookup"><span data-stu-id="c9bef-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c9bef-112">群发邮件程序在发送模式、内容创建和收件人获取做法方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="c9bef-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c9bef-113">良好的批量邮件发送器会向订阅者发送包含相关内容的所需邮件。</span><span class="sxs-lookup"><span data-stu-id="c9bef-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c9bef-114">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="c9bef-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c9bef-115">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="c9bef-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c9bef-116">来自批量邮件的邮件称为"批量邮件"或"灰色邮件"。</span><span class="sxs-lookup"><span data-stu-id="c9bef-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c9bef-117">垃圾邮件筛选根据 BCL 阈值将邮件标记为"批量电子邮件" (默认值或您指定的) 并针对邮件执行指定操作 (默认操作是将邮件发送到收件人的"垃圾邮件"文件夹) 。 </span><span class="sxs-lookup"><span data-stu-id="c9bef-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c9bef-118">有关详细信息，请参阅 [配置反垃圾邮件策略和](configure-your-spam-filter-policies.md) 垃圾邮件和批量电子邮件 [之间有什么区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c9bef-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c9bef-119">您可以使用租户允许/阻止列表配置批量邮件筛选的例外。</span><span class="sxs-lookup"><span data-stu-id="c9bef-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="c9bef-120">来自指定域中发件人的邮件不会收到反垃圾邮件策略中的批量垃圾邮件筛选裁定的操作。</span><span class="sxs-lookup"><span data-stu-id="c9bef-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c9bef-121">有关详细信息，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="c9bef-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="c9bef-122">下表介绍了 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="c9bef-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="c9bef-123">BCL</span><span class="sxs-lookup"><span data-stu-id="c9bef-123">BCL</span></span>|<span data-ttu-id="c9bef-124">说明</span><span class="sxs-lookup"><span data-stu-id="c9bef-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="c9bef-125">0</span><span class="sxs-lookup"><span data-stu-id="c9bef-125">0</span></span>|<span data-ttu-id="c9bef-126">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="c9bef-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c9bef-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c9bef-127">1, 2, 3</span></span>|<span data-ttu-id="c9bef-128">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="c9bef-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c9bef-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c9bef-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="c9bef-130">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="c9bef-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c9bef-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="c9bef-131">8, 9</span></span>|<span data-ttu-id="c9bef-132">邮件来自生成大量投诉的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="c9bef-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="c9bef-133"><sup>\*</sup> 这是反垃圾邮件策略中使用的默认阈值。</span><span class="sxs-lookup"><span data-stu-id="c9bef-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
