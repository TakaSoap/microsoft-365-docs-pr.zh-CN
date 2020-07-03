---
title: 使用 DMARC 验证电子邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: 了解如何配置基于域的邮件身份验证、报告和一致性 (DMARC) 以验证从你的组织发送的邮件。
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016316"
---
# <a name="use-dmarc-to-validate-email"></a><span data-ttu-id="4eb7e-103">使用 DMARC 验证电子邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-103">Use DMARC to validate email</span></span>

<span data-ttu-id="4eb7e-104">基于域的邮件身份验证、报告和一致性 ([DMARC](https://dmarc.org)) 与发件人策略框架 (SPF) 和域密钥识别邮件 (DKIM) 结合使用，以验证邮件发件人并确保目标电子邮件系统信任从你的域发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-104">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="4eb7e-105">实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="4eb7e-106">DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>

> [!TIP]
> <span data-ttu-id="4eb7e-107">请访问 [Microsoft 智能安全协会 (MISA)](https://www.microsoft.com/misapartnercatalog) 目录，查看哪些第三方供应商提供 Microsoft 365 的 DMARC 报告。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-107">Visit the [Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog) catalog to view third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a><span data-ttu-id="4eb7e-108">SPF 和 DMARC 如何协同工作来保护 Microsoft 365 中的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="4eb7e-108">How do SPF and DMARC work together to protect email in Microsoft 365?</span></span>

 <span data-ttu-id="4eb7e-109">电子邮件可能包含多个发送方、发件人或地址。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-109">An email message may contain multiple originator, or sender, addresses.</span></span> <span data-ttu-id="4eb7e-110">这些地址用于不同用途。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-110">These addresses are used for different purposes.</span></span> <span data-ttu-id="4eb7e-111">例如，以下列地址为例：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-111">For example, consider these addresses:</span></span>

- <span data-ttu-id="4eb7e-112">**“邮件发件人”地址**：标识发件人，并指定在传送邮件过程中出现任何问题（例如未送达通知）时发送返回通知的地址。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-112">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="4eb7e-113">该地址出现在电子邮件的信封部分，而电子邮件应用程序通常不显示此地址。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="4eb7e-114">有时称其为" 5321.MailFrom 地址"或"反向路径地址"。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>

- <span data-ttu-id="4eb7e-115">**“发件人”地址**：由邮件应用程序显示为发件人地址的地址。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-115">**"From" address**: The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="4eb7e-116">此地址标识电子邮件的作者。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-116">This address identifies the author of the email.</span></span> <span data-ttu-id="4eb7e-117">即，负责撰写邮件的个人或系统的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="4eb7e-118">有时也称其为"5322.From 地址"。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-118">This is sometimes called the 5322.From address.</span></span>

<span data-ttu-id="4eb7e-119">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-119">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain.</span></span> <span data-ttu-id="4eb7e-120">Normally, SPF checks are only performed against the 5321.MailFrom address.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-120">Normally, SPF checks are only performed against the 5321.MailFrom address.</span></span> <span data-ttu-id="4eb7e-121">This means that the 5322.From address is not authenticated when you use SPF by itself.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-121">This means that the 5322.From address is not authenticated when you use SPF by itself.</span></span> <span data-ttu-id="4eb7e-122">This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-122">This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address.</span></span> <span data-ttu-id="4eb7e-123">For example, consider this SMTP transcript:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-123">For example, consider this SMTP transcript:</span></span>

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

<span data-ttu-id="4eb7e-124">在此脚本中，发件人地址如下所示：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-124">In this transcript, the sender addresses are as follows:</span></span>

- <span data-ttu-id="4eb7e-125">邮件发件人地址 (5321.MailFrom)：phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4eb7e-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>

- <span data-ttu-id="4eb7e-126">发件人地址 (5322.From)：security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="4eb7e-126">From address (5322.From): security@woodgrovebank.com</span></span>

<span data-ttu-id="4eb7e-127">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-127">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com.</span></span> <span data-ttu-id="4eb7e-128">If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-128">If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes.</span></span> <span data-ttu-id="4eb7e-129">Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-129">Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com.</span></span> <span data-ttu-id="4eb7e-130">With SPF alone, the validity of woodgrovebank.com was never authenticated.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-130">With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>

<span data-ttu-id="4eb7e-131">When you use DMARC, the receiving server also performs a check against the From address.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-131">When you use DMARC, the receiving server also performs a check against the From address.</span></span> <span data-ttu-id="4eb7e-132">In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-132">In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>

## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="4eb7e-133">什么是 DMARC TXT 记录？</span><span class="sxs-lookup"><span data-stu-id="4eb7e-133">What is a DMARC TXT record?</span></span>

<span data-ttu-id="4eb7e-134">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-134">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing.</span></span> <span data-ttu-id="4eb7e-135">You publish DMARC TXT records in DNS.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-135">You publish DMARC TXT records in DNS.</span></span> <span data-ttu-id="4eb7e-136">DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-136">DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain.</span></span> <span data-ttu-id="4eb7e-137">The DMARC TXT record identifies authorized outbound email servers.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-137">The DMARC TXT record identifies authorized outbound email servers.</span></span> <span data-ttu-id="4eb7e-138">Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-138">Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>

<span data-ttu-id="4eb7e-139">Microsoft 的 DMARC TXT 记录如下所示：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-139">Microsoft's DMARC TXT record looks something like this:</span></span>

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

<span data-ttu-id="4eb7e-140">Microsoft 将其 DMARC 报告发送至 [Agari](https://agari.com)（第三方）。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-140">Microsoft sends its DMARC reports to [Agari](https://agari.com), a third party.</span></span> <span data-ttu-id="4eb7e-141">Agari 收集并分析 DMARC 报告。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-141">Agari collects and analyzes DMARC reports.</span></span> <span data-ttu-id="4eb7e-142">请访问 [MISA 目录](https://www.microsoft.com/misapartnercatalog)，查看有哪些更多的第三方供应商提供 Microsoft 365 的 DMARC 报告。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-142">Please visit the [MISA catalog](https://www.microsoft.com/misapartnercatalog) to view more third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="4eb7e-143">为入站邮件实现 DMARC</span><span class="sxs-lookup"><span data-stu-id="4eb7e-143">Implement DMARC for inbound mail</span></span>

<span data-ttu-id="4eb7e-144">You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-144">You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365.</span></span> <span data-ttu-id="4eb7e-145">We've taken care of everything for you.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-145">We've taken care of everything for you.</span></span> <span data-ttu-id="4eb7e-146">If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-146">If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</span></span>

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a><span data-ttu-id="4eb7e-147">从 Microsoft 365 中为出站邮件实现 DMARC</span><span class="sxs-lookup"><span data-stu-id="4eb7e-147">Implement DMARC for outbound mail from Microsoft 365</span></span>

<span data-ttu-id="4eb7e-148">If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-148">If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization.</span></span> <span data-ttu-id="4eb7e-149">SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-149">SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail.</span></span> <span data-ttu-id="4eb7e-150">For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-150">For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

 <span data-ttu-id="4eb7e-151">If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-151">If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail.</span></span> <span data-ttu-id="4eb7e-152">Implementing DMARC for your custom domain includes these steps:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-152">Implementing DMARC for your custom domain includes these steps:</span></span>

- [<span data-ttu-id="4eb7e-153">步骤 1：为域标识邮件的有效源</span><span class="sxs-lookup"><span data-stu-id="4eb7e-153">Step 1: Identify valid sources of mail for your domain</span></span>](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [<span data-ttu-id="4eb7e-154">步骤 2：为域设置 SPF</span><span class="sxs-lookup"><span data-stu-id="4eb7e-154">Step 2: Set up SPF for your domain</span></span>](#step-2-set-up-spf-for-your-domain)

- [<span data-ttu-id="4eb7e-155">步骤3：为自定义域设置 DKIM</span><span class="sxs-lookup"><span data-stu-id="4eb7e-155">Step 3: Set up DKIM for your custom domain</span></span>](#step-3-set-up-dkim-for-your-custom-domain)

- [<span data-ttu-id="4eb7e-156">步骤 4：为域生成 DMARC TXT 记录</span><span class="sxs-lookup"><span data-stu-id="4eb7e-156">Step 4: Form the DMARC TXT record for your domain</span></span>](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="4eb7e-157">步骤 1：为域标识邮件的有效源</span><span class="sxs-lookup"><span data-stu-id="4eb7e-157">Step 1: Identify valid sources of mail for your domain</span></span>

<span data-ttu-id="4eb7e-158">If you have already set up SPF then you have already gone through this exercise.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-158">If you have already set up SPF then you have already gone through this exercise.</span></span> <span data-ttu-id="4eb7e-159">However, for DMARC, there are additional considerations.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-159">However, for DMARC, there are additional considerations.</span></span> <span data-ttu-id="4eb7e-160">When identifying sources of mail for your domain there are two questions you need to answer:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-160">When identifying sources of mail for your domain there are two questions you need to answer:</span></span>

- <span data-ttu-id="4eb7e-161">哪些 IP 地址从我的域发送邮件？</span><span class="sxs-lookup"><span data-stu-id="4eb7e-161">What IP addresses send messages from my domain?</span></span>

- <span data-ttu-id="4eb7e-162">对于第三方代表我发送的邮件，5321.MailFrom 和 5322.From 域会匹配吗？</span><span class="sxs-lookup"><span data-stu-id="4eb7e-162">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>

### <a name="step-2-set-up-spf-for-your-domain"></a><span data-ttu-id="4eb7e-163">步骤 2：为域设置 SPF</span><span class="sxs-lookup"><span data-stu-id="4eb7e-163">Step 2: Set up SPF for your domain</span></span>

<span data-ttu-id="4eb7e-164">既然你拥有了所有的有效发件人的列表，你可以按照步骤[设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-164">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

<span data-ttu-id="4eb7e-165">例如，假定 contoso.com 从 Exchange Online 中发送邮件，本地 Exchange 服务器的 IP 地址是 192.168.0.1，并且 Web 应用程序的 IP 地址是 192.168.100.100，则 SPF TXT 记录将如下所示：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-165">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="4eb7e-166">作为最佳做法，请确保 SPF TXT 记录考虑第三方发件人。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-166">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a><span data-ttu-id="4eb7e-167">步骤 3：为自定义域设置 DKIM</span><span class="sxs-lookup"><span data-stu-id="4eb7e-167">Step 3: Set up DKIM for your custom domain</span></span>

<span data-ttu-id="4eb7e-168">Once you have set up SPF, you need to set up DKIM.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-168">Once you have set up SPF, you need to set up DKIM.</span></span> <span data-ttu-id="4eb7e-169">DKIM lets you add a digital signature to email messages in the message header.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-169">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="4eb7e-170">If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-170">If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail.</span></span> <span data-ttu-id="4eb7e-171">This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-171">This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain.</span></span> <span data-ttu-id="4eb7e-172">This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-172">This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>

<span data-ttu-id="4eb7e-173">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-173">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email.</span></span> <span data-ttu-id="4eb7e-174">To avoid this, you need to set up DKIM for your domain specifically with that third-party sender.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-174">To avoid this, you need to set up DKIM for your domain specifically with that third-party sender.</span></span> <span data-ttu-id="4eb7e-175">This allows Microsoft 365 to authenticate email from this 3rd-party service.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-175">This allows Microsoft 365 to authenticate email from this 3rd-party service.</span></span> <span data-ttu-id="4eb7e-176">However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-176">However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you.</span></span> <span data-ttu-id="4eb7e-177">This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-177">This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>

<span data-ttu-id="4eb7e-178">有关为域设置 DKIM 的说明，包括如何为第三方发件人设置 DKIM，以便他们可以欺骗你的域，请参阅[使用 DKIM 验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-178">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a><span data-ttu-id="4eb7e-179">步骤 4：为域生成 DMARC TXT 记录</span><span class="sxs-lookup"><span data-stu-id="4eb7e-179">Step 4: Form the DMARC TXT record for your domain</span></span>

<span data-ttu-id="4eb7e-180">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-180">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365.</span></span> <span data-ttu-id="4eb7e-181">Form the DMARC TXT record for your domain in the format:</span><span class="sxs-lookup"><span data-stu-id="4eb7e-181">Form the DMARC TXT record for your domain in the format:</span></span>

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

<span data-ttu-id="4eb7e-182">其中：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-182">where:</span></span>

- <span data-ttu-id="4eb7e-183">*域*是你想要保护的域。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-183">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="4eb7e-184">默认情况下，该记录可保护从该域和所有子域发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-184">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="4eb7e-185">例如，如果指定 \_dmarc.contoso.com，那么 DMARC 会保护从该域和所有子域（例如 housewares.contoso.com 或 plumbing.contoso.com）发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-185">For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span>

- <span data-ttu-id="4eb7e-186">*TTL* should always be the equivalent of one hour.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-186">*TTL* should always be the equivalent of one hour.</span></span> <span data-ttu-id="4eb7e-187">The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-187">The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span>

- <span data-ttu-id="4eb7e-188">pct=100\*\* 表示此规则应该用于所有的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-188">*pct=100* indicates that this rule should be used for 100% of email.</span></span>

- <span data-ttu-id="4eb7e-189">*policy* specifies what policy you want the receiving server to follow if DMARC fails.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-189">*policy* specifies what policy you want the receiving server to follow if DMARC fails.</span></span> <span data-ttu-id="4eb7e-190">You can set the policy to none, quarantine, or reject.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-190">You can set the policy to none, quarantine, or reject.</span></span>

<span data-ttu-id="4eb7e-191">有关要使用的选项的信息，请熟悉[在 Microsoft 365 中实现 DMARC 的最佳做法](#best-practices-for-implementing-dmarc-in-microsoft-365)中的概念。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-191">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).</span></span>

<span data-ttu-id="4eb7e-192">示例：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-192">Examples:</span></span>

- <span data-ttu-id="4eb7e-193">策略设置为无</span><span class="sxs-lookup"><span data-stu-id="4eb7e-193">Policy set to none</span></span>

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="4eb7e-194">策略设置为隔离</span><span class="sxs-lookup"><span data-stu-id="4eb7e-194">Policy set to quarantine</span></span>

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="4eb7e-195">策略设置为拒绝</span><span class="sxs-lookup"><span data-stu-id="4eb7e-195">Policy set to reject</span></span>

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="4eb7e-196">Once you have formed your record, you need to update the record at your domain registrar.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span> <span data-ttu-id="4eb7e-197">For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-197">For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a><span data-ttu-id="4eb7e-198">在 Microsoft 365 中实现 DMARC 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4eb7e-198">Best practices for implementing DMARC in Microsoft 365</span></span>

<span data-ttu-id="4eb7e-199">You can implement DMARC gradually without impacting the rest of your mail flow.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-199">You can implement DMARC gradually without impacting the rest of your mail flow.</span></span> <span data-ttu-id="4eb7e-200">Create and implement a roll out plan that follows these steps.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-200">Create and implement a roll out plan that follows these steps.</span></span> <span data-ttu-id="4eb7e-201">Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-201">Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>

1. <span data-ttu-id="4eb7e-202">监视实现 DMARC 的影响</span><span class="sxs-lookup"><span data-stu-id="4eb7e-202">Monitor the impact of implementing DMARC</span></span>

    <span data-ttu-id="4eb7e-203">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-203">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain.</span></span> <span data-ttu-id="4eb7e-204">A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-204">A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none).</span></span> <span data-ttu-id="4eb7e-205">Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-205">Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span>

    <span data-ttu-id="4eb7e-206">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-206">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure.</span></span> <span data-ttu-id="4eb7e-207">However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-207">However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM.</span></span> <span data-ttu-id="4eb7e-208">As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-208">As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't.</span></span> <span data-ttu-id="4eb7e-209">You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-209">You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems.</span></span> <span data-ttu-id="4eb7e-210">You'll also begin to see how many fraudulent messages are being sent, and from where.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-210">You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>

2. <span data-ttu-id="4eb7e-211">请求外部邮件系统隔离未通过 DMARC 的邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-211">Request that external mail systems quarantine mail that fails DMARC</span></span>

    <span data-ttu-id="4eb7e-212">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-212">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy.</span></span> <span data-ttu-id="4eb7e-213">A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-213">A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine).</span></span> <span data-ttu-id="4eb7e-214">By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-214">By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>

3. <span data-ttu-id="4eb7e-215">请求外部邮件系统不接受未通过 DMARC 的邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-215">Request that external mail systems not accept messages that fail DMARC</span></span>

    <span data-ttu-id="4eb7e-216">The final step is implementing a reject policy.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-216">The final step is implementing a reject policy.</span></span> <span data-ttu-id="4eb7e-217">A reject policy is a DMARC TXT record that has its policy set to reject (p=reject).</span><span class="sxs-lookup"><span data-stu-id="4eb7e-217">A reject policy is a DMARC TXT record that has its policy set to reject (p=reject).</span></span> <span data-ttu-id="4eb7e-218">When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-218">When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span>

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="4eb7e-219">Microsoft 365 如何处理未通过 DMARC 的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-219">How Microsoft 365 handles outbound email that fails DMARC</span></span>

<span data-ttu-id="4eb7e-220">如果邮件是从 Microsoft 365 出站的而且未通过 DMARC，并且你已将策略设置为 p=quarantine 或 p=reject，则该邮件通过[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)进行路由。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-220">If a message is outbound from Microsoft 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="4eb7e-221">出站电子邮件不存在任何替代方法。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-221">There is no override for outbound email.</span></span>

<span data-ttu-id="4eb7e-222">If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-222">If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service.</span></span> <span data-ttu-id="4eb7e-223">However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-223">However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service.</span></span> <span data-ttu-id="4eb7e-224">This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-224">This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="4eb7e-225">Microsoft 365 如何处理未通过 DMARC 的入站电子邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-225">How Microsoft 365 handles inbound email that fails DMARC</span></span>

<span data-ttu-id="4eb7e-226">如果发送服务器的 DMARC 策略是 `p=reject`，则 EOP 会将该邮件标记为欺骗，而不是拒绝它。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-226">If the DMARC policy of the sending server is `p=reject`, EOP marks the message as spoof instead of rejecting it.</span></span> <span data-ttu-id="4eb7e-227">换句话说，对于入站电子邮件，Microsoft 365 将 `p=reject` 和 `p=quarantine` 视为相同方式。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-227">In other words, for inbound email, Microsoft 365 treats `p=reject` and `p=quarantine` the same way.</span></span> <span data-ttu-id="4eb7e-228">管理员可以定义对[反网络钓鱼策略](set-up-anti-phishing-policies.md)中分类为欺骗的邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-228">Admins can define the action to take on messages classified as spoof within the [anti-phishing policy](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="4eb7e-229">之所以像这样配置 Microsoft 365，是因为某些合法的电子邮件可能会无法通过 DMARC。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-229">Microsoft 365 is configured like this because some legitimate email may fail DMARC.</span></span> <span data-ttu-id="4eb7e-230">例如，如果将邮件发送到一个邮件列表，然后将其中继到所有列表参与者，则该邮件可能无法通过 DMARC。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-230">For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants.</span></span> <span data-ttu-id="4eb7e-231">如果 Microsoft 365 拒绝这些邮件，人们可能会丢失合法的电子邮件，而且无法进行检索。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-231">If Microsoft 365 rejected these messages, people could lose legitimate email and have no way to retrieve it.</span></span> <span data-ttu-id="4eb7e-232">相反，这些邮件仍然无法通过 DMARC，但会将其标记为垃圾邮件而不是拒绝。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-232">Instead, these messages will still fail DMARC but they will be marked as spam and not rejected.</span></span> <span data-ttu-id="4eb7e-233">如果需要，用户仍可以在其收件箱中获得这些邮件，方法如下：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-233">If desired, users can still get these messages in their inbox through these methods:</span></span>

- <span data-ttu-id="4eb7e-234">用户使用其电子邮件客户端分别添加安全发件人。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-234">Users add safe senders individually by using their email client.</span></span>

- <span data-ttu-id="4eb7e-235">管理员可更新[欺骗智能](learn-about-spoof-intelligence.md)报告，以允许欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-235">Administrators can update the [Spoof Intelligence](learn-about-spoof-intelligence.md) reporting to allow the spoof.</span></span>

- <span data-ttu-id="4eb7e-236">管理员创建一个适用于所有用户的 Exchange 邮件流规则（也称为传输规则），允许那些特定发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-236">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span>

<span data-ttu-id="4eb7e-237">有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-237">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a><span data-ttu-id="4eb7e-238">Microsoft 365 如何使用经过身份验证的接收链 (ARC)</span><span class="sxs-lookup"><span data-stu-id="4eb7e-238">How Microsoft 365 utilizes Authenticated Received Chain (ARC)</span></span>

<span data-ttu-id="4eb7e-239">Microsoft 365 中的所有托管邮箱都将获得 ARC 的优势，实现改进的邮件可传递性和增强的反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-239">All hosted mailboxes in Microsoft 365 will now gain the benefit of ARC with improved deliverability of messages and enhanced anti-spoofing protection.</span></span> <span data-ttu-id="4eb7e-240">当电子邮件从始发服务器路由到收件人邮箱时，ARC 将保留来自所有参与中介或跃点的电子邮件身份验证结果。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-240">ARC preserves the email authentication results from all participating intermediaries, or hops, when an email is routed from the originating server to the recipient mailbox.</span></span> <span data-ttu-id="4eb7e-241">在采用 ARC 之前，电子邮件路由中的中介执行的修改（如转发规则或自动签名）可能会在电子邮件到达收件人邮箱时导致 DMARC 故障。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-241">Before ARC, modifications performed by intermediaries in email routing, like forwarding rules or automatic signatures, could cause DMARC failures by the time the email reached the recipient mailbox.</span></span> <span data-ttu-id="4eb7e-242">有了 ARC 之后，身份验证结果的加密保留使得 Microsoft 365 能够验证电子邮件发件人的真伪。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-242">With ARC, the cryptographic preservation of the authentication results allows Microsoft 365 to verify the authenticity of an email's sender.</span></span>

<span data-ttu-id="4eb7e-243">目前，当 Microsoft 是 ARC 保护方时，Microsoft 365 会利用 ARC 来验证身份验证结果，但计划在将来添加对第三方 ARC 保护方的支持。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-243">Microsoft 365 currently utilizes ARC to verify authentication results when Microsoft is the ARC Sealer, but plan to add support for third party ARC sealers in the future.</span></span>

## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="4eb7e-244">DMARC 实现疑难解答</span><span class="sxs-lookup"><span data-stu-id="4eb7e-244">Troubleshooting your DMARC implementation</span></span>

<span data-ttu-id="4eb7e-245">如果你已配置了域的 MX 记录，其中 EOP 不是第一项，将不会为你的域强制执行 DMARC 失败。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-245">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span>

<span data-ttu-id="4eb7e-246">如果你是 客户，并且你的域的主 MX 记录不指向 EOP，你将不会获得 DMARC 的好处。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-246">If you're a customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC.</span></span> <span data-ttu-id="4eb7e-247">例如，如果你将 MX 记录指向你的本地邮件服务器，然后使用连接器将电子邮件路由到 EOP，则 DMARC 将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-247">For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector.</span></span> <span data-ttu-id="4eb7e-248">在这种情况下，接收域是一个接受的域，但 EOP 不是主 MX。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-248">In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX.</span></span> <span data-ttu-id="4eb7e-249">例如，假设 contoso.com 本身指向其 MX 并将 EOP 用作辅助 MX 记录，contoso.com 的 MX 记录将如下所示：</span><span class="sxs-lookup"><span data-stu-id="4eb7e-249">For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="4eb7e-250">由于它是主 MX，全部或大部分电子邮件将首先被路由到 mail.contoso.com，然后将邮件路由到 EOP。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-250">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="4eb7e-251">在某些情况下，你甚至不可能将 EOP 列为 MX 记录，并直接挂接连接器来路由你的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-251">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="4eb7e-252">EOP 不必是执行 DMARC 验证的第一个条目。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-252">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="4eb7e-253">它只是确保验证，因为我们不能确定所有本地/非 O365 服务器都将执行 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-253">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="4eb7e-254">设置 DMARC TXT 记录时，可以对客户的域（而不是服务器）强制执行 DMARC，但是实际上强制执行取决于接收服务器。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-254">DMARC is eligible to be enforced for a customer's domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="4eb7e-255">如果将 EOP 设置为接收服务器，那么 EOP 强制执行 DMARC。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-255">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC 的疑难解答图形，由 Daniel Mande 提供":::

## <a name="for-more-information"></a><span data-ttu-id="4eb7e-257">详细信息</span><span class="sxs-lookup"><span data-stu-id="4eb7e-257">For more information</span></span>

<span data-ttu-id="4eb7e-258">Want more information about DMARC?</span><span class="sxs-lookup"><span data-stu-id="4eb7e-258">Want more information about DMARC?</span></span> <span data-ttu-id="4eb7e-259">These resources can help.</span><span class="sxs-lookup"><span data-stu-id="4eb7e-259">These resources can help.</span></span>

- <span data-ttu-id="4eb7e-260">[反垃圾邮件邮件头](anti-spam-message-headers.md) 包括 Microsoft 365 执行 DMARC 检查时使用的语法和标头字段。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-260">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DMARC checks.</span></span>

- <span data-ttu-id="4eb7e-261">参加 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG（消息、恶意软件、移动反滥用工作组）提供的 <sup>DMARC 培训系列</sup>。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-261">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>

- <span data-ttu-id="4eb7e-262">使用检查表，位于 [dmarcian](https://space.dmarcian.com/deployment/)。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-262">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>

- <span data-ttu-id="4eb7e-263">直接访问源，位于 [DMARC.org](https://dmarc.org)。</span><span class="sxs-lookup"><span data-stu-id="4eb7e-263">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>

## <a name="see-also"></a><span data-ttu-id="4eb7e-264">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4eb7e-264">See also</span></span>

[<span data-ttu-id="4eb7e-265">Microsoft 365 如何使用发件人策略框架 (SPF) 来防止欺骗</span><span class="sxs-lookup"><span data-stu-id="4eb7e-265">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

[<span data-ttu-id="4eb7e-266">在 Microsoft 365 中设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="4eb7e-266">Set up SPF in Microsoft 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[<span data-ttu-id="4eb7e-267">使用 DKIM 在 Microsoft 365 中验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="4eb7e-267">Use DKIM to validate outbound email sent from your custom domain in Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md)
