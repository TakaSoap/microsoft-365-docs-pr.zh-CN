---
title: 创建安全发件人列表
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
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解允许 Exchange Online Protection 中的入站邮件的可用和首选 (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ddcd6240cfc80350920999f9fc1e8ea188834553
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289707"
---
# <a name="create-safe-sender-lists-in-eop"></a><span data-ttu-id="41883-103">在 EOP 中创建安全发件人列表</span><span class="sxs-lookup"><span data-stu-id="41883-103">Create safe sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41883-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="41883-104">**Applies to**</span></span>
- [<span data-ttu-id="41883-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41883-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41883-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="41883-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="41883-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41883-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="41883-108">如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者是没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，则 EOP 提供了多种确保用户将接收来自受信任发件人的电子邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="41883-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of ensuring that users will receive email from trusted senders.</span></span> <span data-ttu-id="41883-109">这些选项包括 Exchange 邮件流规则 (也称为传输规则) 、Outlook 安全发件人、IP 允许列表 (连接筛选) 以及反垃圾邮件策略中允许的发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="41883-109">These options include Exchange mail flow rules (also known as transport rules), Outlook Safe Senders, the IP Allow List (connection filtering), and allowed sender lists or allowed domain lists in anti-spam policies.</span></span> <span data-ttu-id="41883-110">统一来说，你可以将这些选项视为 _安全发件人列表_。</span><span class="sxs-lookup"><span data-stu-id="41883-110">Collectively, you can think of these options as _safe sender lists_.</span></span>

<span data-ttu-id="41883-111">以下列表中介绍了可用的安全发件人列表，顺序从建议最多到建议最少：</span><span class="sxs-lookup"><span data-stu-id="41883-111">The available safe sender lists are described in the following list in order from most recommended to least recommended:</span></span>

1. <span data-ttu-id="41883-112">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="41883-112">Mail flow rules</span></span>
2. <span data-ttu-id="41883-113">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="41883-113">Outlook Safe Senders</span></span>
3. <span data-ttu-id="41883-114">IP 允许列表 (连接筛选) </span><span class="sxs-lookup"><span data-stu-id="41883-114">IP Allow List (connection filtering)</span></span>
4. <span data-ttu-id="41883-115">允许的发件人列表或允许的域 (反垃圾邮件策略) </span><span class="sxs-lookup"><span data-stu-id="41883-115">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>

<span data-ttu-id="41883-116">邮件流规则允许最灵活地确保仅允许正确的邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-116">Mail flow rules allow the most flexibility to ensure that only the right messages are allowed.</span></span> <span data-ttu-id="41883-117">反垃圾邮件策略中允许的发件人和允许的域列表没有 IP 允许列表安全，因为发件人的电子邮件域很容易被欺骗。</span><span class="sxs-lookup"><span data-stu-id="41883-117">Allowed sender and allowed domain lists in anti-spam policies aren't as secure as the IP Allow List, because the sender's email domain is easily spoofed.</span></span> <span data-ttu-id="41883-118">但是，IP 允许列表也带来风险，因为从该 IP地址发送的任何域的电子邮件将绕过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="41883-118">But, the IP Allow List also presents a risk, because email from _any_ domain that's sent from that IP address will bypass spam filtering.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="41883-119">请务必密切监视 *对* 使用安全发件人列表进行垃圾邮件筛选的任何异常。</span><span class="sxs-lookup"><span data-stu-id="41883-119">Be careful to closely monitor *any* exceptions that you make to spam filtering using safe sender lists.</span></span>
>
> - <span data-ttu-id="41883-120">虽然可以使用安全发件人列表来帮助处理误报 (标记为错误) 的优秀电子邮件，但您应考虑使用安全发件人列表作为临时解决方案，如果可能，应避免使用安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="41883-120">While you can use safe sender lists to help with false positives (good email marked as bad), you should consider the use of safe sender lists as a temporary solution that should be avoided if possible.</span></span> <span data-ttu-id="41883-121">我们不建议使用安全发件人列表管理误报，因为垃圾邮件筛选的例外情况可能会使组织遭受欺骗和其他攻击。</span><span class="sxs-lookup"><span data-stu-id="41883-121">We don't recommend managing false positives by using safe sender lists, because exceptions to spam filtering can open your organization to spoofing and other attacks.</span></span> <span data-ttu-id="41883-122">如果你坚持使用安全发件人列表来管理误报，你需要谨慎操作，并准备好将主题"将邮件和文件报告给[Microsoft"。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="41883-122">If you insist on using safe sender lists to manage false positives, you need to be vigilant and keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>
>
> - <span data-ttu-id="41883-123">若要允许域发送未经身份验证的电子邮件 (绕过反欺骗保护) 但不绕过反垃圾邮件和反恶意软件检查，可以将其添加到[AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)安全发件人列表</span><span class="sxs-lookup"><span data-stu-id="41883-123">To allow a domain to send unauthenticated email (bypass anti-spoofing protection) but not bypass anti-spam and anti-malware checks, you can add it to the [AllowedToSpoof safe sender list](walkthrough-spoof-intelligence-insight.md)</span></span>
>
> - <span data-ttu-id="41883-124">EOP 和 Outlook 检查不同的邮件属性以确定邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="41883-124">EOP and Outlook inspect different message properties to determine the sender of the message.</span></span> <span data-ttu-id="41883-125">有关详细信息，请参阅本文稍后的[](#considerations-for-bulk-email)"批量电子邮件的注意事项"部分。</span><span class="sxs-lookup"><span data-stu-id="41883-125">For more information, see the [Considerations for bulk email](#considerations-for-bulk-email) section later in this article.</span></span>

<span data-ttu-id="41883-126">相比之下，您还可以使用阻止的发件人列表阻止来自特定源 _的电子邮件_。</span><span class="sxs-lookup"><span data-stu-id="41883-126">In contrast, you also have several options to block email from specific sources using _blocked sender lists_.</span></span> <span data-ttu-id="41883-127">有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-127">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="recommended-use-mail-flow-rules"></a><span data-ttu-id="41883-128"> (建议) 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="41883-128">(Recommended) Use mail flow rules</span></span>

<span data-ttu-id="41883-129">Exchange Online 和独立 EOP 中的邮件流规则使用条件和例外来标识邮件，以及用于指定应针对这些邮件执行哪些操作的操作。</span><span class="sxs-lookup"><span data-stu-id="41883-129">Mail flow rules in Exchange Online and standalone EOP use conditions and exceptions to identify messages, and actions to specify what should be done to those messages.</span></span> <span data-ttu-id="41883-130">有关详细信息，请参阅 Exchange Online 中的 ([传输) 规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="41883-130">For more information, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>

<span data-ttu-id="41883-131">以下示例假定您需要来自 contoso.com 的电子邮件来跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="41883-131">The following example assumes you need email from contoso.com to skip spam filtering.</span></span> <span data-ttu-id="41883-132">为此，请配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="41883-132">To do this, configure the following settings:</span></span>

1. <span data-ttu-id="41883-133">**条件**：**发件人** \> **域contoso.com。** \></span><span class="sxs-lookup"><span data-stu-id="41883-133">**Condition**: **The sender** \> **domain is** \> contoso.com.</span></span>

2. <span data-ttu-id="41883-134">配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="41883-134">Configure either of the following settings:</span></span>

   - <span data-ttu-id="41883-135">**邮件流规则条件**： **邮件头包含** \> **以下任何** 词语： \> **邮件** 头名称： `Authentication-Results` \> **邮件头值**： `dmarc=pass` 或 `dmarc=bestguesspass` 。</span><span class="sxs-lookup"><span data-stu-id="41883-135">**Mail flow rule condition**: **A message header** \> **includes any of these words** \> **Header name**: `Authentication-Results` \> **Header value**: `dmarc=pass` or `dmarc=bestguesspass`.</span></span>

     <span data-ttu-id="41883-136">此条件检查发送电子邮件域的电子邮件身份验证状态，以确保发送域未遭到欺骗。</span><span class="sxs-lookup"><span data-stu-id="41883-136">This condition checks the email authentication status of the sending email domain to ensure that the sending domain is not being spoofed.</span></span> <span data-ttu-id="41883-137">有关电子邮件身份验证详细信息，请参阅[SPF、DKIM](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[DMARC。](use-dmarc-to-validate-email.md) [](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="41883-137">For more information about email authentication, see [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

   - <span data-ttu-id="41883-138">**IP 允许列表**：在连接筛选器策略中指定源 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="41883-138">**IP Allow List**: Specify the source IP address or address range in the connection filter policy.</span></span>

     <span data-ttu-id="41883-139">如果发送域不使用电子邮件身份验证，则使用此设置。</span><span class="sxs-lookup"><span data-stu-id="41883-139">Use this setting if the sending domain does not use email authentication.</span></span> <span data-ttu-id="41883-140">当涉及 IP 允许列表中的源 IP 地址时，尽量严格。</span><span class="sxs-lookup"><span data-stu-id="41883-140">Be as restrictive as possible when it comes to the source IP addresses in the IP Allow List.</span></span> <span data-ttu-id="41883-141">我们建议 IP 地址范围为 /24 或更少 (是更好的) 。</span><span class="sxs-lookup"><span data-stu-id="41883-141">We recommend an IP address range of /24 or less (less is better).</span></span> <span data-ttu-id="41883-142">请勿使用属于使用者服务的 IP 地址范围 (例如，outlook.com) 或共享基础结构。</span><span class="sxs-lookup"><span data-stu-id="41883-142">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

   > [!IMPORTANT]
   >
   > - <span data-ttu-id="41883-143">永远不要将 *仅发件人域* 配置为跳过垃圾邮件筛选的条件来配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="41883-143">Never configure mail flow rules with *only* the sender domain as the condition to skip spam filtering.</span></span> <span data-ttu-id="41883-144">这样做将显著增加攻击者欺骗发送域 (或模拟完整电子邮件地址) 、跳过所有垃圾邮件筛选和跳过发件人身份验证检查以便邮件到达收件人收件箱的可能性。</span><span class="sxs-lookup"><span data-stu-id="41883-144">Doing so will *significantly* increase the likelihood that attackers can spoof the sending domain (or impersonate the full email address), skip all spam filtering, and skip sender authentication checks so the message will arrive in the recipient's Inbox.</span></span>
   >
   > - <span data-ttu-id="41883-145">请勿将你拥有 (域或) 域或热门 (，例如，microsoft.com) 规则中的条件。</span><span class="sxs-lookup"><span data-stu-id="41883-145">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) as conditions in mail flow rules.</span></span> <span data-ttu-id="41883-146">这样做被视为高风险，因为它会为攻击者创造机会来发送电子邮件，否则会进行筛选。</span><span class="sxs-lookup"><span data-stu-id="41883-146">Doing so is considered high risk because it creates opportunities for attackers to send email that would otherwise be filtered.</span></span>
   >
   > - <span data-ttu-id="41883-147">如果允许网络地址转换 (NAT) 网关后面的 IP 地址，则需要知道 NAT 池中涉及的服务器，才能知道 IP 允许列表的范围。</span><span class="sxs-lookup"><span data-stu-id="41883-147">If you allow an IP address that's behind a network address translation (NAT) gateway, you need to know the servers that are involved in the NAT pool in order to know the scope of your IP Allow List.</span></span> <span data-ttu-id="41883-148">IP 地址和 NAT 参与者可能会更改。</span><span class="sxs-lookup"><span data-stu-id="41883-148">IP addresses and NAT participants can change.</span></span> <span data-ttu-id="41883-149">作为标准维护过程一部分，需要定期检查 IP 允许列表条目。</span><span class="sxs-lookup"><span data-stu-id="41883-149">You need to periodically check your IP Allow List entries as part of your standard maintenance procedures.</span></span>

3. <span data-ttu-id="41883-150">**可选条件**：</span><span class="sxs-lookup"><span data-stu-id="41883-150">**Optional conditions**:</span></span>

   - <span data-ttu-id="41883-151">**发件人** \>**是内部/外部** \>**组织外部**：此条件是隐式的，但可以使用它来考虑可能未正确配置本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="41883-151">**The sender** \> **is internal/external** \> **Outside the organization**: This condition is implicit, but it's OK to use it to account for on-premises email servers that might not be correctly configured.</span></span>

   - <span data-ttu-id="41883-152">**主题或正文** \>**主题或正文包含以下任何词语** \>：如果可以通过主题行或邮件正文中的关键字或短语进一步限制邮件，可以使用这些词 \<keywords\> 作为条件。</span><span class="sxs-lookup"><span data-stu-id="41883-152">**The subject or body** \> **subject or body includes any of these words** \> \<keywords\>: If you can further restrict the messages by keywords or phrases in the subject line or message body, you can use those words as a condition.</span></span>

4. <span data-ttu-id="41883-153">**操作**：在规则中配置这两个操作：</span><span class="sxs-lookup"><span data-stu-id="41883-153">**Action**: Configure both of these actions in the rule:</span></span>

   <span data-ttu-id="41883-154">a.</span><span class="sxs-lookup"><span data-stu-id="41883-154">a.</span></span> <span data-ttu-id="41883-155">**修改邮件属性** \>**将垃圾邮件可信度设置为 (SCL)** \>**绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="41883-155">**Modify the message properties** \> **set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

   <span data-ttu-id="41883-156">b.</span><span class="sxs-lookup"><span data-stu-id="41883-156">b.</span></span> <span data-ttu-id="41883-157">**修改邮件属性** \>**设置邮件头**：**将邮件头** \<CustomHeaderName\> **设置为值** \<CustomHeaderValue\> 。</span><span class="sxs-lookup"><span data-stu-id="41883-157">**Modify the message properties** \> **set a message header**: **Set the message header** \<CustomHeaderName\> **to the value** \<CustomHeaderValue\>.</span></span>

      <span data-ttu-id="41883-158">例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。</span><span class="sxs-lookup"><span data-stu-id="41883-158">For example, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`.</span></span> <span data-ttu-id="41883-159">如果规则中具有多个域，您可以根据需要自定义标题文本。</span><span class="sxs-lookup"><span data-stu-id="41883-159">If you have more than one domain in the rule, you can customize the header text as appropriate.</span></span>

      <span data-ttu-id="41883-160">当邮件由于邮件流规则而跳过垃圾邮件筛选时，值值将标记在 `SFV:SKN` **X-Forefront-Antispam-Report 标头** 中。</span><span class="sxs-lookup"><span data-stu-id="41883-160">When a message skips spam filtering due to a mail flow rule, the value `SFV:SKN` value is stamped in the **X-Forefront-Antispam-Report** header.</span></span> <span data-ttu-id="41883-161">如果邮件来自 IP 允许列表上的源，则也会 `IPV:CAL` 添加该值。</span><span class="sxs-lookup"><span data-stu-id="41883-161">If the message is from a source that's on the IP Allow List, the value `IPV:CAL` is also added.</span></span> <span data-ttu-id="41883-162">这些值可以帮助你进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="41883-162">These values can help you with troubleshooting.</span></span>

![EAC 中用于绕过垃圾邮件筛选的邮件流规则设置。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a><span data-ttu-id="41883-164">使用 Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="41883-164">Use Outlook Safe Senders</span></span>

> [!CAUTION]
> <span data-ttu-id="41883-165">此方法会为攻击者成功将电子邮件成功发送到收件箱带来高风险，否则会进行筛选;但是，用户的"安全发件人"或"安全域"列表不会阻止筛选恶意软件或高可信度网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-165">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the user's Safe Senders or Safe Domains lists don't prevent malware or high confidence phishing messages from being filtered.</span></span>

<span data-ttu-id="41883-166">用户或管理员可以将发件人电子邮件地址添加到邮箱中的"安全发件人"列表中，而不是组织设置。</span><span class="sxs-lookup"><span data-stu-id="41883-166">Instead of an organizational setting, users or admins can add the sender email addresses to the Safe Senders list in the mailbox.</span></span> <span data-ttu-id="41883-167">有关说明，请参阅 [在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-167">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span> <span data-ttu-id="41883-168">在大多数情况下，这是不可取的，因为发件人将绕过筛选堆栈的某些部分。</span><span class="sxs-lookup"><span data-stu-id="41883-168">This is not desirable in most situations since senders will bypass parts of the filtering stack.</span></span> <span data-ttu-id="41883-169">虽然您信任发件人，但发件人仍可能会遭到入侵并发送恶意内容。</span><span class="sxs-lookup"><span data-stu-id="41883-169">Although you trust the sender, the sender can still be compromised and send malicious content.</span></span> <span data-ttu-id="41883-170">最好让筛选器执行检查每封邮件所需的操作，然后在筛选器出错时向 Microsoft 报告误报 [/](report-junk-email-messages-to-microsoft.md) 负数。</span><span class="sxs-lookup"><span data-stu-id="41883-170">It is best that you let our filters do what is needed to check every message and then [report the false positive/negative to Microsoft](report-junk-email-messages-to-microsoft.md) if our filters got it wrong.</span></span> <span data-ttu-id="41883-171">绕过筛选堆栈也会干扰[ZAP。](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="41883-171">Bypassing the filtering stack also interferes with [ZAP](zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="41883-172">当邮件由于用户的安全发件人列表而跳过垃圾邮件筛选时 **，X-Forefront-Antispam-Report** 头字段将包含值，该值指示已绕过对垃圾邮件、欺骗和网络钓鱼的筛选。 `SFV:SFE`</span><span class="sxs-lookup"><span data-stu-id="41883-172">When messages skip spam filtering due to a user's Safe Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:SFE`, which indicates that filtering for spam, spoof, and phishing were bypassed.</span></span>

## <a name="use-the-ip-allow-list"></a><span data-ttu-id="41883-173">使用 IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="41883-173">Use the IP Allow List</span></span>

<span data-ttu-id="41883-174">如果无法按前面所述使用邮件流规则，则下一个最佳选项是向连接筛选器策略中的 IP 允许列表添加源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="41883-174">If you can't use mail flow rules as previously described, the next best option is to add the source email server or servers to the IP Allow List in the connection filter policy.</span></span> <span data-ttu-id="41883-175">有关详细信息，请参阅["在 EOP 中配置连接筛选"。](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="41883-175">For details, see [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

<span data-ttu-id="41883-176">**注意**：</span><span class="sxs-lookup"><span data-stu-id="41883-176">**Notes**:</span></span>

- <span data-ttu-id="41883-177">将允许的 IP 地址数保持在最少，这一点很重要，因此尽可能避免使用整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="41883-177">It's important that you keep the number of allowed IP addresses to a minimum, so avoid using entire IP address ranges whenever possible.</span></span>

- <span data-ttu-id="41883-178">请勿使用属于使用者服务的 IP 地址范围 (例如，outlook.com) 或共享基础结构。</span><span class="sxs-lookup"><span data-stu-id="41883-178">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

- <span data-ttu-id="41883-179">定期查看 IP 允许列表中的条目并删除不再需要的条目。</span><span class="sxs-lookup"><span data-stu-id="41883-179">Regularly review the entries in the IP Allow List and remove the entries that you no longer need.</span></span>

> [!CAUTION]
> <span data-ttu-id="41883-180">如果没有其他验证（如邮件流规则），来自 IP 允许列表中的源的电子邮件将跳过 SPF、DKIM、DMARC (垃圾邮件筛选和发件人身份验证) 检查。</span><span class="sxs-lookup"><span data-stu-id="41883-180">Without additional verification like mail flow rules, email from sources in the IP Allow List skips spam filtering and sender authentication (SPF, DKIM, DMARC) checks.</span></span> <span data-ttu-id="41883-181">这将存在攻击者成功将电子邮件发送到收件箱（否则会进行筛选）的高风险;但是，IP 允许列表不会阻止筛选恶意软件或高可信度网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-181">This creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the IP Allow List doesn't prevent malware or high confidence phishing messages from being filtered.</span></span>

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a><span data-ttu-id="41883-182">使用允许的发件人列表或允许的域列表</span><span class="sxs-lookup"><span data-stu-id="41883-182">Use allowed sender lists or allowed domain lists</span></span>

<span data-ttu-id="41883-183">最不可取的选项是在反垃圾邮件策略中使用允许的发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="41883-183">The least desirable option is to use the allowed sender list or allowed domain list in anti-spam policies.</span></span> <span data-ttu-id="41883-184">如果可能，应尽量避免使用此选项，因为发件人绕过所有垃圾邮件、欺骗和网络钓鱼保护，以及发件人身份验证 (SPF、DKIM、DMARC) 。</span><span class="sxs-lookup"><span data-stu-id="41883-184">You should avoid this option *if at all possible* because senders bypass all spam, spoof, and phishing protection, and sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="41883-185">此方法最好仅用于临时测试。</span><span class="sxs-lookup"><span data-stu-id="41883-185">This method is best used for temporary testing only.</span></span> <span data-ttu-id="41883-186">可以在 EOP 主题中的 ["配置反垃圾邮件策略"中找到详细](configure-your-spam-filter-policies.md) 步骤。</span><span class="sxs-lookup"><span data-stu-id="41883-186">The detailed steps can be found in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.</span></span>

<span data-ttu-id="41883-187">这些列表的最大限制为大约 1000 个条目;但是，你只能向门户输入 30 个条目。</span><span class="sxs-lookup"><span data-stu-id="41883-187">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="41883-188">必须使用 PowerShell 添加 30 多个条目。</span><span class="sxs-lookup"><span data-stu-id="41883-188">You must use PowerShell to add more than 30 entries.</span></span>

> [!CAUTION]
>
> - <span data-ttu-id="41883-189">此方法会为攻击者成功将电子邮件成功发送到收件箱带来高风险，否则会进行筛选;但是，允许的发件人或允许的域列表不会阻止筛选恶意软件或高可信度网络钓鱼混乱。</span><span class="sxs-lookup"><span data-stu-id="41883-189">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the allowed senders or allowed domains lists don't prevent malware or high confidence phishing messsages from being filtered.</span></span>
>
> - <span data-ttu-id="41883-190">请勿使用你拥有 (也称为接受) 域或常用 (，例如microsoft.com) 域中的域。</span><span class="sxs-lookup"><span data-stu-id="41883-190">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) in allowed domain lists.</span></span>

## <a name="considerations-for-bulk-email"></a><span data-ttu-id="41883-191">批量电子邮件的注意事项</span><span class="sxs-lookup"><span data-stu-id="41883-191">Considerations for bulk email</span></span>

<span data-ttu-id="41883-192">标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="41883-192">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="41883-193">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="41883-193">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="41883-194">邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="41883-194">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="41883-195">RFC 5321 中描述了邮件信封，RFC 5322 中描述了邮件头。</span><span class="sxs-lookup"><span data-stu-id="41883-195">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="41883-196">收件人永远不会看到实际的邮件信封，因为它由邮件传输进程生成，并且实际上不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="41883-196">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="41883-197">地址 (MAIL `5321.MailFrom` **FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="41883-197">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="41883-198">虽然发件人可以指定不同的返回路径电子邮件地址，但此电子邮件地址通常记录在邮件头 (的"返回路径"头字段中) 。 </span><span class="sxs-lookup"><span data-stu-id="41883-198">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="41883-199">如果邮件无法传递，则它是未送达报告的收件人 (也称为 NDR 或退回邮件) 。</span><span class="sxs-lookup"><span data-stu-id="41883-199">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="41883-200">该 (也称为发件人地址或 P2 发件人) 是"发件人"头字段中的电子邮件地址，是电子邮件客户端中显示的发件人 `5322.From` 电子邮件地址。  </span><span class="sxs-lookup"><span data-stu-id="41883-200">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="41883-201">通常， `5321.MailFrom` 地址 `5322.From` 和地址 (人员之间的通信) 。</span><span class="sxs-lookup"><span data-stu-id="41883-201">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="41883-202">但是，当代表其他人发送电子邮件时，地址可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="41883-202">However, when email is sent on behalf of someone else, the addresses can be different.</span></span> <span data-ttu-id="41883-203">这通常发生在批量电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="41883-203">This happens most often for bulk email messages.</span></span>

<span data-ttu-id="41883-204">例如，假设 Blue Yonder Airlines 雇用玛吉旅行社发送其电子邮件广告。</span><span class="sxs-lookup"><span data-stu-id="41883-204">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="41883-205">在收件箱中收到的邮件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="41883-205">The message you receive in your Inbox has the following properties:</span></span>

- <span data-ttu-id="41883-206">地址 `5321.MailFrom` blueyonder.airlines@margiestravel.com。</span><span class="sxs-lookup"><span data-stu-id="41883-206">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="41883-207">地址 `5322.From` 是blueyonder@news.blueyonderairlines.com，你将在 Outlook 中看到该地址。</span><span class="sxs-lookup"><span data-stu-id="41883-207">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="41883-208">EOP 中的反垃圾邮件策略中的安全发件人列表和安全域列表仅检查地址，这类似于使用该地址的 `5322.From` Outlook 安全 `5322.From` 发件人。</span><span class="sxs-lookup"><span data-stu-id="41883-208">Safe sender lists and safe domain lists in anti-spam policies in EOP inspect only the `5322.From` addresses, this is similar to Outlook Safe Senders that uses the `5322.From` address.</span></span>

<span data-ttu-id="41883-209">若要阻止筛选此消息，可以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="41883-209">To prevent this message from being filtered, you can take the following steps:</span></span>

- <span data-ttu-id="41883-210">将blueyonder@news.blueyonderairlines.com (`5322.From` 添加) Outlook 安全发件人。</span><span class="sxs-lookup"><span data-stu-id="41883-210">Add blueyonder@news.blueyonderairlines.com (the `5322.From` address) as an Outlook Safe Sender.</span></span>

- <span data-ttu-id="41883-211">[将邮件流规则](#recommended-use-mail-flow-rules) 与以下条件一同使用：从地址blueyonder@news.blueyonderairlines.com (邮件、blueyonder.airlines@margiestravel.com (或) `5322.From` `5321.MailFrom` 邮件。</span><span class="sxs-lookup"><span data-stu-id="41883-211">[Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`), or both.</span></span>

<span data-ttu-id="41883-212">有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="41883-212">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>
