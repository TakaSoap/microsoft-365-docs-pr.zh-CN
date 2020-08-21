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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection 和 EOP 应用程序中允许入站邮件的可用 () 选项。
ms.openlocfilehash: f182027b153ee73e33131b39066e512c9303fcbd
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827107"
---
# <a name="create-safe-sender-lists-in-eop"></a><span data-ttu-id="99752-103">在 EOP 中创建安全发件人列表</span><span class="sxs-lookup"><span data-stu-id="99752-103">Create safe sender lists in EOP</span></span>

<span data-ttu-id="99752-104">如果你是具有 Exchange Online 邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，EOP 提供了多种方法来确保用户将收到来自受信任发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="99752-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of ensuring that users will receive email from trusted senders.</span></span> <span data-ttu-id="99752-105">这些选项包括 Exchange 邮件流规则 (也称为传输规则) 、Outlook 安全发件人、IP 允许列表 (连接筛选) ，以及反垃圾邮件策略中的允许发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="99752-105">These options include Exchange mail flow rules (also known as transport rules), Outlook Safe Senders, the IP Allow List (connection filtering), and allowed sender lists or allowed domain lists in anti-spam policies.</span></span> <span data-ttu-id="99752-106">总的来说，可以将这些选项视为安全 _发件人列表_。</span><span class="sxs-lookup"><span data-stu-id="99752-106">Collectively, you can think of these options as _safe sender lists_.</span></span>

<span data-ttu-id="99752-107">以下列表中的可用安全发件人列表按建议从推荐最不推荐到最不推荐的顺序进行介绍：</span><span class="sxs-lookup"><span data-stu-id="99752-107">The available safe sender lists are described in the following list in order from most recommended to least recommended:</span></span>

1. <span data-ttu-id="99752-108">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="99752-108">Mail flow rules</span></span>
2. <span data-ttu-id="99752-109">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="99752-109">Outlook Safe Senders</span></span>
3. <span data-ttu-id="99752-110">IP 允许 (筛选) </span><span class="sxs-lookup"><span data-stu-id="99752-110">IP Allow List (connection filtering)</span></span>
4. <span data-ttu-id="99752-111">反垃圾邮件策略的允许发件人列表或允许的 (域) </span><span class="sxs-lookup"><span data-stu-id="99752-111">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>

<span data-ttu-id="99752-112">邮件流规则使灵活性最高的可确保只允许正确的邮件。</span><span class="sxs-lookup"><span data-stu-id="99752-112">Mail flow rules allow the most flexibility to ensure that only the right messages are allowed.</span></span> <span data-ttu-id="99752-113">反垃圾邮件策略中的允许发件人和允许的域列表不如 IP 允许列表一起使用，因为发件人的电子邮件域易受到欺骗性的原因。</span><span class="sxs-lookup"><span data-stu-id="99752-113">Allowed sender and allowed domain lists in anti-spam policies aren't as secure as the IP Allow List, because the sender's email domain is easily spoofed.</span></span> <span data-ttu-id="99752-114">但是，IP 允许列表还会带来风险，因为来自任何域_any_并来自该 IP 地址的电子邮件都将不进行垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="99752-114">But, the IP Allow List also presents a risk, because email from _any_ domain that's sent from that IP address will bypass spam filtering.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="99752-115">请注意，应使用安全发件人列表 *密* 大监控垃圾邮件筛选的异常。</span><span class="sxs-lookup"><span data-stu-id="99752-115">Be careful to closely monitor *any* exceptions that you to spam filtering using safe sender lists.</span></span>
>
> - <span data-ttu-id="99752-116">虽然可以使用安全发件人列表来帮助 (误报 (标记为垃圾邮件) 的电子邮件，但应考虑使用安全发件人列表作为临时解决方案，应尽可能避免使用该解决方案。</span><span class="sxs-lookup"><span data-stu-id="99752-116">While you can use safe sender lists to help with false positives (good email marked as spam), you should consider the use of safe sender lists as a temporary solution that should be avoided if possible.</span></span> <span data-ttu-id="99752-117">我们不建议使用安全发件人列表管理误报，因为垃圾邮件筛选的例外会让您的组织将其投入欺骗和其他攻击。</span><span class="sxs-lookup"><span data-stu-id="99752-117">We don't recommend managing false positives by using safe sender lists, because exceptions to spam filtering can open your organization to spoofing and other attacks.</span></span> <span data-ttu-id="99752-118">如果您对使用安全发件人列表管理误报感到了解，则你必须是理智之，并且准备就绪时将主题[报告给 Microsoft。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="99752-118">If you insist on using safe sender lists to manage false positives, you need to be vigilant and keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>
>
> - <span data-ttu-id="99752-119">要允许域发送未经身份验证的电子邮件 (请绕过反欺骗保护) 而无需绕过反垃圾邮件和反恶意软件检查，您可以将其添加到 [AllowedToSpoof 安全发件人列表](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="99752-119">To allow a domain to send unauthenticated email (bypass anti-spoofing protection) but not bypass anti-spam and anti-malware checks, you can add it to the [AllowedToSpoof safe sender list](walkthrough-spoof-intelligence-insight.md)</span></span>
>
> - <span data-ttu-id="99752-120">EOP 和 Outlook 检查不同的邮件属性，以确定邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="99752-120">EOP and Outlook inspect different message properties to determine the sender of the message.</span></span> <span data-ttu-id="99752-121">有关详细信息，请参阅本主题 [后面的批量电子邮件注意](#considerations-for-bulk-email) 事项部分。</span><span class="sxs-lookup"><span data-stu-id="99752-121">For more information, see the [Considerations for bulk email](#considerations-for-bulk-email) section later in this topic.</span></span>

<span data-ttu-id="99752-122">相比之下，还可以通过多个选项来阻止来自使用阻止发件人列表的特定 _源的电子邮件_。</span><span class="sxs-lookup"><span data-stu-id="99752-122">In contrast, you also have several options to block email from specific sources using _blocked sender lists_.</span></span> <span data-ttu-id="99752-123">有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="99752-123">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="recommended-use-mail-flow-rules"></a><span data-ttu-id="99752-124"> (建议) 使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="99752-124">(Recommended) Use mail flow rules</span></span>

<span data-ttu-id="99752-125">Exchange Online 和独立 EOP 中的邮件流规则使用条件和例外来标识邮件，并采取操作来指定邮件应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="99752-125">Mail flow rules in Exchange Online and standalone EOP use conditions and exceptions to identify messages, and actions to specify what should be done to those messages.</span></span> <span data-ttu-id="99752-126">有关详细信息，请参阅 [邮件流规则 (Exchange Online) 传输规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="99752-126">For more information, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>

<span data-ttu-id="99752-127">以下示例假设需要电子邮件从报表中contoso.com垃圾邮件筛选跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="99752-127">The following example assumes you need email from contoso.com to skip spam filtering.</span></span> <span data-ttu-id="99752-128">为此，请配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="99752-128">To do this, configure the following settings:</span></span>

1. <span data-ttu-id="99752-129">**条件**：**发件人** \> **域为contoso.com。** \></span><span class="sxs-lookup"><span data-stu-id="99752-129">**Condition**: **The sender** \> **domain is** \> contoso.com.</span></span>

2. <span data-ttu-id="99752-130">配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="99752-130">Configure either of the following settings:</span></span>

   - <span data-ttu-id="99752-131">**邮件流规则条件**： **邮件头包括** \> **下列任何词头名称** \> **：** `Authentication-Results` \> **标头值**： `dmarc=pass` 或 `dmarc=bestguesspass` 。</span><span class="sxs-lookup"><span data-stu-id="99752-131">**Mail flow rule condition**: **A message header** \> **includes any of these words** \> **Header name**: `Authentication-Results` \> **Header value**: `dmarc=pass` or `dmarc=bestguesspass`.</span></span>

     <span data-ttu-id="99752-132">此条件检查发送电子邮件域的发件人身份验证状态，以确保发送域未被欺骗。</span><span class="sxs-lookup"><span data-stu-id="99752-132">This condition checks the sender authentication status of the sending email domain to ensure that the sending domain is not being spoofed.</span></span> <span data-ttu-id="99752-133">有关电子邮件身份验证的详细信息，请参阅[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [、DKIM](use-dkim-to-validate-outbound-email.md)和[DMARC。](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="99752-133">For more information about email authentication, see [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

   - <span data-ttu-id="99752-134">**IP 允许列表**：指定连接筛选器策略中的源 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="99752-134">**IP Allow List**: Specify the source IP address or address range in the connection filter policy.</span></span>
  
     <span data-ttu-id="99752-135">如果发送域没有身份验证，则使用此设置。</span><span class="sxs-lookup"><span data-stu-id="99752-135">Use this setting if the sending domain does not have authentication.</span></span> <span data-ttu-id="99752-136">如果它是 IP 允许列表中的源 IP 地址，则尽可能具有限制性。</span><span class="sxs-lookup"><span data-stu-id="99752-136">Be as restrictive as possible when it comes to the source IP addresses in the IP Allow List.</span></span> <span data-ttu-id="99752-137">建议的 IP 地址范围为 /24 或更小 (更好地为) 。</span><span class="sxs-lookup"><span data-stu-id="99752-137">We recommend an IP address range of /24 or less (less is better).</span></span> <span data-ttu-id="99752-138">请勿使用属于使用者服务（例如，工作流或 (）outlook.com) IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="99752-138">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

   > [!IMPORTANT]
   >
   > - <span data-ttu-id="99752-139">从不将仅使用发件人域 *配置* 邮件流规则作为条件以跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="99752-139">Never configure configure mail flow rules with *only* the sender domain as the condition to skip spam filtering.</span></span> <span data-ttu-id="99752-140">这样会 *显著提高* 攻击者可以欺骗发送域 (或模拟完整电子邮件地址) 、跳过所有垃圾邮件筛选，并跳过发件人身份验证检查，以便该邮件到达收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="99752-140">Doing so will *significantly* increase the likelihood that attackers can spoof the sending domain (or impersonate the full email address), skip all spam filtering, and skip sender authentication checks so the message will arrive in the recipient's Inbox.</span></span>
   >
   > - <span data-ttu-id="99752-141">不要使用你自己的域 (你自己的域（亦称为"接受的) 或 (受欢的microsoft.com) 例如，microsoft.com) 作为邮件流规则的条件。</span><span class="sxs-lookup"><span data-stu-id="99752-141">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) as conditions in mail flow rules.</span></span> <span data-ttu-id="99752-142">这样做被视为高风险，因为它为攻击者带来了发送本来会被筛选的电子邮件的机会。</span><span class="sxs-lookup"><span data-stu-id="99752-142">Doing so is considered high risk because it creates opportunities for attackers to send email that would otherwise be filtered.</span></span>
   >
   > - <span data-ttu-id="99752-143">如果您允许网络地址转换 (NAT) 网关之后的 IP 地址，则需要知道 NAT 池中涉及的服务器，才能知道 IP 允许列表的作用域。</span><span class="sxs-lookup"><span data-stu-id="99752-143">If you allow an IP address that's behind a network address translation (NAT) gateway, you need to know the servers that are involved in the NAT pool in order to know the scope of your IP Allow List.</span></span> <span data-ttu-id="99752-144">IP 地址和 NAT 参与者可以更改。</span><span class="sxs-lookup"><span data-stu-id="99752-144">IP addresses and NAT participants can change.</span></span> <span data-ttu-id="99752-145">作为标准维护过程的一部分，您需要定期检查 IP 允许列表条目。</span><span class="sxs-lookup"><span data-stu-id="99752-145">You need to periodically check your IP Allow List entries as part of your standard maintenance procedures.</span></span>

3. <span data-ttu-id="99752-146">**可选条件**：</span><span class="sxs-lookup"><span data-stu-id="99752-146">**Optional conditions**:</span></span>

   - <span data-ttu-id="99752-147">**发件人** \>**为内部/外部** \>**组织外部**：此条件是隐式的，但可以用它来说明可能未正确配置的本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="99752-147">**The sender** \> **is internal/external** \> **Outside the organization**: This condition is implicit, but it's OK to use it to account for on-premises email servers that might not be correctly configured.</span></span>

   - <span data-ttu-id="99752-148">**主题或正文** \>**主题或正文包含以下任何词语** \>\<keywords\>：如果可以在主题行或邮件正文中按关键字或短语进一步限制邮件，则可以使用这些词作为条件。</span><span class="sxs-lookup"><span data-stu-id="99752-148">**The subject or body** \> **subject or body includes any of these words** \> \<keywords\>: If you can further restrict the messages by keywords or phrases in the subject line or message body, you can use those words as a condition.</span></span>

4. <span data-ttu-id="99752-149">**操作**：在该规则中配置以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="99752-149">**Action**: Configure both of these actions in the rule:</span></span>

   <span data-ttu-id="99752-150">a.</span><span class="sxs-lookup"><span data-stu-id="99752-150">a.</span></span> <span data-ttu-id="99752-151">**修改邮件属性** \>**设置 SCL 外部 (可信度) \*\* \>**绕过垃圾邮件筛选\*\*。</span><span class="sxs-lookup"><span data-stu-id="99752-151">**Modify the message properties** \> **set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

   <span data-ttu-id="99752-152">b.</span><span class="sxs-lookup"><span data-stu-id="99752-152">b.</span></span> <span data-ttu-id="99752-153">**邮件头** \>**包含以下任何词语** \>**标头名称**： \<CustomHeaderName\> **标头值** \<CustomHeaderValue\> ：.</span><span class="sxs-lookup"><span data-stu-id="99752-153">**A message header** \> **includes any of these words** \> **Header name**: \<CustomHeaderName\> **Header value**: \<CustomHeaderValue\>.</span></span>

      <span data-ttu-id="99752-154">例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。</span><span class="sxs-lookup"><span data-stu-id="99752-154">For example, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`.</span></span> <span data-ttu-id="99752-155">如果规则中有多个域，您可以根据需要自定义头文本。</span><span class="sxs-lookup"><span data-stu-id="99752-155">If you have more than one domain in the rule, you can customize the header text as appropriate.</span></span>

      <span data-ttu-id="99752-156">当邮件由于邮件流规则而跳过垃圾邮件筛选时，会在 `SFV:SKN` **X-Forefront-Antispam-Report 标头中标记该值** 。</span><span class="sxs-lookup"><span data-stu-id="99752-156">When a message skips spam filtering due to a mail flow rule, the value `SFV:SKN` value is stamped in the **X-Forefront-Antispam-Report** header.</span></span> <span data-ttu-id="99752-157">如果邮件来自 IP 允许列表上的源，则也会 `IPV:CAL` 添加该值。</span><span class="sxs-lookup"><span data-stu-id="99752-157">If the message is from a source that's on the IP Allow List, the value `IPV:CAL` is also added.</span></span> <span data-ttu-id="99752-158">这些值可帮助进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="99752-158">These values can help you with troubleshooting.</span></span>

![将不传递垃圾邮件筛选的 EAC 中的邮件流规则设置。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a><span data-ttu-id="99752-160">使用 Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="99752-160">Use Outlook Safe Senders</span></span>

<span data-ttu-id="99752-161">用户或管理员可以将发件人电子邮件地址添加到邮箱的"安全发件人"列表中，而不是组织设置。</span><span class="sxs-lookup"><span data-stu-id="99752-161">Instead of an organizational setting, users or admins can add the sender email addresses to the Safe Senders list in the mailbox.</span></span> <span data-ttu-id="99752-162">有关说明，请参阅在 [Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="99752-162">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span> <span data-ttu-id="99752-163">在大多数情况下都不需要这样的操作，因为发件人将绕过筛选堆栈的一部分。</span><span class="sxs-lookup"><span data-stu-id="99752-163">This is not desirable in most situations since senders will bypass parts of the filtering stack.</span></span> <span data-ttu-id="99752-164">虽然您信任发件人，但发件人仍会受到安全影响，并可能发送恶意内容。</span><span class="sxs-lookup"><span data-stu-id="99752-164">Although you trust the sender, the sender cans still be compromised and can send malicious content.</span></span> <span data-ttu-id="99752-165">最好让筛选器执行检查每封邮件所需的操作，如果筛选器出问题，则会向 [Microsoft](report-junk-email-messages-to-microsoft.md) 报告误报/否。</span><span class="sxs-lookup"><span data-stu-id="99752-165">It is best that you let our filters do what is needed to check every message and then [report the false positive/negative to Microsoft](report-junk-email-messages-to-microsoft.md) if our filters got it wrong.</span></span> <span data-ttu-id="99752-166">绕过筛选堆栈也会干扰[ZAP。](zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="99752-166">Bypassing the filtering stack also interferes with [ZAP](zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="99752-167">如果邮件由于用户的安全发件人列表，导致邮件跳过垃圾邮件筛选 **，X-Forefront-Antispam-Report** 标头字段将包含值，该值指示已绕过垃圾邮件、欺骗和网络钓 `SFV:SFE` 鱼筛选。</span><span class="sxs-lookup"><span data-stu-id="99752-167">When messages skip spam filtering due to a user's Safe Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:SFE`, which indicates that spam, spoof, and phish filtering were bypassed.</span></span>

## <a name="use-the-ip-allow-list"></a><span data-ttu-id="99752-168">使用 IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="99752-168">Use the IP Allow List</span></span>

<span data-ttu-id="99752-169">如果无法按上文所述使用邮件流规则，下一个最佳选择是将源电子邮件服务器添加到连接筛选器策略中的 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="99752-169">If you can't use mail flow rules as previously described, the next best option is to add the source email server or servers to the IP Allow List in the connection filter policy.</span></span> <span data-ttu-id="99752-170">有关详细信息，请参阅 [在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="99752-170">For details, see [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

<span data-ttu-id="99752-171">**注意**：</span><span class="sxs-lookup"><span data-stu-id="99752-171">**Notes**:</span></span>

- <span data-ttu-id="99752-172">请务必将允许的 IP 地址数保持在最少数，因此尽可能避免使用整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="99752-172">It's important that you keep the number of allowed IP addresses to a minimum, so avoid using entire IP address ranges whenever possible.</span></span>

- <span data-ttu-id="99752-173">请勿使用属于使用者服务（例如，工作流或 (）outlook.com) IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="99752-173">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

- <span data-ttu-id="99752-174">定期查看 IP 允许列表中的条目并删除不再需要的条目。</span><span class="sxs-lookup"><span data-stu-id="99752-174">Regularly review the entries in the IP Allow List and remove the entries that you no longer need.</span></span>

> [!CAUTION]
> <span data-ttu-id="99752-175">无需像邮件流规则一样执行其他验证，来自 IP 允许列表中的来源的电子邮件将跳过垃圾邮件筛选和发件人 (SPF、DKIM、DMARC) 检查。</span><span class="sxs-lookup"><span data-stu-id="99752-175">Without additional verification like mail flow rules, email from sources in the IP Allow List skips spam filtering and sender authentication (SPF, DKIM, DMARC) checks.</span></span> <span data-ttu-id="99752-176">这会造为攻击者成功将电子邮件传递到收件箱（否则会进行筛选）带来高风险。</span><span class="sxs-lookup"><span data-stu-id="99752-176">This creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered.</span></span>

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a><span data-ttu-id="99752-177">使用允许发件人列表或允许的域列表</span><span class="sxs-lookup"><span data-stu-id="99752-177">Use allowed sender lists or allowed domain lists</span></span>

<span data-ttu-id="99752-178">最不希望的选择是使用反垃圾邮件策略中包含的允许发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="99752-178">The least desirable option is to use the allowed sender list or allowed domain list in anti-spam policies.</span></span> <span data-ttu-id="99752-179">只应尽可能 *避免此选项，* 因为发件人绕过所有垃圾邮件、欺骗和网络钓鱼保护，以及发件人 (SPF、DKIM 和 DMARC) 。</span><span class="sxs-lookup"><span data-stu-id="99752-179">You should avoid this option *if at all possible* because senders bypass all spam, spoof, and phish protection, and sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="99752-180">此方法最适合仅用于临时测试。</span><span class="sxs-lookup"><span data-stu-id="99752-180">This method is best used for temporary testing only.</span></span> <span data-ttu-id="99752-181">详细步骤可以在 EOP 中" [配置反垃圾邮件策略"](configure-your-spam-filter-policies.md) 主题中找到。</span><span class="sxs-lookup"><span data-stu-id="99752-181">The detailed steps can be found in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.</span></span>

<span data-ttu-id="99752-182">这些列表的最大限制是大约 1000 个条目;虽然您只能在门户中输入 30 个条目。</span><span class="sxs-lookup"><span data-stu-id="99752-182">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="99752-183">必须使用 PowerShell 添加超过 30 个条目。</span><span class="sxs-lookup"><span data-stu-id="99752-183">You must use PowerShell to add more than 30 entries.</span></span>

> [!CAUTION]
>
> - <span data-ttu-id="99752-184">此方法可使攻击者将电子邮件成功送达到收件箱（否则会进行筛选）带来高风险。</span><span class="sxs-lookup"><span data-stu-id="99752-184">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered.</span></span>
>
> - <span data-ttu-id="99752-185">请勿使用你自己的域 (你自己的接受域) 或受（ (例如，microsoft.com) 允许的域列表中）。</span><span class="sxs-lookup"><span data-stu-id="99752-185">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) in allowed domain lists.</span></span>

## <a name="considerations-for-bulk-email"></a><span data-ttu-id="99752-186">批量电子邮件的注意事项</span><span class="sxs-lookup"><span data-stu-id="99752-186">Considerations for bulk email</span></span>

<span data-ttu-id="99752-187">标准 SMTP 电子邮件由*邮件信封*和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="99752-187">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="99752-188">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="99752-188">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="99752-189">邮件内容包含邮件头字段（统称为*邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="99752-189">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="99752-190">RFC 5321 中介绍了邮件信封，RFC 5322 中介绍了邮件头。</span><span class="sxs-lookup"><span data-stu-id="99752-190">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="99752-191">收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，实际上并不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="99752-191">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="99752-192">地址 `5321.MailFrom` (也称为 **"MAIL FROM** 地址、P1 发件人"或"信封发件人) "的电子邮件地址是邮件 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="99752-192">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="99752-193">通常，此电子邮件地址记录在邮件头 (中的 **"返回** 路径"标头字段中，尽管发件人可以指定不同的 **返回** 路径电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="99752-193">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="99752-194">如果邮件无法送达，则其其人是未送达报告 (的收件人，也称为 NDR 或退回) 。</span><span class="sxs-lookup"><span data-stu-id="99752-194">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="99752-195">`5322.From` (也称为发件人地址**From**或 P2 发件人) 是 **"发件人"标头字段**中的电子邮件地址，也是电子邮件客户端中显示的发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="99752-195">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="99752-196">通常，与 `5321.MailFrom` 个人 `5322.From` 间的通信 (相同) ，</span><span class="sxs-lookup"><span data-stu-id="99752-196">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="99752-197">但是，当代表其他人发送电子邮件时，地址可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="99752-197">However, when email is sent on behalf of someone else, the addresses can be different.</span></span> <span data-ttu-id="99752-198">这是批量电子邮件最常造的情况。</span><span class="sxs-lookup"><span data-stu-id="99752-198">This happens most often for bulk email messages.</span></span>

<span data-ttu-id="99752-199">例如，假设 Blue Yonder Airlines 已采用百分之一流，可以发送电子邮件广告。</span><span class="sxs-lookup"><span data-stu-id="99752-199">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="99752-200">在收件箱中收到的邮件包含以下属性：</span><span class="sxs-lookup"><span data-stu-id="99752-200">The message you receive in your Inbox has the following properties:</span></span>

- <span data-ttu-id="99752-201">地址 `5321.MailFrom` 不是blueyonder.airlines@margiestravel.com。</span><span class="sxs-lookup"><span data-stu-id="99752-201">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="99752-202">地址 `5322.From` 是blueyonder@news.blueyonderairlines.com显示的，你将在 Outlook 中看到该地址。</span><span class="sxs-lookup"><span data-stu-id="99752-202">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="99752-203">EOP 中反垃圾邮件策略中的安全发件人列表和安全域列表仅检查 `5322.From` 这些地址，这类似于使用该地址的 Outlook 安全 `5322.From` 发件人。</span><span class="sxs-lookup"><span data-stu-id="99752-203">Safe sender lists and safe domain lists in anti-spam policies in EOP inspect only the `5322.From` addresses, this is similar to Outlook Safe Senders that uses the `5322.From` address.</span></span>

<span data-ttu-id="99752-204">若要防止对此邮件进行筛选，可以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="99752-204">To prevent this message from being filtered, you can take the following steps:</span></span>

- <span data-ttu-id="99752-205">将blueyonder@news.blueyonderairlines.com (`5322.From` 地址) 为 Outlook 安全发件人。</span><span class="sxs-lookup"><span data-stu-id="99752-205">Add blueyonder@news.blueyonderairlines.com (the `5322.From` address) as an Outlook Safe Sender.</span></span>

- <span data-ttu-id="99752-206">[Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`) , or both.</span><span class="sxs-lookup"><span data-stu-id="99752-206">[Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`), or both.</span></span>

<span data-ttu-id="99752-207">有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="99752-207">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>
