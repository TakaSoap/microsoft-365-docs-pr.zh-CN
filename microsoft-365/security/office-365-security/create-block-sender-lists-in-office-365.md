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
description: 管理员可以了解可用的首选选项以阻止入站邮件在 Exchange Online Protection (EOP) 中。
ms.openlocfilehash: 7894a6cfe665539fa8c00f5911c4a588b9cf7ebc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203187"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="60da0-103">在 EOP 中创建阻止的发件人列表</span><span class="sxs-lookup"><span data-stu-id="60da0-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="60da0-104">在使用 Exchange Online 或独立 Exchange online 保护的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，EOP 提供了阻止来自不需要的发件人的电子邮件的多种方式。</span><span class="sxs-lookup"><span data-stu-id="60da0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="60da0-105">这些选项包括 Outlook 阻止的发件人列表，阻止的发件人列表或阻止的域列表在反垃圾邮件策略中，Exchange 邮件流规则 (也称为传输规则) ，以及 IP 阻止列表 (连接筛选) 。</span><span class="sxs-lookup"><span data-stu-id="60da0-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="60da0-106">你可以将这些选项统称为阻止的 _发件人列表_。</span><span class="sxs-lookup"><span data-stu-id="60da0-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="60da0-107">阻止发件人的最佳方法因影响范围而异。</span><span class="sxs-lookup"><span data-stu-id="60da0-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="60da0-108">对于单个用户，正确的解决方案可能是 Outlook 阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="60da0-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="60da0-109">对于很多用户而言，其他选项中的一种更合适。</span><span class="sxs-lookup"><span data-stu-id="60da0-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="60da0-110">下面的选项按影响范围和广度进行排序。</span><span class="sxs-lookup"><span data-stu-id="60da0-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="60da0-111">列表从窄到范围，但阅读完整建议的 *细节* 。</span><span class="sxs-lookup"><span data-stu-id="60da0-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="60da0-112">Outlook 阻止的发件人 (存储在每个邮箱中的阻止发件人列表) </span><span class="sxs-lookup"><span data-stu-id="60da0-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="60da0-113"> (反垃圾邮件策略阻止的发件人列表或阻止的域列表) </span><span class="sxs-lookup"><span data-stu-id="60da0-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="60da0-114">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="60da0-114">Mail flow rules</span></span>

4. <span data-ttu-id="60da0-115"> (连接筛选的 IP 阻止列表) </span><span class="sxs-lookup"><span data-stu-id="60da0-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="60da0-116">虽然您可以使用组织范围内的阻止设置来解决丢失垃圾邮件) 的漏报 (，但还应将这些邮件提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="60da0-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="60da0-117">使用阻止列表管理漏报会显著增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="60da0-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="60da0-118">如果使用阻止列表转移丢失的垃圾邮件，则需要将主题 [报告邮件和文件](report-junk-email-messages-to-microsoft.md) 保留在 Microsoft 准备就绪。</span><span class="sxs-lookup"><span data-stu-id="60da0-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="60da0-119">相比之下，您还可以使用多个选项始终允许使用 _安全发件人列表_从特定来源发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="60da0-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="60da0-120">有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="60da0-120">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="60da0-121">电子邮件基础知识</span><span class="sxs-lookup"><span data-stu-id="60da0-121">Email message basics</span></span>

<span data-ttu-id="60da0-122">标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="60da0-122">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="60da0-123">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="60da0-123">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="60da0-124">邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="60da0-124">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="60da0-125">RFC 5321 中介绍了邮件信封，并且 RFC 5322 中介绍了邮件头。</span><span class="sxs-lookup"><span data-stu-id="60da0-125">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="60da0-126">收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，并且实际上并不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="60da0-126">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="60da0-127">该 `5321.MailFrom` 地址 (也称为 " **发** 件人地址"、"P1 发件人" 或 "信封发件人") 是在邮件的 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="60da0-127">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="60da0-128">此电子邮件地址通常记录在邮件标头的 " **返回路径** 标头" 字段中 (尽管可以将不同的 **返回路径** 电子邮件地址指定) 。</span><span class="sxs-lookup"><span data-stu-id="60da0-128">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="60da0-129">如果无法传递邮件，则表示未送达报告 (的收件人也称为 "NDR" 或 "退回邮件") 。</span><span class="sxs-lookup"><span data-stu-id="60da0-129">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="60da0-130">"发件人 `5322.From` 地址" **From**或 "P2 发件人") 的 (也称为 **"发**件人" 头字段中的电子邮件地址，它是电子邮件客户端中显示的发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="60da0-130">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="60da0-131">通常， `5321.MailFrom` 和 `5322.From` 地址 (个人到人员通信) 相同。</span><span class="sxs-lookup"><span data-stu-id="60da0-131">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="60da0-132">但是，如果代表其他人发送电子邮件，则地址可能会不同。</span><span class="sxs-lookup"><span data-stu-id="60da0-132">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="60da0-133">EOP 中的反垃圾邮件策略中阻止的发件人列表和阻止的域列表将检查 `5321.MailFrom` 和 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="60da0-133">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="60da0-134">Outlook 阻止的发件人仅使用该 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="60da0-134">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="60da0-135">使用 Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="60da0-135">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="60da0-136">当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中阻止的发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="60da0-136">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="60da0-137">有关说明，请参阅 [在 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="60da0-137">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="60da0-138">当邮件由于用户的阻止发件人列表而成功被阻止时， **X-Forefront-反垃圾邮件报告** 的标头字段将包含该值 `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="60da0-138">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="60da0-139">如果不需要的邮件是来自可信且可识别的来源的新闻快递，则取消对该电子邮件的订阅是阻止用户接收邮件的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="60da0-139">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="60da0-140">使用阻止的发件人列表或阻止的域列表</span><span class="sxs-lookup"><span data-stu-id="60da0-140">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="60da0-141">当多个用户受到影响时，范围将变宽，因此下一个最佳选项是在反垃圾邮件策略中阻止发件人列表或阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="60da0-141">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="60da0-142">来自列表中发件人的邮件被标记为 **垃圾**邮件，而您为 **垃圾邮件** 筛选器判定配置的操作将在邮件上执行。</span><span class="sxs-lookup"><span data-stu-id="60da0-142">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="60da0-143">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="60da0-143">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="60da0-144">这些列表的最大限制约为1000个条目。</span><span class="sxs-lookup"><span data-stu-id="60da0-144">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="60da0-145">使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="60da0-145">Use mail flow rules</span></span>

<span data-ttu-id="60da0-146">如果需要阻止发送到特定用户或整个组织中的邮件，则可以使用邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="60da0-146">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="60da0-147">邮件流规则比阻止发件人列表或阻止的发件人域列表更灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。</span><span class="sxs-lookup"><span data-stu-id="60da0-147">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="60da0-148">无论您用于标识邮件的条件或例外情况如何，都可以将操作配置为将邮件的垃圾邮件可信度级别 (SCL) 设置为9，这会将邮件标记为 **高可信度垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="60da0-148">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="60da0-149">有关详细信息，请参阅 [使用邮件流规则设置邮件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="60da0-149">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60da0-150">很容易创建规则 *过于* 积极的规则，因此，只需使用非常具体的条件来确定要阻止的邮件，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="60da0-150">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="60da0-151">此外，请务必对规则启用审核并测试规则的结果，以确保一切按预期工作。</span><span class="sxs-lookup"><span data-stu-id="60da0-151">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="60da0-152">使用 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="60da0-152">Use the IP Block List</span></span>

<span data-ttu-id="60da0-153">如果不能使用其他选项之一来阻止发件人，则 *只有* 在连接筛选器策略中使用 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="60da0-153">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="60da0-154">有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="60da0-154">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="60da0-155">一定要将阻止的 Ip 的数量保持为最小值，以便 *不* 建议阻止整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="60da0-155">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="60da0-156">您应该 *特别* 避免添加属于消费服务 (的 IP 地址范围，例如 outlook.com) 或共享基础结构，还应确保在定期维护过程中查看阻止的 IP 地址的列表。</span><span class="sxs-lookup"><span data-stu-id="60da0-156">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
