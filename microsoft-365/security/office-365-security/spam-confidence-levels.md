---
title: 垃圾邮件可信度
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解应用于 Exchange Online Protection (EOP) 中的邮件的垃圾邮件可信度 (SCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203204"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="9ca58-103">EOP 中的垃圾邮件 (SCL) 级别</span><span class="sxs-lookup"><span data-stu-id="9ca58-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="9ca58-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9ca58-104">**Applies to**</span></span>
- [<span data-ttu-id="9ca58-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9ca58-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9ca58-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9ca58-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9ca58-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ca58-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ca58-108">在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，入站邮件通过 EOP 中的垃圾邮件筛选，并分配有垃圾邮件得分。</span><span class="sxs-lookup"><span data-stu-id="9ca58-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="9ca58-109">该分数映射到添加到 X 标头中的 (SCL) 单个垃圾邮件可信度。</span><span class="sxs-lookup"><span data-stu-id="9ca58-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="9ca58-110">SCL 越高，邮件就越有可能是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="9ca58-111">EOP 根据 SCL 对邮件采取操作。</span><span class="sxs-lookup"><span data-stu-id="9ca58-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="9ca58-112">下表介绍了 SCL 的含义以及对邮件执行的默认操作。</span><span class="sxs-lookup"><span data-stu-id="9ca58-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="9ca58-113">有关可以基于垃圾邮件筛选裁定对邮件采取的操作详细信息，请参阅在 [EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="9ca58-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="9ca58-114">SCL</span><span class="sxs-lookup"><span data-stu-id="9ca58-114">SCL</span></span>|<span data-ttu-id="9ca58-115">定义</span><span class="sxs-lookup"><span data-stu-id="9ca58-115">Definition</span></span>|<span data-ttu-id="9ca58-116">默认操作</span><span class="sxs-lookup"><span data-stu-id="9ca58-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="9ca58-117">-1</span><span class="sxs-lookup"><span data-stu-id="9ca58-117">-1</span></span>|<span data-ttu-id="9ca58-118">邮件跳过了垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9ca58-118">The message skipped spam filtering.</span></span> <span data-ttu-id="9ca58-119">例如，邮件来自安全发件人、发送给安全收件人或来自 IP 允许列表上的电子邮件源服务器。</span><span class="sxs-lookup"><span data-stu-id="9ca58-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="9ca58-120">有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="9ca58-121">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="9ca58-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9ca58-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="9ca58-122">0, 1</span></span>|<span data-ttu-id="9ca58-123">垃圾邮件筛选确定邮件不是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="9ca58-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="9ca58-124">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="9ca58-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="9ca58-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="9ca58-125">5, 6</span></span>|<span data-ttu-id="9ca58-126">垃圾邮件筛选将邮件标记为 **"垃圾邮件"**</span><span class="sxs-lookup"><span data-stu-id="9ca58-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="9ca58-127">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ca58-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="9ca58-128">9 </span><span class="sxs-lookup"><span data-stu-id="9ca58-128">9</span></span>|<span data-ttu-id="9ca58-129">垃圾邮件筛选将邮件标记为 **高可信度垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9ca58-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="9ca58-130">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ca58-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="9ca58-131">你会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7 和 8。</span><span class="sxs-lookup"><span data-stu-id="9ca58-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="9ca58-132">您可以使用邮件流规则 (传输规则) 标记邮件上的 SCL。</span><span class="sxs-lookup"><span data-stu-id="9ca58-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="9ca58-133">如果使用邮件流规则设置 SCL，则值 5 或 6 将触发 **垃圾邮件** 的垃圾邮件筛选操作，值 7、8 或 9 将触发高可信度垃圾邮件的垃圾邮件筛选 **操作**。</span><span class="sxs-lookup"><span data-stu-id="9ca58-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="9ca58-134">有关详细信息，请参阅使用邮件 [流规则在邮件中设置 (SCL) 垃圾邮件可信度](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca58-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="9ca58-135">与 SCL 类似，BCL 中的批量投诉级别 (BCL) 识别错误批量 (也称为灰色 _邮件) 。_</span><span class="sxs-lookup"><span data-stu-id="9ca58-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="9ca58-136">BCL 越高，大量邮件产生投诉的可能性就越大（因此更有可能是垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="9ca58-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="9ca58-137">您可以在反垃圾邮件策略中配置 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="9ca58-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="9ca58-138">有关详细信息，请参阅在[EOP](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略[、EOP ](bulk-complaint-level-values.md)) 中的批量投诉级别 (BCL) 和垃圾邮件和批量电子邮件之间有什么[区别？。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="9ca58-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="9ca58-139">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 的简短图标**</span><span class="sxs-lookup"><span data-stu-id="9ca58-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="9ca58-140">发现 LinkedIn Learning 为 **Microsoft 365** 管理员和 IT 专业人员提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="9ca58-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
