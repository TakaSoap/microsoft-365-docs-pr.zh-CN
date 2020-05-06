---
title: 批量投诉级别值
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: 了解 Office 365 中的 "批量合规性级别（BCL）" 值。
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035564"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="37ca8-103">Office 365 中的大宗投诉级别（BCL）</span><span class="sxs-lookup"><span data-stu-id="37ca8-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="37ca8-104">批量收件人因其发送模式、内容创建和收件人获取实践而异。</span><span class="sxs-lookup"><span data-stu-id="37ca8-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="37ca8-105">有些是极大批量邮件程序，可向订阅者发送带有相关内容的所需邮件。</span><span class="sxs-lookup"><span data-stu-id="37ca8-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="37ca8-106">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="37ca8-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="37ca8-107">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="37ca8-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="37ca8-108">来自批量邮件散播邮件的邮件称为 "批量邮件" 或 "灰色邮件"。</span><span class="sxs-lookup"><span data-stu-id="37ca8-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="37ca8-109">若要区分来自不同类型的批量发件人的邮件，批量邮件（Exchange Online 或独立 Exchange Online 保护（EOP），不包含 Exchange Online 邮箱）的入站邮件被分配了一个以 X 标头形式添加到邮件的批量投诉级别（BCL）。</span><span class="sxs-lookup"><span data-stu-id="37ca8-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="37ca8-110">BCL 类似于用于将邮件标识为垃圾邮件的[垃圾邮件信任级别（SCL）](spam-confidence-levels.md) 。</span><span class="sxs-lookup"><span data-stu-id="37ca8-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="37ca8-111">较高的 BCL 指示批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="37ca8-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="37ca8-112">Microsoft 使用内部和第三方源来标识批量邮件，并确定相应的 BCL。</span><span class="sxs-lookup"><span data-stu-id="37ca8-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="37ca8-113">垃圾邮件筛选将邮件标记为基于 BCL 阈值（默认值或指定值）的**批量电子邮件**，并对邮件执行指定的操作（默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="37ca8-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="37ca8-114">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="37ca8-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="37ca8-115">下表描述了 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="37ca8-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="37ca8-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="37ca8-116">**BCL**</span></span>|<span data-ttu-id="37ca8-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="37ca8-117">**Description**</span></span>|
|<span data-ttu-id="37ca8-118">0</span><span class="sxs-lookup"><span data-stu-id="37ca8-118">0</span></span>|<span data-ttu-id="37ca8-119">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="37ca8-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="37ca8-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="37ca8-120">1, 2, 3</span></span>|<span data-ttu-id="37ca8-121">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="37ca8-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="37ca8-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="37ca8-122">4, 5, 6, 7</span></span>|<span data-ttu-id="37ca8-123">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="37ca8-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="37ca8-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="37ca8-124">8, 9</span></span>|<span data-ttu-id="37ca8-125">邮件来自批量发件人，生成大量投诉。</span><span class="sxs-lookup"><span data-stu-id="37ca8-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
