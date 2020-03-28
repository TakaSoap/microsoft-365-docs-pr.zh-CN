---
title: 在 Office 365 中创建阻止的发件人列表
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
- MET150s
description: 管理员可以了解 Office 365 和 EOP 中的可用选项来阻止入站邮件。
ms.openlocfilehash: 0bfab3024bc781e53600092ebc88fae25c5f4afc
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033418"
---
# <a name="create-blocked-sender-lists-in-office-365"></a><span data-ttu-id="70580-103">在 Office 365 中创建阻止的发件人列表</span><span class="sxs-lookup"><span data-stu-id="70580-103">Create blocked sender lists in Office 365</span></span>

<span data-ttu-id="70580-104">如果您是在 Exchange Online 中使用邮箱的 Office 365 客户或没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）客户，则 EOP 提供多种阻止来自不需要的发件人的电子邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="70580-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="70580-105">这些选项包括 Outlook 阻止的发件人、阻止的发件人列表或反垃圾邮件策略中阻止的域列表、Exchange 邮件流规则（也称为传输规则）和 IP 阻止列表（连接筛选）。</span><span class="sxs-lookup"><span data-stu-id="70580-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="70580-106">你可以将这些选项统称为阻止的_发件人列表_。</span><span class="sxs-lookup"><span data-stu-id="70580-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="70580-107">阻止发件人的最佳方法因影响范围而异。</span><span class="sxs-lookup"><span data-stu-id="70580-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="70580-108">对于单个用户，正确的解决方案可能是 Outlook 阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="70580-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="70580-109">对于很多用户而言，其他选项中的一种更合适。</span><span class="sxs-lookup"><span data-stu-id="70580-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="70580-110">下面的选项按影响范围和广度进行排序。</span><span class="sxs-lookup"><span data-stu-id="70580-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="70580-111">列表从窄到范围，但阅读完整建议的*细节*。</span><span class="sxs-lookup"><span data-stu-id="70580-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="70580-112">Outlook 阻止的发件人（存储在每个邮箱中的阻止发件人列表）</span><span class="sxs-lookup"><span data-stu-id="70580-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="70580-113">阻止的发件人列表或阻止的域列表（反垃圾邮件策略）</span><span class="sxs-lookup"><span data-stu-id="70580-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="70580-114">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="70580-114">Mail flow rules</span></span>

4. <span data-ttu-id="70580-115">IP 阻止列表（连接筛选）</span><span class="sxs-lookup"><span data-stu-id="70580-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="70580-116">虽然您可以使用组织范围内的阻止设置来解决漏报（丢失的垃圾邮件），但还应将这些邮件提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="70580-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="70580-117">使用阻止列表管理漏报会显著增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="70580-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="70580-118">如果使用阻止列表转移丢失的垃圾邮件，则需要将主题[报告邮件和文件](report-junk-email-messages-to-microsoft.md)保留在 Microsoft 准备就绪。</span><span class="sxs-lookup"><span data-stu-id="70580-118">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="70580-119">相比之下，您还可以使用多个选项始终允许使用_安全发件人列表_从特定来源发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="70580-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="70580-120">有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="70580-120">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="70580-121">使用 Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="70580-121">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="70580-122">当只有少量用户收到不需要的电子邮件时，用户或管理员可以将发件人电子邮件地址添加到邮箱中阻止的发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="70580-122">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="70580-123">有关说明，请参阅在[Office 365 中的 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="70580-123">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="70580-124">当邮件由于用户的阻止发件人列表而成功被阻止时， **X-Forefront-反垃圾邮件报告**的标头字段`SFV:BLK`将包含该值。</span><span class="sxs-lookup"><span data-stu-id="70580-124">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="70580-125">如果不需要的邮件是来自可信且可识别的来源的新闻快递，则取消对该电子邮件的订阅是阻止用户接收邮件的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="70580-125">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="70580-126">使用阻止的发件人列表或阻止的域列表</span><span class="sxs-lookup"><span data-stu-id="70580-126">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="70580-127">当多个用户受到影响时，范围将变宽，因此下一个最佳选项是在反垃圾邮件策略中阻止发件人列表或阻止的域列表。</span><span class="sxs-lookup"><span data-stu-id="70580-127">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="70580-128">来自列表中发件人的邮件被标记为**垃圾**邮件，而您为**垃圾邮件**筛选器判定配置的操作将在邮件上执行。</span><span class="sxs-lookup"><span data-stu-id="70580-128">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="70580-129">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70580-129">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="70580-130">这些列表的最大限制约为1000个条目;尽管只能将30个条目输入到门户中。</span><span class="sxs-lookup"><span data-stu-id="70580-130">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="70580-131">您需要使用 PowerShell 来添加30个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="70580-131">You need to use PowerShell to add more than 30 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="70580-132">使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="70580-132">Use mail flow rules</span></span>

<span data-ttu-id="70580-133">如果需要阻止发送到特定用户或整个组织中的邮件，则可以使用邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="70580-133">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="70580-134">邮件流规则比阻止发件人列表或阻止的发件人域列表更灵活，因为它们还可以查找不需要的邮件中的关键字或其他属性。</span><span class="sxs-lookup"><span data-stu-id="70580-134">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="70580-135">无论您用于标识邮件的条件或例外情况如何，都可以将操作配置为将邮件的垃圾邮件可信度（SCL）设置为9，这会将邮件标记为**高可信度垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="70580-135">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="70580-136">有关详细信息，请参阅[使用邮件流规则设置邮件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="70580-136">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70580-137">很容易创建规则*过于*积极的规则，因此，只需使用非常具体的条件来确定要阻止的邮件，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="70580-137">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="70580-138">此外，请务必对规则启用审核并测试规则的结果，以确保一切按预期工作。</span><span class="sxs-lookup"><span data-stu-id="70580-138">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="70580-139">使用 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="70580-139">Use the IP Block List</span></span>

<span data-ttu-id="70580-140">如果不能使用其他选项之一来阻止发件人，则*只有*在连接筛选器策略中使用 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="70580-140">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="70580-141">有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="70580-141">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="70580-142">一定要将阻止的 Ip 的数量保持为最小值，以便*不*建议阻止整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="70580-142">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="70580-143">您应该*特别*避免添加属于消费者服务（例如，outlook.com）或共享基础结构的 ip 地址范围，还应确保在定期维护过程中查看被阻止的 IP 地址的列表。</span><span class="sxs-lookup"><span data-stu-id="70580-143">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
