---
title: 创建阻止发件人列表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 管理员可以了解在创建 EOP 域中阻止入站邮件的可用 (选项) 。
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827309"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="e1be1-103">在 EOP 中创建阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="e1be1-103">Create blocked sender lists in EOP</span></span>

<span data-ttu-id="e1be1-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 提供了多种阻止来自不需要发件人的电子邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="e1be1-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="e1be1-105">这些选项包括 Outlook 阻止发件人、阻止发件人列表或阻止的域名列表、Exchange 邮件流规则 (也称为传输规则) ，以及 IP 阻止列表 (连接筛选) 。</span><span class="sxs-lookup"><span data-stu-id="e1be1-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="e1be1-106">总的来说，您可以将这些选项视为 _阻止的发件人名片_。</span><span class="sxs-lookup"><span data-stu-id="e1be1-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="e1be1-107">阻止发件人的最佳方法因影响范围而异。</span><span class="sxs-lookup"><span data-stu-id="e1be1-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="e1be1-108">对于单个用户，正确的解决方案可能是 Outlook 阻止发件人。</span><span class="sxs-lookup"><span data-stu-id="e1be1-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="e1be1-109">对于许多用户来说，其他选项可能更合适。</span><span class="sxs-lookup"><span data-stu-id="e1be1-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="e1be1-110">下列选项按影响范围和大范围内的影响进行排名。</span><span class="sxs-lookup"><span data-stu-id="e1be1-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="e1be1-111">该列表从窄到广泛， *但为了提供完整建议* ，请阅读其细分。</span><span class="sxs-lookup"><span data-stu-id="e1be1-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="e1be1-112">Outlook 阻止 (存储在每个邮箱中的阻止发件人) </span><span class="sxs-lookup"><span data-stu-id="e1be1-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="e1be1-113">反垃圾邮件策略的阻止发件人 (阻止的) </span><span class="sxs-lookup"><span data-stu-id="e1be1-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="e1be1-114">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="e1be1-114">Mail flow rules</span></span>

4. <span data-ttu-id="e1be1-115">连接筛选策略 (IP) </span><span class="sxs-lookup"><span data-stu-id="e1be1-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="e1be1-116">尽管您可以使用组织范围内阻止设置解决漏报问题 (报垃圾邮件) ，但您还应将这些邮件提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e1be1-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="e1be1-117">使用阻止列表管理误报将大大增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="e1be1-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="e1be1-118">如果您使用阻止列表以防弃使用垃圾邮件，则需要在准备就 [绪时将主题"向 Microsoft 报告](report-junk-email-messages-to-microsoft.md) 邮件和文件"。</span><span class="sxs-lookup"><span data-stu-id="e1be1-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="e1be1-119">相比之下，您也可以通过多种选择始终允许使用安全发件人列表发送来自特定 _源的电子邮件_。</span><span class="sxs-lookup"><span data-stu-id="e1be1-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="e1be1-120">有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e1be1-120">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="e1be1-121">电子邮件消息基础知识</span><span class="sxs-lookup"><span data-stu-id="e1be1-121">Email message basics</span></span>

<span data-ttu-id="e1be1-122">标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="e1be1-122">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="e1be1-123">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="e1be1-123">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="e1be1-124">邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="e1be1-124">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="e1be1-125">RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。</span><span class="sxs-lookup"><span data-stu-id="e1be1-125">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="e1be1-126">收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，实际上并不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="e1be1-126">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="e1be1-127">地址 `5321.MailFrom` (也称为 **"MAIL FROM** 地址、P1 发件人"或"信封发件人) "的电子邮件地址是邮件 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e1be1-127">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="e1be1-128">通常，此电子邮件地址记录在邮件头 (中的 **"返回** 路径"标头字段中，尽管发件人可以指定不同的 **返回** 路径电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="e1be1-128">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="e1be1-129">如果邮件无法送达，则其其人是未送达报告 (的收件人，也称为 NDR 或退回) 。</span><span class="sxs-lookup"><span data-stu-id="e1be1-129">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="e1be1-130">`5322.From` (也称为发件人地址**From**或 P2 发件人) 是"发件人"标头**字段**中的电子邮件地址，也是电子邮件客户端中显示的发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e1be1-130">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="e1be1-131">通常，与 `5321.MailFrom` 个人 `5322.From` 间的通信 (相同，这些与) 。</span><span class="sxs-lookup"><span data-stu-id="e1be1-131">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="e1be1-132">但是，当代表其他人发送电子邮件时，地址可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="e1be1-132">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="e1be1-133">EOP 中反垃圾邮件策略中的阻止发件人列表和阻止的域列表检查和 `5321.MailFrom` `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="e1be1-133">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="e1be1-134">Outlook 阻止发件人仅使用 `5322.From` 该地址。</span><span class="sxs-lookup"><span data-stu-id="e1be1-134">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="e1be1-135">使用 Outlook 阻止发件人</span><span class="sxs-lookup"><span data-stu-id="e1be1-135">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="e1be1-136">仅少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中"阻止的发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="e1be1-136">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="e1be1-137">有关说明，请参阅 [在 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="e1be1-137">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="e1be1-138">当由于用户阻止的发件人名单而导致邮件成功阻止时 **，X-Forefront-Antispam-Report** 标头字段将包含该值 `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="e1be1-138">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="e1be1-139">如果不需要的邮件是来自可信源且可识别的新闻稿，则无法从电子邮件中取消订阅是阻止用户接收邮件的另一个选项。</span><span class="sxs-lookup"><span data-stu-id="e1be1-139">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="e1be1-140">使用阻止发件人列表或阻止的域列表</span><span class="sxs-lookup"><span data-stu-id="e1be1-140">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="e1be1-141">如果多个用户受到影响，作用域更广，则下一个最佳选项是阻止反垃圾邮件策略中的发件人列表或阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="e1be1-141">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="e1be1-142">来自列表上的发件人的邮件被标记为 **"垃圾邮件"，** 您配置的 **适用于垃圾邮件** 筛选器验证词语的操作会在邮件上执行。</span><span class="sxs-lookup"><span data-stu-id="e1be1-142">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="e1be1-143">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e1be1-143">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e1be1-144">这些列表的最大限制是大约 1000 个条目。</span><span class="sxs-lookup"><span data-stu-id="e1be1-144">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="e1be1-145">使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="e1be1-145">Use mail flow rules</span></span>

<span data-ttu-id="e1be1-146">如果需要阻止发送到特定用户或跨整个组织的邮件，可以使用邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="e1be1-146">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="e1be1-147">邮件流规则比阻止发件人列表或阻止发件人域列表灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。</span><span class="sxs-lookup"><span data-stu-id="e1be1-147">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="e1be1-148">无论使用哪种条件或例外来标识邮件，您应将操作配置为将邮件的垃圾邮件可信度 (SCL) 设置为 9，以将邮件的"**高可信度垃圾邮件"标记为"高可信度"。**</span><span class="sxs-lookup"><span data-stu-id="e1be1-148">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="e1be1-149">有关详细信息，请参阅"[使用邮件流规则"在邮件中设置 SCL。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="e1be1-149">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1be1-150">创建非常周于很容易，因此*overly*务必要仅识别要使用非常具体的条件阻止的邮件。</span><span class="sxs-lookup"><span data-stu-id="e1be1-150">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="e1be1-151">此外，请确保启用规则审核并测试规则的结果，以确保一切按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="e1be1-151">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="e1be1-152">使用 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="e1be1-152">Use the IP Block List</span></span>

<span data-ttu-id="e1be1-153">如果不能使用其他选项之一阻止发件人，应 *只应* 在连接筛选器策略中使用 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="e1be1-153">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="e1be1-154">有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e1be1-154">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="e1be1-155">请务必将阻止的 IP 数数保持为最少，因此不建议阻止整个 IP *地址* 范围。</span><span class="sxs-lookup"><span data-stu-id="e1be1-155">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="e1be1-156">应 *特别避免* 添加属于使用者服务 (例如 outlook.com) 或共享基础架构）的 IP 地址范围，同时确保在常规维护时查看被阻止的 IP 地址的列表。</span><span class="sxs-lookup"><span data-stu-id="e1be1-156">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
