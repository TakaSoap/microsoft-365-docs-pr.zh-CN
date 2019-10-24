---
title: 批量投诉级别值、批量邮件发件、BCL 级别、BCL 的工作方式、bcl 评级、反垃圾邮件、反垃圾邮件标头、批量邮件筛选、停止批量邮件
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
description: 了解 Office 365 中的批量投诉级别（BCL）值。
ms.openlocfilehash: 822c84ea9b36cfdae1d8faccf7e0c7d9f747c917
ms.sourcegitcommit: 7830969c8fa41724359657910716f3ce312cc2cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "37650114"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="6f8e3-103">批量投诉级别值</span><span class="sxs-lookup"><span data-stu-id="6f8e3-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="6f8e3-104">批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="6f8e3-105">一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="6f8e3-106">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="6f8e3-107">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="6f8e3-108">为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="6f8e3-109">BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="6f8e3-110">BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="6f8e3-111">Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="6f8e3-112">有关此邮件头的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="6f8e3-113">由于分级为9的批量邮件可能会生成投诉，因此默认 BCL 为7。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="6f8e3-114">这意味着将接受批量邮件，直到达到7和邮件的投诉级别之后才接受。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="6f8e3-115">分级越低，接受的垃圾邮件越少。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="6f8e3-116">如果你的用户是，并且他们的工作是对批量邮件敏感，并且你的 BCL 设置为4，则将不接受具有高于4的 BCL 的批量邮件。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="6f8e3-117">通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6f8e3-118">下表介绍当前正在使用的 BCL 值。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6f8e3-119">**BCL 值**</span><span class="sxs-lookup"><span data-stu-id="6f8e3-119">**BCL Value**</span></span>|<span data-ttu-id="6f8e3-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="6f8e3-120">**Description**</span></span>|
|<span data-ttu-id="6f8e3-121">0</span><span class="sxs-lookup"><span data-stu-id="6f8e3-121">0</span></span>|<span data-ttu-id="6f8e3-122">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="6f8e3-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="6f8e3-123">1, 2, 3</span></span>|<span data-ttu-id="6f8e3-124">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="6f8e3-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="6f8e3-125">4, 5, 6, 7</span></span>|<span data-ttu-id="6f8e3-126">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="6f8e3-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="6f8e3-127">8, 9</span></span>|<span data-ttu-id="6f8e3-128">邮件来自批量发件人，生成大量投诉。</span><span class="sxs-lookup"><span data-stu-id="6f8e3-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
