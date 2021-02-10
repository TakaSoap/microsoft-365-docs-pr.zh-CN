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
description: 管理员可以了解 Exchange Online Protection (EOP) 中使用的 BCL (BCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165963"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="80574-103">EOP 中的批量 (BCL) 级别</span><span class="sxs-lookup"><span data-stu-id="80574-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80574-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="80574-104">**Applies to**</span></span>
- [<span data-ttu-id="80574-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="80574-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="80574-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="80574-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="80574-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80574-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="80574-108">在 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 将批量兼容级别 (BCL) 分配给来自批量邮件的入站邮件。</span><span class="sxs-lookup"><span data-stu-id="80574-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="80574-109">BCL 将添加到 X 标头中的邮件中，类似于垃圾邮件可信度 [ (SCL ](spam-confidence-levels.md)) 用于将邮件标识为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="80574-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="80574-110">BCL 越高，表明批量邮件 (产生投诉，因此更有可能是垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="80574-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="80574-111">Microsoft 使用内部源和第三方源来标识批量邮件并确定相应的 BCL。</span><span class="sxs-lookup"><span data-stu-id="80574-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="80574-112">批量邮件发送程序在发送模式、内容创建和收件人获取做法方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="80574-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="80574-113">良好的批量邮件发送器会向订阅者发送包含相关内容的所需邮件。</span><span class="sxs-lookup"><span data-stu-id="80574-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="80574-114">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="80574-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="80574-115">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="80574-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="80574-116">来自批量邮件的邮件称为"批量邮件"或"灰色邮件"。</span><span class="sxs-lookup"><span data-stu-id="80574-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="80574-117">垃圾邮件筛选根据 BCL 阈值 (默认值或指定) 的值将邮件标记为批量电子邮件，并针对邮件执行指定操作 (默认操作是将邮件发送到收件人的"垃圾邮件"文件夹) 。 </span><span class="sxs-lookup"><span data-stu-id="80574-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="80574-118">有关详细信息，请参阅" [配置反垃圾邮件](configure-your-spam-filter-policies.md) 策略"以及垃圾邮件和批量电子邮件之间有什么 [区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="80574-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="80574-119">下表介绍了 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="80574-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="80574-120">BCL</span><span class="sxs-lookup"><span data-stu-id="80574-120">BCL</span></span>|<span data-ttu-id="80574-121">说明</span><span class="sxs-lookup"><span data-stu-id="80574-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="80574-122">0</span><span class="sxs-lookup"><span data-stu-id="80574-122">0</span></span>|<span data-ttu-id="80574-123">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="80574-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="80574-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="80574-124">1, 2, 3</span></span>|<span data-ttu-id="80574-125">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="80574-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="80574-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="80574-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="80574-127">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="80574-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="80574-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="80574-128">8, 9</span></span>|<span data-ttu-id="80574-129">邮件来自生成大量投诉的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="80574-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="80574-130"><sup>\*</sup> 这是反垃圾邮件策略中使用的默认阈值。</span><span class="sxs-lookup"><span data-stu-id="80574-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
