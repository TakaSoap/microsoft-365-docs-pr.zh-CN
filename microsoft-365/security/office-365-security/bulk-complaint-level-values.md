---
title: 批量投诉级别值、批量邮件发件、BCL 级别、BCL 的工作方式、bcl 评级、反垃圾邮件、反垃圾邮件标头、批量邮件筛选、停止批量邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 了解有关 Office 365 中的批量 bomplain 级别（BCL）值的信息。
ms.openlocfilehash: 6b90064db7dd9b27fdc729b65fb798dfbe756da7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895389"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="53823-103">Office 365 中的大宗投诉级别（BCL）</span><span class="sxs-lookup"><span data-stu-id="53823-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="53823-104">批量收件人因其发送模式、内容创建和收件人获取实践而异。</span><span class="sxs-lookup"><span data-stu-id="53823-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="53823-105">有些是极大批量邮件程序，可向订阅者发送带有相关内容的所需邮件。</span><span class="sxs-lookup"><span data-stu-id="53823-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="53823-106">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="53823-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="53823-107">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="53823-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="53823-108">来自批量邮件散播邮件的邮件称为 "批量邮件" 或 "灰色邮件"。</span><span class="sxs-lookup"><span data-stu-id="53823-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="53823-109">若要区分来自不同类型的批量邮件的邮件，从批量邮件发件人到 Office 365 （Exchange Online 或独立 Exchange Online Protection （EOP），而不是 Exchange Online 邮箱）的入站电子邮件被分配了一个添加到的批量投诉级别（BCL）X 标头中的邮件。</span><span class="sxs-lookup"><span data-stu-id="53823-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="53823-110">BCL 类似于用于将邮件标识为垃圾邮件的[垃圾邮件信任级别（SCL）](spam-confidence-levels.md) 。</span><span class="sxs-lookup"><span data-stu-id="53823-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="53823-111">较高的 BCL 指示批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="53823-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="53823-112">Microsoft 使用内部和第三方源来标识批量邮件，并确定相应的 BCL。</span><span class="sxs-lookup"><span data-stu-id="53823-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="53823-113">垃圾邮件筛选将邮件标记为基于 BCL 阈值（默认值或指定值）的**批量电子邮件**，并对邮件执行指定的操作（默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="53823-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="53823-114">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="53823-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

<span data-ttu-id="53823-115">下表描述了 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="53823-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="53823-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="53823-116">**BCL**</span></span>|<span data-ttu-id="53823-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="53823-117">**Description**</span></span>|
|<span data-ttu-id="53823-118">0</span><span class="sxs-lookup"><span data-stu-id="53823-118">0</span></span>|<span data-ttu-id="53823-119">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="53823-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="53823-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="53823-120">1, 2, 3</span></span>|<span data-ttu-id="53823-121">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="53823-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="53823-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="53823-122">4, 5, 6, 7</span></span>|<span data-ttu-id="53823-123">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="53823-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="53823-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="53823-124">8, 9</span></span>|<span data-ttu-id="53823-125">邮件来自批量发件人，生成大量投诉。</span><span class="sxs-lookup"><span data-stu-id="53823-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
