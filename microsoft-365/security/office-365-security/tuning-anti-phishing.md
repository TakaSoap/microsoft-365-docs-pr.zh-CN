---
title: 优化防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理员可以了解如何在 Microsoft 365 中确定仿冒邮件的原因以及在将来阻止更多网络钓鱼邮件的原因。
ms.openlocfilehash: a9b7a58f32fd14c157d72e8f91a1f1b8bfe3aedc
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208581"
---
# <a name="tune-anti-phishing-protection"></a><span data-ttu-id="5b101-103">优化防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="5b101-103">Tune anti-phishing protection</span></span>

<span data-ttu-id="5b101-104">尽管 Microsoft 365 提供了在默认情况下启用的各种反网络钓鱼功能，但有些网络钓鱼邮件仍可能会到达您的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b101-104">Although Microsoft 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="5b101-105">本主题介绍您可以执行哪些操作来发现仿冒邮件的访问原因，以及您可以采取什么措施来调整 Microsoft 365 组织中的反网络钓鱼设置，_而不会意外地使事情更糟_。</span><span class="sxs-lookup"><span data-stu-id="5b101-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Microsoft 365 organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="5b101-106">首先要做的第一件事：处理任何受损帐户，并确保阻止任何更多的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="5b101-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="5b101-107">如果收件人的帐户因仿冒邮件而受到威胁，请按照在[Microsoft 365 中响应已泄露电子邮件帐户中](responding-to-a-compromised-email-account.md)的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="5b101-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Microsoft 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="5b101-108">如果你的订阅包括高级威胁防护（ATP），则可以使用[Office 365 威胁智能](office-365-ti.md)标识也收到网络钓鱼邮件的其他用户。</span><span class="sxs-lookup"><span data-stu-id="5b101-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="5b101-109">您还可以使用其他选项阻止网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="5b101-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="5b101-110">ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="5b101-110">ATP Safe Links</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="5b101-111">ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="5b101-111">ATP Safe Attachments</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="5b101-112">[Microsoft 365 中的 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5b101-112">[ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="5b101-113">请注意，可以暂时将策略中的**高级网络钓鱼阈值**从**Standard**提高到**主动**、**更主动**或**最严格**的。</span><span class="sxs-lookup"><span data-stu-id="5b101-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="5b101-114">验证这些 ATP 功能是否已打开。</span><span class="sxs-lookup"><span data-stu-id="5b101-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="5b101-115">向 Microsoft 报告网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="5b101-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="5b101-116">在调整用于保护 Microsoft 365 中所有客户的筛选器时，报告网络钓鱼邮件非常有帮助。</span><span class="sxs-lookup"><span data-stu-id="5b101-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Microsoft 365.</span></span> <span data-ttu-id="5b101-117">有关说明，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="5b101-117">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="5b101-118">检查邮件头</span><span class="sxs-lookup"><span data-stu-id="5b101-118">Inspect the message headers</span></span>

<span data-ttu-id="5b101-119">您可以检查网络钓鱼邮件的标头，以查看是否有任何可以执行的操作，以防止更多的网络钓鱼邮件进入。</span><span class="sxs-lookup"><span data-stu-id="5b101-119">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="5b101-120">换句话说，检查邮件头可以帮助您确定组织中负责允许网络钓鱼邮件的任何设置。</span><span class="sxs-lookup"><span data-stu-id="5b101-120">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="5b101-121">具体来说，应检查邮件头中的**X-Forefront-反垃圾邮件报告**标头字段，以了解垃圾邮件筛选判定（SFV）值中跳过的垃圾邮件或网络钓鱼筛选的指示。</span><span class="sxs-lookup"><span data-stu-id="5b101-121">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="5b101-122">跳过筛选的邮件将具有一个条目 `SCL:-1` ，这意味着您的设置允许此邮件通过覆盖由该服务确定的垃圾邮件或网络钓鱼 verdicts。</span><span class="sxs-lookup"><span data-stu-id="5b101-122">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="5b101-123">有关如何获取邮件头以及所有可用反垃圾邮件和反网络钓鱼邮件头的完整列表的详细信息，请参阅[Microsoft 365 中的反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="5b101-123">For more information on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="5b101-124">保持受保护状态的最佳做法</span><span class="sxs-lookup"><span data-stu-id="5b101-124">Best practices to stay protected</span></span>

- <span data-ttu-id="5b101-125">在每月的基础上，运行[安全分数](../mtp/microsoft-secure-score.md)以评估组织的安全设置。</span><span class="sxs-lookup"><span data-stu-id="5b101-125">On a monthly basis, run [Secure Score](../mtp/microsoft-secure-score.md) to assess your organization's security settings.</span></span>

- <span data-ttu-id="5b101-126">定期查看[欺骗智能报告](learn-about-spoof-intelligence.md)并[将欺骗智能配置](set-up-anti-phishing-policies.md#spoof-settings)为**隔离**可疑邮件，而不是将其传递到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5b101-126">Periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md) and [configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings) to **Quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="5b101-127">定期查看[威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="5b101-127">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="5b101-128">某些客户通过将自己的域放在反垃圾邮件策略中的 "允许发件人" 或 "允许域" 列表中，在无意中允许网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="5b101-128">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="5b101-129">如果选择执行此操作，则必须小心使用。</span><span class="sxs-lookup"><span data-stu-id="5b101-129">If you choose to do this, you must use extreme caution.</span></span> <span data-ttu-id="5b101-130">虽然此配置允许某些合法邮件通过，但它还会允许垃圾邮件和/或网络钓鱼筛选器通常会阻止的恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="5b101-130">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the spam and/or phish filters.</span></span>

  <span data-ttu-id="5b101-131">处理由 Microsoft 365 （误报）阻止的合法邮件（涉及域中的发件人）的最佳方式是在 DNS 中为_所有_电子邮件域完全且完整地配置 SPF、DKIM 和 DMARC 记录：</span><span class="sxs-lookup"><span data-stu-id="5b101-131">The best way to deal with legitimate messages that are blocked by Microsoft 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains:</span></span>

  - <span data-ttu-id="5b101-132">验证您的 SPF 记录是否标识了您的域中的发件人的_所有_电子邮件源（不要忘记第三方服务！）。</span><span class="sxs-lookup"><span data-stu-id="5b101-132">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="5b101-133">使用硬故障（ \- ）以确保配置为这样做的电子邮件系统拒绝未经授权的发件人。</span><span class="sxs-lookup"><span data-stu-id="5b101-133">Use hard fail (\-) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="5b101-134">您可以使用[欺骗智能](learn-about-spoof-intelligence.md)来帮助标识使用您的域的发件人，以便您可以在 SPF 记录中包括授权的第三方发件人。</span><span class="sxs-lookup"><span data-stu-id="5b101-134">You can use [spoof intelligence](learn-about-spoof-intelligence.md) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="5b101-135">有关配置说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5b101-135">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="5b101-136">设置 SPF 以帮助防止欺骗</span><span class="sxs-lookup"><span data-stu-id="5b101-136">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="5b101-137">使用 DKIM 验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="5b101-137">Use DKIM to validate outbound email sent from your custom domain</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="5b101-138">使用 DMARC 验证电子邮件</span><span class="sxs-lookup"><span data-stu-id="5b101-138">Use DMARC to validate email</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="5b101-139">如果可能，我们建议您将域的电子邮件直接传递到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5b101-139">Whenever possible, we recommend that you deliver email for your domain directly to Microsoft 365.</span></span> <span data-ttu-id="5b101-140">换句话说，将 Microsoft 365 域的 MX 记录指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5b101-140">In other words, point your Microsoft 365 domain's MX record to Microsoft 365.</span></span> <span data-ttu-id="5b101-141">Exchange Online Protection （EOP）能够在将其邮件直接传递到 Microsoft 365 时为你的云用户提供最佳保护。</span><span class="sxs-lookup"><span data-stu-id="5b101-141">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Microsoft 365.</span></span> <span data-ttu-id="5b101-142">如果必须在 EOP 前面使用第三方电子邮件清洁系统，请对连接器使用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="5b101-142">If you must use a third-party email hygiene system in front of EOP, use Enhanced Filtering for Connectors.</span></span> <span data-ttu-id="5b101-143">有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="5b101-143">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="5b101-144">多重因素身份验证（MFA）是防止受损帐户的一种不错的方法。</span><span class="sxs-lookup"><span data-stu-id="5b101-144">Multi factor authentication (MFA) is a good way to prevent compromised accounts.</span></span> <span data-ttu-id="5b101-145">强烈考虑为所有用户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="5b101-145">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="5b101-146">对于分阶段的方法，先在为每个人启用 MFA 之前为最敏感的用户（管理员、高级管理人员等）启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="5b101-146">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="5b101-147">有关说明，请参阅[设置多因素身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="5b101-147">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="5b101-148">将规则转发给外部收件人通常由攻击者用来提取数据。</span><span class="sxs-lookup"><span data-stu-id="5b101-148">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="5b101-149">使用 "审阅[Microsoft 安全分数](../mtp/microsoft-secure-score.md)中的**邮箱转发规则**" 信息查找甚至阻止外部收件人的转发规则。</span><span class="sxs-lookup"><span data-stu-id="5b101-149">Use the **Review mailbox forwarding rules** information in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="5b101-150">有关详细信息，请参阅[通过安全分数缓解客户端外部转发规则](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。</span><span class="sxs-lookup"><span data-stu-id="5b101-150">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).</span></span>
