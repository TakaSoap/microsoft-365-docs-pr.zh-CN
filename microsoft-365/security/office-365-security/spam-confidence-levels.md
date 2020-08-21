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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解应用到 EOP (Exchange Online Protection) 的 SCL 证书中的垃圾邮件可 (信度) 。
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827393"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="b418b-103">EOP 中适用的 (SCL) 可信度</span><span class="sxs-lookup"><span data-stu-id="b418b-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="b418b-104">在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，入站邮件通过 EOP 中的垃圾邮件筛选并分配有垃圾邮件得分。</span><span class="sxs-lookup"><span data-stu-id="b418b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="b418b-105">该分数将被映射到添加到 X 标头 (邮件的单个垃圾邮件可) 信度 (SCL。</span><span class="sxs-lookup"><span data-stu-id="b418b-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="b418b-106">SCL 更高，表示邮件是垃圾邮件的可能性较大。</span><span class="sxs-lookup"><span data-stu-id="b418b-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="b418b-107">EOP 根据 SCL 对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="b418b-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="b418b-108">下表描述了 SCL 意味及对邮件采取的默认操作。</span><span class="sxs-lookup"><span data-stu-id="b418b-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="b418b-109">有关可以基于垃圾邮件筛选谓词对邮件采取的操作的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b418b-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="b418b-110">SCL</span><span class="sxs-lookup"><span data-stu-id="b418b-110">SCL</span></span>|<span data-ttu-id="b418b-111">定义</span><span class="sxs-lookup"><span data-stu-id="b418b-111">Definition</span></span>|<span data-ttu-id="b418b-112">默认操作</span><span class="sxs-lookup"><span data-stu-id="b418b-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="b418b-113">-1</span><span class="sxs-lookup"><span data-stu-id="b418b-113">-1</span></span>|<span data-ttu-id="b418b-114">邮件跳过了垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="b418b-114">The message skipped spam filtering.</span></span> <span data-ttu-id="b418b-115">例如，该邮件来自安全发件人，或从 IP 允许列表上的电子邮件源服务器发送。</span><span class="sxs-lookup"><span data-stu-id="b418b-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="b418b-116">有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b418b-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="b418b-117">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b418b-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="b418b-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="b418b-118">0, 1</span></span>|<span data-ttu-id="b418b-119">垃圾邮件筛选确定邮件不是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b418b-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="b418b-120">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b418b-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="b418b-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="b418b-121">5, 6</span></span>|<span data-ttu-id="b418b-122">邮件被筛选标记为 **"垃圾邮件"**</span><span class="sxs-lookup"><span data-stu-id="b418b-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="b418b-123">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b418b-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="b418b-124">9 </span><span class="sxs-lookup"><span data-stu-id="b418b-124">9</span></span>|<span data-ttu-id="b418b-125">邮件被标记为" **高可信度垃圾邮件"的垃圾邮件筛选**</span><span class="sxs-lookup"><span data-stu-id="b418b-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="b418b-126">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b418b-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="b418b-127">您会注意到垃圾邮件筛选不会使用 SCL 2、3、4、7 和 8。</span><span class="sxs-lookup"><span data-stu-id="b418b-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="b418b-128">可以使用邮件流规则 (也称为用于标记邮件上) SCL 的传输规则。</span><span class="sxs-lookup"><span data-stu-id="b418b-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="b418b-129">如果你使用邮件流规则设置 SCL，则值 5 或 6 会触发垃圾邮件筛选 **操作对垃圾邮件**，值为 7、8 或 9 会触发"高可信度垃圾邮件" **的垃圾邮件筛选操作**。</span><span class="sxs-lookup"><span data-stu-id="b418b-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="b418b-130">有关详细信息，请参阅" [使用邮件流规则"在邮件中设置关于 SCL (的) 可信度](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b418b-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="b418b-131">与 SCL 类似，批量公合级别 (BCL) 它标识了变成灰 (色邮件的邮件 _项目和格式_) 。</span><span class="sxs-lookup"><span data-stu-id="b418b-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="b418b-132">BCL 更高，则大量邮件更有可能生成电子邮件 (因此更可能是垃圾邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b418b-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="b418b-133">配置反垃圾邮件策略中的 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="b418b-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="b418b-134">有关详细信息，请参阅"[在 EOP 中配置反垃圾邮件策略"、批量](configure-your-spam-filter-policies.md)与会级[ (BCL) （EOP) ） 以及](bulk-complaint-level-values.md)垃圾邮件和批量邮件之间[有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="b418b-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="b418b-135">![LinkedIn Learning New 到 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 简短图标？**</span><span class="sxs-lookup"><span data-stu-id="b418b-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="b418b-136">发现 LinkedIn Learning 向 **Microsoft 365 管理员**和 IT 专业人人提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="b418b-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
