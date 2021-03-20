---
title: 优化防钓鱼保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 管理员可以了解在 Microsoft 365 中通过网络钓鱼邮件的原因和方式，以及在将来如何防止更多网络钓鱼邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84159ef08324ed0a895d84e6c9c19f429e227fa1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908134"
---
# <a name="tune-anti-phishing-protection"></a><span data-ttu-id="008f6-103">优化防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="008f6-103">Tune anti-phishing protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="008f6-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="008f6-104">**Applies to**</span></span>
- [<span data-ttu-id="008f6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="008f6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="008f6-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="008f6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="008f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="008f6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="008f6-108">尽管 Microsoft 365 附带了各种默认情况下启用的防钓鱼功能，但某些网络钓鱼邮件可能仍可以到达你的邮箱。</span><span class="sxs-lookup"><span data-stu-id="008f6-108">Although Microsoft 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="008f6-109">本主题介绍您可以执行哪些操作来发现网络钓鱼邮件通过的原因，以及您可以如何调整 Microsoft 365 组织的反网络钓鱼设置，而不会意外使情况变得 _更糟_。</span><span class="sxs-lookup"><span data-stu-id="008f6-109">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Microsoft 365 organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="008f6-110">首先：处理任何遭到入侵的帐户，并确保阻止更多网络钓鱼邮件通过</span><span class="sxs-lookup"><span data-stu-id="008f6-110">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="008f6-111">如果收件人的帐户由于网络钓鱼邮件而泄露，请按照在 [Microsoft 365](responding-to-a-compromised-email-account.md)中响应遭到入侵的电子邮件帐户中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="008f6-111">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Microsoft 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="008f6-112">如果你的订阅包含适用于 Office 365 的 Microsoft Defender，可以使用 [Office 365](office-365-ti.md) 威胁智能来识别还收到网络钓鱼邮件的其他用户。</span><span class="sxs-lookup"><span data-stu-id="008f6-112">If your subscription includes Microsoft Defender for Office 365, you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="008f6-113">有其他选项可以阻止钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="008f6-113">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="008f6-114">Microsoft Defender for Office 365 中的安全链接</span><span class="sxs-lookup"><span data-stu-id="008f6-114">Safe Links in Microsoft Defender for Office 365</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="008f6-115">Microsoft Defender for Office 365 中的安全附件</span><span class="sxs-lookup"><span data-stu-id="008f6-115">Safe Attachments in Microsoft Defender for Office 365</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="008f6-116">[Microsoft Defender for Office 365 中的防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="008f6-116">[Anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="008f6-117">请注意，你可以暂时将策略中的高级网络钓鱼阈值从 **"标准**"提高为 **"主动**"、更 **主动** 或 **最具有攻击性**。</span><span class="sxs-lookup"><span data-stu-id="008f6-117">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="008f6-118">验证这些 Defender for Office 365 功能是否打开。</span><span class="sxs-lookup"><span data-stu-id="008f6-118">Verify these Defender for Office 365 features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="008f6-119">向 Microsoft 报告网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="008f6-119">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="008f6-120">报告网络钓鱼邮件有助于优化用于保护 Microsoft 365 中所有客户的筛选器。</span><span class="sxs-lookup"><span data-stu-id="008f6-120">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Microsoft 365.</span></span> <span data-ttu-id="008f6-121">有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="008f6-121">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="008f6-122">检查邮件头</span><span class="sxs-lookup"><span data-stu-id="008f6-122">Inspect the message headers</span></span>

<span data-ttu-id="008f6-123">你可以检查网络钓鱼邮件的邮件头，看看是否有自己能够阻止更多网络钓鱼邮件通过的内容。</span><span class="sxs-lookup"><span data-stu-id="008f6-123">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="008f6-124">换句话说，检查邮件头可以帮助您识别组织中负责允许网络钓鱼邮件进入的任何设置。</span><span class="sxs-lookup"><span data-stu-id="008f6-124">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="008f6-125">具体来说，应检查邮件头中的 **X-Forefront-Antispam-Report** 头字段，以在 SFV 垃圾邮件筛选裁定 (值中指示已跳过对垃圾邮件或网络钓鱼) 筛选。</span><span class="sxs-lookup"><span data-stu-id="008f6-125">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped filtering for spam or phishing in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="008f6-126">跳过筛选的邮件将具有 的条目，这意味着你的其中一个设置允许通过覆盖由服务确定的垃圾邮件或网络钓鱼 `SCL:-1` 裁定来传递此邮件。</span><span class="sxs-lookup"><span data-stu-id="008f6-126">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phishing verdicts that were determined by the service.</span></span> <span data-ttu-id="008f6-127">若要详细了解如何获取邮件头以及所有可用反垃圾邮件和反网络钓鱼邮件头的完整列表，请参阅 [Microsoft 365](anti-spam-message-headers.md)中的反垃圾邮件邮件头。</span><span class="sxs-lookup"><span data-stu-id="008f6-127">For more information on how to get message headers and the complete list of all available anti-spam and anti-phishing message headers, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="008f6-128">保持受保护状态的最佳方案</span><span class="sxs-lookup"><span data-stu-id="008f6-128">Best practices to stay protected</span></span>

- <span data-ttu-id="008f6-129">每月运行安全 [分数](../mtp/microsoft-secure-score.md) 来评估组织的安全设置。</span><span class="sxs-lookup"><span data-stu-id="008f6-129">On a monthly basis, run [Secure Score](../mtp/microsoft-secure-score.md) to assess your organization's security settings.</span></span>

- <span data-ttu-id="008f6-130">对于错误地隔离的邮件，或允许通过的邮件，我们建议你在威胁资源管理器和实时检测中搜索这些 [邮件](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="008f6-130">For messages that end up in quarantine by mistake, or for messages that are allowed through, we recommend that you search for those messages in [Threat Explorer and real-time detections](threat-explorer.md).</span></span> <span data-ttu-id="008f6-131">可以按发件人、收件人或邮件 ID 进行搜索。</span><span class="sxs-lookup"><span data-stu-id="008f6-131">You can search by sender, recipient, or message ID.</span></span> <span data-ttu-id="008f6-132">找到邮件后，单击主题转到详细信息。</span><span class="sxs-lookup"><span data-stu-id="008f6-132">After you locate the message, go to details by clicking on the subject.</span></span> <span data-ttu-id="008f6-133">对于隔离的邮件，查看"检测技术"是什么，以便您可以使用适当的方法进行覆盖。</span><span class="sxs-lookup"><span data-stu-id="008f6-133">For a quarantined message, look to see what the "detection technology" was so that you can use the appropriate method to override.</span></span> <span data-ttu-id="008f6-134">对于允许的邮件，查看允许邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="008f6-134">For an allowed message, look to see which policy allowed the message.</span></span>

- <span data-ttu-id="008f6-135">欺骗邮件在 Defender for Office 365 中标记为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="008f6-135">Spoofed mail is tagged as phishing in Defender for Office 365.</span></span> <span data-ttu-id="008f6-136">有时欺骗是恶意的，有时用户不希望隔离它。</span><span class="sxs-lookup"><span data-stu-id="008f6-136">Sometimes spoof is benign, and sometimes users do not want it quarantined.</span></span> <span data-ttu-id="008f6-137">若要尽可能减少对用户的影响，请定期查看欺骗 [智能报告](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="008f6-137">To minimize impact to users, periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md).</span></span> <span data-ttu-id="008f6-138">查看并进行必要的替代后，你可以确信地将欺骗智能配置为隔离可疑邮件，[](set-up-anti-phishing-policies.md#spoof-settings)而不是将它们发送到用户的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="008f6-138">Once you have reviewed and made any necessary overrides, you can be confident to [configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings) to **Quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="008f6-139">您可以对域中或用户 (模拟重复上述) 。</span><span class="sxs-lookup"><span data-stu-id="008f6-139">You can repeat the above step for Impersonation (domain or user).</span></span> <span data-ttu-id="008f6-140">模拟报告位于威胁 **管理仪表板** \>  \> **见解下**。</span><span class="sxs-lookup"><span data-stu-id="008f6-140">The Impersonation report is found under **Threat Management** \> **Dashboard** \> **Insights**.</span></span>

- <span data-ttu-id="008f6-141">定期检查威胁 [防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="008f6-141">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="008f6-142">一些客户无意中允许网络钓鱼邮件通过，他们通过将自己的域放在反垃圾邮件策略的"允许发件人"或"允许域"列表中。</span><span class="sxs-lookup"><span data-stu-id="008f6-142">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="008f6-143">尽管此配置将允许某些合法邮件通过，但它还将允许通常被垃圾邮件和/或网络钓鱼筛选器阻止的恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="008f6-143">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the spam and/or phishing filters.</span></span> <span data-ttu-id="008f6-144">应纠正基础问题，而不是允许域。</span><span class="sxs-lookup"><span data-stu-id="008f6-144">Instead of allowing the domain, you should correct the underlying problem.</span></span>

  <span data-ttu-id="008f6-145">处理由 Microsoft 365 (误报) 阻止的合法邮件（涉及域中的发件人）的最好办法就是在所有电子邮件域的 DNS 中完全完全配置 SPF、DKIM 和 DMARC 记录： </span><span class="sxs-lookup"><span data-stu-id="008f6-145">The best way to deal with legitimate messages that are blocked by Microsoft 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains:</span></span>

  - <span data-ttu-id="008f6-146">验证 SPF 记录是否 _标识_ 域中发件人的所有电子邮件 (不要忘记第三方服务！) 。</span><span class="sxs-lookup"><span data-stu-id="008f6-146">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="008f6-147">使用硬 (所有) ，以确保未经授权的发件人被配置为拒绝的电子邮件 \- 系统拒绝。</span><span class="sxs-lookup"><span data-stu-id="008f6-147">Use hard fail (\-all) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="008f6-148">您可以使用 [欺骗智能](learn-about-spoof-intelligence.md) 来帮助识别正在使用你的域的发件人，以便可以在 SPF 记录中包括授权的第三方发件人。</span><span class="sxs-lookup"><span data-stu-id="008f6-148">You can use [spoof intelligence](learn-about-spoof-intelligence.md) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="008f6-149">有关配置说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="008f6-149">For configuration instructions, see:</span></span>

  - [<span data-ttu-id="008f6-150">设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="008f6-150">Set up SPF to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="008f6-151">使用 DKIM 验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="008f6-151">Use DKIM to validate outbound email sent from your custom domain</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="008f6-152">使用 DMARC 验证电子邮件</span><span class="sxs-lookup"><span data-stu-id="008f6-152">Use DMARC to validate email</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="008f6-153">建议尽可能将域的电子邮件直接发送到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="008f6-153">Whenever possible, we recommend that you deliver email for your domain directly to Microsoft 365.</span></span> <span data-ttu-id="008f6-154">换句话说，将 Microsoft 365 域的 MX 记录指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="008f6-154">In other words, point your Microsoft 365 domain's MX record to Microsoft 365.</span></span> <span data-ttu-id="008f6-155">Exchange Online Protection (EOP) 可以在邮件直接传递到 Microsoft 365 时为云用户提供最佳保护。</span><span class="sxs-lookup"><span data-stu-id="008f6-155">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Microsoft 365.</span></span> <span data-ttu-id="008f6-156">如果必须在 EOP 前面使用第三方电子邮件清洁系统，请使用增强的连接器筛选功能。</span><span class="sxs-lookup"><span data-stu-id="008f6-156">If you must use a third-party email hygiene system in front of EOP, use Enhanced Filtering for Connectors.</span></span> <span data-ttu-id="008f6-157">有关说明，请参阅 [增强的 Exchange Online 中的连接器筛选](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="008f6-157">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

- <span data-ttu-id="008f6-158">用户应该使用["报告邮件"](enable-the-report-message-add-in.md)加载项或"报告[](enable-the-report-phish-add-in.md)钓鱼邮件"加载项向 Microsoft 报告邮件，Microsoft 可以训练我们的系统。</span><span class="sxs-lookup"><span data-stu-id="008f6-158">Users should use the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to report messages to Microsoft, which can train our system.</span></span> <span data-ttu-id="008f6-159">管理员还应利用管理员 [提交](admin-submission.md) 功能。</span><span class="sxs-lookup"><span data-stu-id="008f6-159">Admins should also take advantage of [Admin Submission](admin-submission.md) capabilities.</span></span>

- <span data-ttu-id="008f6-160">使用 MFA (多重) 是防止帐户遭到入侵的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="008f6-160">Multi factor authentication (MFA) is a good way to prevent compromised accounts.</span></span> <span data-ttu-id="008f6-161">你应强烈建议为所有用户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="008f6-161">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="008f6-162">对于分阶段方法，首先为最敏感的用户 (管理员、主管人员等) ，然后再为所有人启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="008f6-162">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="008f6-163">有关说明，请参阅 [设置多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="008f6-163">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="008f6-164">向外部收件人转发规则通常被攻击者用来提取数据。</span><span class="sxs-lookup"><span data-stu-id="008f6-164">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="008f6-165">使用 [Microsoft](../mtp/microsoft-secure-score.md) **安全分数中的"** 审阅邮箱转发规则"信息查找甚至阻止将规则转发给外部收件人。</span><span class="sxs-lookup"><span data-stu-id="008f6-165">Use the **Review mailbox forwarding rules** information in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="008f6-166">有关详细信息，请参阅使用安全分数缓解客户端 [外部转发规则](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="008f6-166">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).</span></span>