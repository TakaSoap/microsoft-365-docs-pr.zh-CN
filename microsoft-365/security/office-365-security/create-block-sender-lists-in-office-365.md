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
localization_priority: Normal
search.appverid:
- MET150s
description: 管理员可以了解在 EOP 电子邮件中阻止入站邮件的可用Exchange Online Protection (首选) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c844378a19ba7995cbd616f615e8a84994f9bf26
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624073"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="7acba-103">在 EOP 中创建阻止的发件人列表</span><span class="sxs-lookup"><span data-stu-id="7acba-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7acba-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="7acba-104">**Applies to**</span></span>
- [<span data-ttu-id="7acba-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7acba-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7acba-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="7acba-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7acba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7acba-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7acba-108">在Microsoft 365没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中，EOP 提供了多种阻止来自不需要的发件人的电子邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="7acba-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="7acba-109">这些选项包括Outlook阻止的发件人、反垃圾邮件策略中的阻止发件人列表或阻止的域列表、Exchange 邮件流规则 (也称为传输规则) 以及 IP 阻止列表 (连接筛选) 。</span><span class="sxs-lookup"><span data-stu-id="7acba-109">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="7acba-110">您一起可以将这些选项视为 _阻止的发件人列表_。</span><span class="sxs-lookup"><span data-stu-id="7acba-110">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="7acba-111">阻止发件人的最佳方法因影响范围而异。</span><span class="sxs-lookup"><span data-stu-id="7acba-111">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="7acba-112">对于单个用户，正确的解决方案可能是Outlook阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="7acba-112">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="7acba-113">对于许多用户，其他选项之一更为合适。</span><span class="sxs-lookup"><span data-stu-id="7acba-113">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="7acba-114">以下选项按影响范围和广度进行排名。</span><span class="sxs-lookup"><span data-stu-id="7acba-114">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="7acba-115">该列表从窄到宽，但请阅读具体 *内容* ，了解完整建议。</span><span class="sxs-lookup"><span data-stu-id="7acba-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="7acba-116">Outlook阻止的 (每个邮箱邮箱中存储的"阻止的发件人"列表) </span><span class="sxs-lookup"><span data-stu-id="7acba-116">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="7acba-117">阻止的发件人列表或阻止的域 (反垃圾邮件策略) </span><span class="sxs-lookup"><span data-stu-id="7acba-117">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="7acba-118">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="7acba-118">Mail flow rules</span></span>

4. <span data-ttu-id="7acba-119">IP 阻止列表 (筛选) </span><span class="sxs-lookup"><span data-stu-id="7acba-119">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="7acba-120">虽然您可以使用组织范围的阻止设置来解决漏报垃圾邮件 (漏报) ，但您还应将那些邮件提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="7acba-120">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="7acba-121">使用阻止列表管理漏报会显著增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="7acba-121">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="7acba-122">如果使用阻止列表来阻止错过的垃圾邮件，则需要将主题"将邮件和文件报告给 [Microsoft"](report-junk-email-messages-to-microsoft.md) 保持就绪状态。</span><span class="sxs-lookup"><span data-stu-id="7acba-122">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="7acba-123">相比之下，你还有若干选项可以始终允许来自使用安全发件人列表的特定 _来源的电子邮件_。</span><span class="sxs-lookup"><span data-stu-id="7acba-123">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="7acba-124">有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7acba-124">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="7acba-125">电子邮件基础知识</span><span class="sxs-lookup"><span data-stu-id="7acba-125">Email message basics</span></span>

<span data-ttu-id="7acba-126">标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="7acba-126">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="7acba-127">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="7acba-127">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="7acba-128">邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="7acba-128">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="7acba-129">RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。</span><span class="sxs-lookup"><span data-stu-id="7acba-129">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="7acba-130">收件人永远不会看到实际的邮件信封，因为它是由邮件传输过程生成的，实际上并不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="7acba-130">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="7acba-131">地址 `5321.MailFrom` (**MAIL FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7acba-131">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="7acba-132">虽然发件人可以指定不同的"返回路径"电子邮件地址 (但此电子邮件地址通常记录在邮件头的"返回路径") 。 </span><span class="sxs-lookup"><span data-stu-id="7acba-132">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="7acba-133">如果邮件无法传递，则它是未送达报告的收件人 (NDR 或退回邮件) 。</span><span class="sxs-lookup"><span data-stu-id="7acba-133">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="7acba-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field， and is the sender's email address that's displayed in email clients.</span><span class="sxs-lookup"><span data-stu-id="7acba-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="7acba-135">通常， `5321.MailFrom` 和 `5322.From` 地址在个人 (通信中) 。</span><span class="sxs-lookup"><span data-stu-id="7acba-135">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="7acba-136">但是，代表其他人发送电子邮件时，地址可以不同。</span><span class="sxs-lookup"><span data-stu-id="7acba-136">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="7acba-137">EOP 中的反垃圾邮件策略中阻止的发件人列表和阻止的域列表将检查 `5321.MailFrom` 和 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="7acba-137">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="7acba-138">Outlook阻止的发件人仅使用 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="7acba-138">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="7acba-139">使用Outlook阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="7acba-139">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="7acba-140">当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中的"阻止的发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="7acba-140">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="7acba-141">有关说明，请参阅[在邮箱上配置Exchange Online设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="7acba-141">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="7acba-142">当用户的阻止的发件人名单成功阻止邮件时 **，X-Forefront-Antispam-Report** 头字段将包含值 `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="7acba-142">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="7acba-143">如果不需要的邮件来自信誉良好且可识别的来源，则取消订阅电子邮件是阻止用户接收邮件的另一个选项。</span><span class="sxs-lookup"><span data-stu-id="7acba-143">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="7acba-144">使用阻止的发件人列表或阻止的域列表</span><span class="sxs-lookup"><span data-stu-id="7acba-144">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="7acba-145">当多个用户受到影响时，范围会更大，因此反垃圾邮件策略中的下一个最佳选项是阻止发件人列表或阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="7acba-145">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="7acba-146">来自列表上发件人的邮件标记为 **"高** 可信度垃圾邮件"，并且对邮件执行为"高可信度垃圾邮件筛选器"裁定配置的操作。</span><span class="sxs-lookup"><span data-stu-id="7acba-146">Messages from senders on the lists are marked as **High confidence spam**, and the action that you've configured for the **High confidence spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="7acba-147">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7acba-147">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="7acba-148">这些列表的最大限制为大约 1000 个条目。</span><span class="sxs-lookup"><span data-stu-id="7acba-148">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="7acba-149">使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="7acba-149">Use mail flow rules</span></span>

<span data-ttu-id="7acba-150">如果需要阻止发送给特定用户或整个组织的邮件，可以使用邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="7acba-150">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="7acba-151">邮件流规则比阻止发件人列表或阻止发件人域列表更灵活，因为它们还可以在不需要的邮件中查找关键字或其他属性。</span><span class="sxs-lookup"><span data-stu-id="7acba-151">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="7acba-152">不论您用于标识邮件的条件或例外如何，您都将操作配置为将邮件的垃圾邮件可信度 (SCL) 设置为 9，从而将邮件标记为高可信度 **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="7acba-152">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="7acba-153">有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="7acba-153">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7acba-154">创建过于主动的规则很容易，因此使用非常具体的条件仅标识要阻止的邮件非常重要。</span><span class="sxs-lookup"><span data-stu-id="7acba-154">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="7acba-155">此外，请务必对规则启用审核并测试规则结果，以确保一切正常。</span><span class="sxs-lookup"><span data-stu-id="7acba-155">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="7acba-156">使用 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="7acba-156">Use the IP Block List</span></span>

<span data-ttu-id="7acba-157">当无法使用其他选项之一阻止发件人时，只有在连接筛选器策略中才应该使用 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="7acba-157">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="7acba-158">有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="7acba-158">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="7acba-159">将阻止的 IP 数量保持在最少很重要，因此不建议阻止整个 IP *地址范围。*</span><span class="sxs-lookup"><span data-stu-id="7acba-159">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="7acba-160">您尤其应避免添加属于消费者服务 (（例如 outlook.com) 或共享基础结构）的 IP 地址范围，并确保在常规维护中查看阻止的 IP 地址列表。</span><span class="sxs-lookup"><span data-stu-id="7acba-160">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
