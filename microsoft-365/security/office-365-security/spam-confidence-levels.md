---
title: 垃圾邮件可信度
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 在本文中，管理员可以了解垃圾邮件信任级别（SCL）如何将邮件的 likeliness 确定为垃圾邮件。
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035244"
---
# <a name="spam-confidence-level-scl-in-office-365"></a><span data-ttu-id="b9cd5-103">Office 365 中的垃圾邮件可信度（SCL）</span><span class="sxs-lookup"><span data-stu-id="b9cd5-103">Spam confidence level (SCL) in Office 365</span></span>

<span data-ttu-id="b9cd5-104">当 Microsoft 365 （Exchange Online 或独立 Exchange Online Protection （EOP），而不是 Exchange Online 邮箱）收到入站电子邮件时，邮件将通过垃圾邮件筛选，并为其分配一个垃圾邮件分数。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-104">When Microsoft 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) receives an inbound email message, the message goes through spam filtering, and is assigned a spam score.</span></span> <span data-ttu-id="b9cd5-105">该分数映射到在 X 标头中添加到邮件的单个垃圾邮件可信度（SCL）。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="b9cd5-106">SCL 较高表示邮件更有可能是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="b9cd5-107">该服务将根据 SCL 对邮件采取操作。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-107">The service takes action on the message based on the SCL.</span></span>

<span data-ttu-id="b9cd5-108">下表描述了 SCL 的含义以及对邮件所执行的默认操作。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="b9cd5-109">有关可以对基于垃圾邮件筛选判定的邮件执行的操作的详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

||||
|:---:|---|---|
|<span data-ttu-id="b9cd5-110">**SCL**</span><span class="sxs-lookup"><span data-stu-id="b9cd5-110">**SCL**</span></span>|<span data-ttu-id="b9cd5-111">**定义**</span><span class="sxs-lookup"><span data-stu-id="b9cd5-111">**Definition**</span></span>|<span data-ttu-id="b9cd5-112">**默认操作**</span><span class="sxs-lookup"><span data-stu-id="b9cd5-112">**Default action**</span></span>|
|<span data-ttu-id="b9cd5-113">-1</span><span class="sxs-lookup"><span data-stu-id="b9cd5-113">-1</span></span>|<span data-ttu-id="b9cd5-114">邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-114">The message skipped spam filtering.</span></span> <span data-ttu-id="b9cd5-115">例如，邮件来自安全发件人，发送到安全收件人，或者来自 IP 允许列表中的电子邮件源服务器。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="b9cd5-116">有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-116">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="b9cd5-117">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="b9cd5-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="b9cd5-118">0, 1</span></span>|<span data-ttu-id="b9cd5-119">垃圾邮件筛选已确定邮件不是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="b9cd5-120">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="b9cd5-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="b9cd5-121">5, 6</span></span>|<span data-ttu-id="b9cd5-122">垃圾邮件筛选功能已将邮件标记为**垃圾**邮件</span><span class="sxs-lookup"><span data-stu-id="b9cd5-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="b9cd5-123">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="b9cd5-124">9 </span><span class="sxs-lookup"><span data-stu-id="b9cd5-124">9</span></span>|<span data-ttu-id="b9cd5-125">垃圾邮件筛选功能已将邮件标记为**高可信度垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b9cd5-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="b9cd5-126">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="b9cd5-127">您会注意到，垃圾邮件筛选不会使用 SCL 2、3、4、7和8。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="b9cd5-128">您可以使用邮件流规则（也称为传输规则）在邮件上标记 SCL。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="b9cd5-129">如果使用邮件流规则设置 SCL，则值5或6将触发垃圾邮件的垃圾邮件筛选操作，值7、8或9将触发垃圾邮件筛选**操作，以**实现**高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="b9cd5-130">有关详细信息，请参阅[使用邮件流规则在邮件中设置垃圾邮件可信度级别（SCL）](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="b9cd5-131">与 SCL 类似，批量投诉级别（BCL）标识错误的批量电子邮件（也称为_灰色邮件_）。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="b9cd5-132">较高的 BCL 表明批量邮件更有可能生成投诉（因此更可能是垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="b9cd5-133">在反垃圾邮件策略中配置 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="b9cd5-134">有关详细信息，请参阅[在 office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)、 [office 365 中的批量投诉级别（BCL）](bulk-complaint-level-values.md)，以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in Office 365)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

||
|:-----|
|<span data-ttu-id="b9cd5-135">![LinkedIn Learning 短图标](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="b9cd5-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="b9cd5-136">探索通过 LinkedIn 学习获取的适用于**Microsoft 365 管理员和 IT 专业人员**的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="b9cd5-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
