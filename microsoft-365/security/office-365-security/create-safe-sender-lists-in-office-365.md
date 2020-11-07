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
description: 管理员可以了解可用的首选选项以允许入站邮件在 Exchange Online Protection (EOP) 中。
ms.openlocfilehash: 0ab0a636cb70d98aa7c17ffe6aaec66ae1f4ecc7
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945338"
---
# <a name="create-safe-sender-lists-in-eop"></a><span data-ttu-id="a7828-103">在 EOP 中创建安全发件人列表</span><span class="sxs-lookup"><span data-stu-id="a7828-103">Create safe sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a7828-104">如果您是在 Exchange Online 中使用邮箱的 Microsoft 365 客户或独立 Exchange Online Protection (EOP) 不含 Exchange Online 邮箱的客户，EOP 将提供多种方法来确保用户收到来自受信任的发件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a7828-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of ensuring that users will receive email from trusted senders.</span></span> <span data-ttu-id="a7828-105">这些选项包括 Exchange 邮件流规则 (也称为传输规则) 、Outlook 安全发件人、IP 允许列表 (连接筛选) ，以及反垃圾邮件策略中允许的发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="a7828-105">These options include Exchange mail flow rules (also known as transport rules), Outlook Safe Senders, the IP Allow List (connection filtering), and allowed sender lists or allowed domain lists in anti-spam policies.</span></span> <span data-ttu-id="a7828-106">可以将这些选项统称为 _安全发件人列表_ 。</span><span class="sxs-lookup"><span data-stu-id="a7828-106">Collectively, you can think of these options as _safe sender lists_.</span></span>

<span data-ttu-id="a7828-107">以下列表中介绍了可用的安全发件人列表，从最建议的到最小建议的顺序如下：</span><span class="sxs-lookup"><span data-stu-id="a7828-107">The available safe sender lists are described in the following list in order from most recommended to least recommended:</span></span>

1. <span data-ttu-id="a7828-108">邮件流规则</span><span class="sxs-lookup"><span data-stu-id="a7828-108">Mail flow rules</span></span>
2. <span data-ttu-id="a7828-109">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="a7828-109">Outlook Safe Senders</span></span>
3. <span data-ttu-id="a7828-110"> (连接筛选的 IP 允许列表) </span><span class="sxs-lookup"><span data-stu-id="a7828-110">IP Allow List (connection filtering)</span></span>
4. <span data-ttu-id="a7828-111"> (反垃圾邮件策略的允许的发件人列表或允许的域列表) </span><span class="sxs-lookup"><span data-stu-id="a7828-111">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>

<span data-ttu-id="a7828-112">邮件流规则允许最大限度地确保只允许使用正确的邮件。</span><span class="sxs-lookup"><span data-stu-id="a7828-112">Mail flow rules allow the most flexibility to ensure that only the right messages are allowed.</span></span> <span data-ttu-id="a7828-113">反垃圾邮件策略中允许的发件人和允许的域列表与 IP 允许列表相比不安全，因为发件人的电子邮件域很容易被欺骗。</span><span class="sxs-lookup"><span data-stu-id="a7828-113">Allowed sender and allowed domain lists in anti-spam policies aren't as secure as the IP Allow List, because the sender's email domain is easily spoofed.</span></span> <span data-ttu-id="a7828-114">但是，IP 允许列表也会带来风险，因为从该 IP 地址发送的 _任何_ 域发送的电子邮件将绕过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="a7828-114">But, the IP Allow List also presents a risk, because email from _any_ domain that's sent from that IP address will bypass spam filtering.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="a7828-115">请务必密切监视使用安全发件人列表的垃圾邮件筛选的 *任何* 例外情况。</span><span class="sxs-lookup"><span data-stu-id="a7828-115">Be careful to closely monitor *any* exceptions that you to spam filtering using safe sender lists.</span></span>
>
> - <span data-ttu-id="a7828-116">虽然您可以使用安全发件人列表帮助误报 (将正常的电子邮件标记为垃圾邮件) ，但您应考虑将安全发件人列表用作临时解决方案，如果可能，应尽可能避免使用。</span><span class="sxs-lookup"><span data-stu-id="a7828-116">While you can use safe sender lists to help with false positives (good email marked as spam), you should consider the use of safe sender lists as a temporary solution that should be avoided if possible.</span></span> <span data-ttu-id="a7828-117">我们不建议使用安全发件人列表管理误报，因为垃圾邮件筛选例外可以将组织打开为哄骗和其他攻击。</span><span class="sxs-lookup"><span data-stu-id="a7828-117">We don't recommend managing false positives by using safe sender lists, because exceptions to spam filtering can open your organization to spoofing and other attacks.</span></span> <span data-ttu-id="a7828-118">如果您坚持使用安全发件人列表来管理误报，您需要时刻小心，并在准备好时让主题 [报告邮件和文件到 Microsoft](report-junk-email-messages-to-microsoft.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7828-118">If you insist on using safe sender lists to manage false positives, you need to be vigilant and keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>
>
> - <span data-ttu-id="a7828-119">若要允许域发送未经身份验证的电子邮件 (绕过反欺骗保护) 但不绕过反垃圾邮件和反恶意软件检查，可以将其添加到 [AllowedToSpoof 安全发件人列表](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="a7828-119">To allow a domain to send unauthenticated email (bypass anti-spoofing protection) but not bypass anti-spam and anti-malware checks, you can add it to the [AllowedToSpoof safe sender list](walkthrough-spoof-intelligence-insight.md)</span></span>
>
> - <span data-ttu-id="a7828-120">EOP 和 Outlook 检查不同的邮件属性以确定邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="a7828-120">EOP and Outlook inspect different message properties to determine the sender of the message.</span></span> <span data-ttu-id="a7828-121">有关详细信息，请参阅本主题后面的 " [批量电子邮件的注意事项](#considerations-for-bulk-email) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a7828-121">For more information, see the [Considerations for bulk email](#considerations-for-bulk-email) section later in this topic.</span></span>

<span data-ttu-id="a7828-122">相比之下，您还可以使用 _阻止发件人列表_ 的多个选项阻止来自特定来源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a7828-122">In contrast, you also have several options to block email from specific sources using _blocked sender lists_.</span></span> <span data-ttu-id="a7828-123">有关详细信息，请参阅[在 EOP 中创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-123">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="recommended-use-mail-flow-rules"></a><span data-ttu-id="a7828-124"> (建议的) 使用邮件流规则</span><span class="sxs-lookup"><span data-stu-id="a7828-124">(Recommended) Use mail flow rules</span></span>

<span data-ttu-id="a7828-125">Exchange Online 和独立 EOP 中的邮件流规则：使用条件和例外来标识邮件，以及指定对这些邮件执行的操作的操作。</span><span class="sxs-lookup"><span data-stu-id="a7828-125">Mail flow rules in Exchange Online and standalone EOP use conditions and exceptions to identify messages, and actions to specify what should be done to those messages.</span></span> <span data-ttu-id="a7828-126">有关详细信息，请参阅 [Mail flow rules (transport rules) In Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="a7828-126">For more information, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>

<span data-ttu-id="a7828-127">下面的示例假定您需要来自 contoso.com 的电子邮件以跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="a7828-127">The following example assumes you need email from contoso.com to skip spam filtering.</span></span> <span data-ttu-id="a7828-128">为此，请配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a7828-128">To do this, configure the following settings:</span></span>

1. <span data-ttu-id="a7828-129">**条件** ： **发件人** \> **域为** \> contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a7828-129">**Condition** : **The sender** \> **domain is** \> contoso.com.</span></span>

2. <span data-ttu-id="a7828-130">配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="a7828-130">Configure either of the following settings:</span></span>

   - <span data-ttu-id="a7828-131">**邮件流规则条件** ： **邮件头** \> **包含以下任何词语** \> **头名称** ： `Authentication-Results` \> **头值** ： `dmarc=pass` 或 `dmarc=bestguesspass` 。</span><span class="sxs-lookup"><span data-stu-id="a7828-131">**Mail flow rule condition** : **A message header** \> **includes any of these words** \> **Header name** : `Authentication-Results` \> **Header value** : `dmarc=pass` or `dmarc=bestguesspass`.</span></span>

     <span data-ttu-id="a7828-132">此条件检查发送电子邮件域的电子邮件身份验证状态，以确保不会欺骗发送域。</span><span class="sxs-lookup"><span data-stu-id="a7828-132">This condition checks the email authentication status of the sending email domain to ensure that the sending domain is not being spoofed.</span></span> <span data-ttu-id="a7828-133">有关电子邮件身份验证的详细信息，请参阅 [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-133">For more information about email authentication, see [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

   - <span data-ttu-id="a7828-134">**IP 允许列表** ：在连接筛选器策略中指定源 IP 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="a7828-134">**IP Allow List** : Specify the source IP address or address range in the connection filter policy.</span></span>
  
     <span data-ttu-id="a7828-135">如果发送域不使用电子邮件身份验证，则使用此设置。</span><span class="sxs-lookup"><span data-stu-id="a7828-135">Use this setting if the sending domain does not use email authentication.</span></span> <span data-ttu-id="a7828-136">当到达 IP 允许列表中的源 IP 地址时，应尽可能地限制其限制性。</span><span class="sxs-lookup"><span data-stu-id="a7828-136">Be as restrictive as possible when it comes to the source IP addresses in the IP Allow List.</span></span> <span data-ttu-id="a7828-137">建议使用的 IP 地址范围为/24 或更低 (更) 。</span><span class="sxs-lookup"><span data-stu-id="a7828-137">We recommend an IP address range of /24 or less (less is better).</span></span> <span data-ttu-id="a7828-138">请勿使用属于消费服务 (的 IP 地址范围，例如 outlook.com) 或共享基础结构。</span><span class="sxs-lookup"><span data-stu-id="a7828-138">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

   > [!IMPORTANT]
   >
   > - <span data-ttu-id="a7828-139">永远不要将邮件流规则配置为 *只* 使用发件人域作为跳过垃圾邮件筛选的条件。</span><span class="sxs-lookup"><span data-stu-id="a7828-139">Never configure mail flow rules with *only* the sender domain as the condition to skip spam filtering.</span></span> <span data-ttu-id="a7828-140">这样做会 *显著* 增加攻击者欺骗发送域的可能性 (或模拟完整的电子邮件地址) 、跳过所有垃圾邮件筛选和跳过发件人身份验证检查，以便邮件将到达收件人的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="a7828-140">Doing so will *significantly* increase the likelihood that attackers can spoof the sending domain (or impersonate the full email address), skip all spam filtering, and skip sender authentication checks so the message will arrive in the recipient's Inbox.</span></span>
   >
   > - <span data-ttu-id="a7828-141">请勿使用自己的域 (也称为接受域) 或受欢迎的域 (例如，microsoft.com) 邮件流规则中的条件。</span><span class="sxs-lookup"><span data-stu-id="a7828-141">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) as conditions in mail flow rules.</span></span> <span data-ttu-id="a7828-142">这样做被认为是高风险，因为它会给攻击者发送电子邮件，以其他方式筛选的机会。</span><span class="sxs-lookup"><span data-stu-id="a7828-142">Doing so is considered high risk because it creates opportunities for attackers to send email that would otherwise be filtered.</span></span>
   >
   > - <span data-ttu-id="a7828-143">如果您允许网络地址转换后面的 IP 地址 (NAT) 网关，则需要知道 NAT 池中涉及的服务器，才能知道您的 IP 允许列表的作用域。</span><span class="sxs-lookup"><span data-stu-id="a7828-143">If you allow an IP address that's behind a network address translation (NAT) gateway, you need to know the servers that are involved in the NAT pool in order to know the scope of your IP Allow List.</span></span> <span data-ttu-id="a7828-144">IP 地址和 NAT 参与者可以更改。</span><span class="sxs-lookup"><span data-stu-id="a7828-144">IP addresses and NAT participants can change.</span></span> <span data-ttu-id="a7828-145">你需要定期检查你的 IP 允许列表条目，作为你的标准维护过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7828-145">You need to periodically check your IP Allow List entries as part of your standard maintenance procedures.</span></span>

3. <span data-ttu-id="a7828-146">**可选条件** ：</span><span class="sxs-lookup"><span data-stu-id="a7828-146">**Optional conditions** :</span></span>

   - <span data-ttu-id="a7828-147">**发件人** \>**内部/外部** \>在 **组织外部** ：此条件是隐式的，但可使用它来考虑可能未正确配置的本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="a7828-147">**The sender** \> **is internal/external** \> **Outside the organization** : This condition is implicit, but it's OK to use it to account for on-premises email servers that might not be correctly configured.</span></span>

   - <span data-ttu-id="a7828-148">**主题或正文** \>**主题或正文包含以下任何词语** \>\<keywords\>：如果可以通过主题行或邮件正文中的关键字或短语进一步限制邮件，则可以使用这些词作为条件。</span><span class="sxs-lookup"><span data-stu-id="a7828-148">**The subject or body** \> **subject or body includes any of these words** \> \<keywords\>: If you can further restrict the messages by keywords or phrases in the subject line or message body, you can use those words as a condition.</span></span>

4. <span data-ttu-id="a7828-149">**操作** ：在规则中配置这两个操作：</span><span class="sxs-lookup"><span data-stu-id="a7828-149">**Action** : Configure both of these actions in the rule:</span></span>

   <span data-ttu-id="a7828-150">a.</span><span class="sxs-lookup"><span data-stu-id="a7828-150">a.</span></span> <span data-ttu-id="a7828-151">**修改邮件属性** \>**(SCL)** \> 设置垃圾邮件可信度级别 **绕过垃圾邮件筛选** 。</span><span class="sxs-lookup"><span data-stu-id="a7828-151">**Modify the message properties** \> **set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

   <span data-ttu-id="a7828-152">b.</span><span class="sxs-lookup"><span data-stu-id="a7828-152">b.</span></span> <span data-ttu-id="a7828-153">**修改邮件属性** \>**设置邮件头** ： **将邮件标头设置** \<CustomHeaderName\> **为值** \<CustomHeaderValue\> 。</span><span class="sxs-lookup"><span data-stu-id="a7828-153">**Modify the message properties** \> **set a message header** : **Set the message header** \<CustomHeaderName\> **to the value** \<CustomHeaderValue\>.</span></span>

      <span data-ttu-id="a7828-154">例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。</span><span class="sxs-lookup"><span data-stu-id="a7828-154">For example, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`.</span></span> <span data-ttu-id="a7828-155">如果规则中有多个域，则可以根据需要自定义标题文本。</span><span class="sxs-lookup"><span data-stu-id="a7828-155">If you have more than one domain in the rule, you can customize the header text as appropriate.</span></span>

      <span data-ttu-id="a7828-156">当邮件由于邮件流规则而跳过垃圾邮件筛选时，该值 `SFV:SKN` 值将在 **X Forefront-反垃圾邮件报告** 标头中标记。</span><span class="sxs-lookup"><span data-stu-id="a7828-156">When a message skips spam filtering due to a mail flow rule, the value `SFV:SKN` value is stamped in the **X-Forefront-Antispam-Report** header.</span></span> <span data-ttu-id="a7828-157">如果邮件来自 IP 允许列表中的源，则 `IPV:CAL` 也会添加该值。</span><span class="sxs-lookup"><span data-stu-id="a7828-157">If the message is from a source that's on the IP Allow List, the value `IPV:CAL` is also added.</span></span> <span data-ttu-id="a7828-158">这些值可帮助您进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="a7828-158">These values can help you with troubleshooting.</span></span>

![EAC 中用于绕过垃圾邮件筛选的邮件流规则设置。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a><span data-ttu-id="a7828-160">使用 Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="a7828-160">Use Outlook Safe Senders</span></span>

<span data-ttu-id="a7828-161">用户或管理员可以将发件人电子邮件地址添加到邮箱中的安全发件人列表中，而不是组织设置。</span><span class="sxs-lookup"><span data-stu-id="a7828-161">Instead of an organizational setting, users or admins can add the sender email addresses to the Safe Senders list in the mailbox.</span></span> <span data-ttu-id="a7828-162">有关说明，请参阅在 [Office 365 中的 Exchange Online 邮箱上配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-162">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span> <span data-ttu-id="a7828-163">在大多数情况下，这不是必需的，因为发件人将绕过部分筛选堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7828-163">This is not desirable in most situations since senders will bypass parts of the filtering stack.</span></span> <span data-ttu-id="a7828-164">尽管您信任发件人，但发件人仍可能受到威胁，并会发送恶意内容。</span><span class="sxs-lookup"><span data-stu-id="a7828-164">Although you trust the sender, the sender can still be compromised and send malicious content.</span></span> <span data-ttu-id="a7828-165">最好让我们的筛选器执行检查每个邮件所需的操作，然后将 [误报/负数报告给 Microsoft （](report-junk-email-messages-to-microsoft.md) 如果筛选器出现错误）。</span><span class="sxs-lookup"><span data-stu-id="a7828-165">It is best that you let our filters do what is needed to check every message and then [report the false positive/negative to Microsoft](report-junk-email-messages-to-microsoft.md) if our filters got it wrong.</span></span> <span data-ttu-id="a7828-166">绕过筛选堆栈也会妨碍 [ZAP](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-166">Bypassing the filtering stack also interferes with [ZAP](zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="a7828-167">当邮件由于用户的安全发件人列表而跳过垃圾邮件筛选时， **X-Forefront-反垃圾邮件报告** 标头字段将包含值 `SFV:SFE` ，这表明已绕过垃圾邮件、欺骗和网络钓鱼筛选。</span><span class="sxs-lookup"><span data-stu-id="a7828-167">When messages skip spam filtering due to a user's Safe Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:SFE`, which indicates that spam, spoof, and phish filtering were bypassed.</span></span>

## <a name="use-the-ip-allow-list"></a><span data-ttu-id="a7828-168">使用 IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="a7828-168">Use the IP Allow List</span></span>

<span data-ttu-id="a7828-169">如果您在前面所述的情况下无法使用邮件流规则，则下一个最佳选择是将源电子邮件服务器或服务器添加到连接筛选器策略中的 IP 允许列表中。</span><span class="sxs-lookup"><span data-stu-id="a7828-169">If you can't use mail flow rules as previously described, the next best option is to add the source email server or servers to the IP Allow List in the connection filter policy.</span></span> <span data-ttu-id="a7828-170">有关详细信息，请参阅 [在 EOP 中配置连接筛选](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-170">For details, see [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

<span data-ttu-id="a7828-171">**注意** ：</span><span class="sxs-lookup"><span data-stu-id="a7828-171">**Notes** :</span></span>

- <span data-ttu-id="a7828-172">一定要将允许的 IP 地址数保持为最小值，以便尽可能避免使用整个 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="a7828-172">It's important that you keep the number of allowed IP addresses to a minimum, so avoid using entire IP address ranges whenever possible.</span></span>

- <span data-ttu-id="a7828-173">请勿使用属于消费服务 (的 IP 地址范围，例如 outlook.com) 或共享基础结构。</span><span class="sxs-lookup"><span data-stu-id="a7828-173">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

- <span data-ttu-id="a7828-174">定期查看 IP 允许列表中的条目，并删除不再需要的条目。</span><span class="sxs-lookup"><span data-stu-id="a7828-174">Regularly review the entries in the IP Allow List and remove the entries that you no longer need.</span></span>

> [!CAUTION]
> <span data-ttu-id="a7828-175">如果没有其他验证（如邮件流规则），来自 IP 允许列表中的来源的电子邮件将跳过垃圾邮件筛选和发件人身份验证 (SPF、DKIM、DMARC) 检查。</span><span class="sxs-lookup"><span data-stu-id="a7828-175">Without additional verification like mail flow rules, email from sources in the IP Allow List skips spam filtering and sender authentication (SPF, DKIM, DMARC) checks.</span></span> <span data-ttu-id="a7828-176">这会造成攻击者成功将电子邮件传递到收件箱的高风险，否则将被筛选。</span><span class="sxs-lookup"><span data-stu-id="a7828-176">This creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered.</span></span>

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a><span data-ttu-id="a7828-177">使用允许的发件人列表或允许的域列表</span><span class="sxs-lookup"><span data-stu-id="a7828-177">Use allowed sender lists or allowed domain lists</span></span>

<span data-ttu-id="a7828-178">最不理想的选择是在反垃圾邮件策略中使用允许的发件人列表或允许的域列表。</span><span class="sxs-lookup"><span data-stu-id="a7828-178">The least desirable option is to use the allowed sender list or allowed domain list in anti-spam policies.</span></span> <span data-ttu-id="a7828-179">*如果可能* ，应尽可能避免此选项，因为发件人绕过所有垃圾邮件、欺骗和网络钓鱼防护以及发件人身份验证 (SPF、DKIM、DMARC) 。</span><span class="sxs-lookup"><span data-stu-id="a7828-179">You should avoid this option *if at all possible* because senders bypass all spam, spoof, and phish protection, and sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="a7828-180">此方法最好仅用于临时测试。</span><span class="sxs-lookup"><span data-stu-id="a7828-180">This method is best used for temporary testing only.</span></span> <span data-ttu-id="a7828-181">详细步骤可在 EOP 主题中的 " [配置反垃圾邮件策略](configure-your-spam-filter-policies.md) " 中找到。</span><span class="sxs-lookup"><span data-stu-id="a7828-181">The detailed steps can be found in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.</span></span>

<span data-ttu-id="a7828-182">这些列表的最大限制约为1000个条目;尽管只能将30个条目输入到门户中。</span><span class="sxs-lookup"><span data-stu-id="a7828-182">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="a7828-183">必须使用 PowerShell 添加30个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="a7828-183">You must use PowerShell to add more than 30 entries.</span></span>

> [!CAUTION]
>
> - <span data-ttu-id="a7828-184">此方法会带来以下风险：成功将电子邮件传递到收件箱的高风险，否则将被筛选。</span><span class="sxs-lookup"><span data-stu-id="a7828-184">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered.</span></span>
>
> - <span data-ttu-id="a7828-185">请勿使用自己的域 (也称为接受域) 或受欢迎的域 (例如，microsoft.com) 允许的域列表中。</span><span class="sxs-lookup"><span data-stu-id="a7828-185">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) in allowed domain lists.</span></span>

## <a name="considerations-for-bulk-email"></a><span data-ttu-id="a7828-186">批量电子邮件的注意事项</span><span class="sxs-lookup"><span data-stu-id="a7828-186">Considerations for bulk email</span></span>

<span data-ttu-id="a7828-187">标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="a7828-187">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="a7828-188">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a7828-188">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="a7828-189">邮件内容包含邮件头字段（统称为 *邮件头* ）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="a7828-189">The message content contains message header fields (collectively called the *message header* ) and the message body.</span></span> <span data-ttu-id="a7828-190">RFC 5321 中介绍了邮件信封，并且 RFC 5322 中介绍了邮件头。</span><span class="sxs-lookup"><span data-stu-id="a7828-190">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="a7828-191">收件人从不会看到实际邮件信封，因为它是由邮件传输进程生成的，并且实际上并不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7828-191">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="a7828-192">该 `5321.MailFrom` 地址 (也称为 " **发** 件人地址"、"P1 发件人" 或 "信封发件人") 是在邮件的 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a7828-192">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="a7828-193">此电子邮件地址通常记录在邮件标头的 " **返回路径** 标头" 字段中 (尽管可以将不同的 **返回路径** 电子邮件地址指定) 。</span><span class="sxs-lookup"><span data-stu-id="a7828-193">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="a7828-194">如果无法传递邮件，则表示未送达报告 (的收件人也称为 "NDR" 或 "退回邮件") 。</span><span class="sxs-lookup"><span data-stu-id="a7828-194">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="a7828-195">"发件人 `5322.From` 地址" **From** 或 "P2 发件人") 的 (也称为 **"发** 件人" 头字段中的电子邮件地址，它是电子邮件客户端中显示的发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a7828-195">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="a7828-196">通常， `5321.MailFrom` 和 `5322.From` 地址 (个人到人员通信) 相同。</span><span class="sxs-lookup"><span data-stu-id="a7828-196">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="a7828-197">但是，如果代表其他人发送电子邮件，则地址可能会不同。</span><span class="sxs-lookup"><span data-stu-id="a7828-197">However, when email is sent on behalf of someone else, the addresses can be different.</span></span> <span data-ttu-id="a7828-198">对于批量电子邮件，这通常会发生。</span><span class="sxs-lookup"><span data-stu-id="a7828-198">This happens most often for bulk email messages.</span></span>

<span data-ttu-id="a7828-199">例如，假设蓝色 Yonder 航空公司已雇用玛吉的旅行，发出电子邮件广告。</span><span class="sxs-lookup"><span data-stu-id="a7828-199">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="a7828-200">您在收件箱中收到的邮件具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a7828-200">The message you receive in your Inbox has the following properties:</span></span>

- <span data-ttu-id="a7828-201">`5321.MailFrom`地址为 blueyonder.airlines@margiestravel.com。</span><span class="sxs-lookup"><span data-stu-id="a7828-201">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="a7828-202">`5322.From`地址为 blueyonder@news.blueyonderairlines.com，这就是您在 Outlook 中看到的内容。</span><span class="sxs-lookup"><span data-stu-id="a7828-202">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="a7828-203">EOP 中的反垃圾邮件策略中的安全发件人列表和安全域列表仅检查 `5322.From` 地址，这类似于使用地址的 Outlook 安全发件人 `5322.From` 。</span><span class="sxs-lookup"><span data-stu-id="a7828-203">Safe sender lists and safe domain lists in anti-spam policies in EOP inspect only the `5322.From` addresses, this is similar to Outlook Safe Senders that uses the `5322.From` address.</span></span>

<span data-ttu-id="a7828-204">若要阻止筛选此邮件，您可以执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a7828-204">To prevent this message from being filtered, you can take the following steps:</span></span>

- <span data-ttu-id="a7828-205">将 blueyonder@news.blueyonderairlines.com (`5322.From`) 作为 Outlook 安全发件人的地址。</span><span class="sxs-lookup"><span data-stu-id="a7828-205">Add blueyonder@news.blueyonderairlines.com (the `5322.From` address) as an Outlook Safe Sender.</span></span>

- <span data-ttu-id="a7828-206">使用带有条件的[邮件流规则](#recommended-use-mail-flow-rules)，该条件查找来自 blueyonder@news.blueyonderairlines.com (`5322.From` 地址、Blueyonder.airlines@margiestravel.com (`5321.MailFrom`) 或两者的邮件。</span><span class="sxs-lookup"><span data-stu-id="a7828-206">[Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`), or both.</span></span>

<span data-ttu-id="a7828-207">有关详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a7828-207">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>
