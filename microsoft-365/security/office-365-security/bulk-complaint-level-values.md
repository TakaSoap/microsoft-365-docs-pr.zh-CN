---
title: 批量投诉级别值
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection （EOP）中使用的批量合规性级别（BCL）值。
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209603"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="eb2d5-103">EOP 中的大宗投诉级别（BCL）</span><span class="sxs-lookup"><span data-stu-id="eb2d5-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="eb2d5-104">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中具有邮箱的 Microsoft 365 组织中，EOP 会从批量邮件发件人向入站邮件分配一个批量合规性级别（BCL）。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="eb2d5-105">将 BCL 添加到邮件的 X 标头中，类似于用于将邮件标识为垃圾邮件的[垃圾邮件可信度（SCL）](spam-confidence-levels.md) 。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="eb2d5-106">较高的 BCL 指示批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="eb2d5-107">Microsoft 使用内部和第三方源来标识批量邮件，并确定相应的 BCL。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="eb2d5-108">批量收件人因其发送模式、内容创建和收件人获取实践而异。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="eb2d5-109">正常批量邮件发送将包含相关内容的邮件发送到订阅者。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="eb2d5-110">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="eb2d5-111">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="eb2d5-112">来自批量邮件散播邮件的邮件称为 "批量邮件" 或 "灰色邮件"。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="eb2d5-113">垃圾邮件筛选将邮件标记为基于 BCL 阈值（默认值或指定值）的**批量电子邮件**，并对邮件执行指定的操作（默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="eb2d5-114">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="eb2d5-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="eb2d5-115">下表描述了 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="eb2d5-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="eb2d5-116">**BCL**</span></span>|<span data-ttu-id="eb2d5-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb2d5-117">**Description**</span></span>|
|<span data-ttu-id="eb2d5-118">0</span><span class="sxs-lookup"><span data-stu-id="eb2d5-118">0</span></span>|<span data-ttu-id="eb2d5-119">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="eb2d5-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="eb2d5-120">1, 2, 3</span></span>|<span data-ttu-id="eb2d5-121">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="eb2d5-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="eb2d5-122">4, 5, 6, 7</span></span>|<span data-ttu-id="eb2d5-123">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="eb2d5-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="eb2d5-124">8, 9</span></span>|<span data-ttu-id="eb2d5-125">邮件来自批量发件人，生成大量投诉。</span><span class="sxs-lookup"><span data-stu-id="eb2d5-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
