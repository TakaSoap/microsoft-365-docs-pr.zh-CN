---
title: Microsoft 365 中的电子邮件身份验证
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 管理员可了解 Exchange Online Protection (EOP) 如何使用电子邮件身份验证（SPF、DKIM 和 DMARC）来帮助防止欺骗、网络钓鱼和垃圾邮件。
ms.openlocfilehash: c79a75f1ae520a0c4f885c923b4a56cdb0f7fb87
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209495"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="cbbe9-103">EOP 中的电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="cbbe9-103">Email authentication in EOP</span></span>

<span data-ttu-id="cbbe9-104">电子邮件身份验证（也称为电子邮件验证）是一组尝试阻止欺骗（来自伪造发件人的电子邮件）的标准。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="cbbe9-105">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 都按照标准来验证入站电子邮件：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-105">In Microsoft 365 organizations with mailboxes in Exchange Online, and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="cbbe9-106">SPF</span><span class="sxs-lookup"><span data-stu-id="cbbe9-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="cbbe9-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="cbbe9-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="cbbe9-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="cbbe9-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="cbbe9-109">电子邮件身份验证会验证发件人的电子邮件（例如，laura@contoso.com）是否合法，是否来自该电子邮件域的预期来源（例如，contoso.com。）</span><span class="sxs-lookup"><span data-stu-id="cbbe9-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="cbbe9-110">本主题的其余部分将说明这些技术的工作原理，以及 EOP 如何使用它们来检查入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="cbbe9-111">使用电子邮件身份验证帮助防止欺骗</span><span class="sxs-lookup"><span data-stu-id="cbbe9-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="cbbe9-112">DMARC 通过检查邮件中的**发件人**地址（用户在电子邮件客户端中看到的发件人电子邮件地址）来防止欺骗。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="cbbe9-113">目标电子邮件组织还可以验证该域已通过 SPF 或 DKIM 检查，这意味着域已通过身份验证，因此未被欺骗。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="cbbe9-114">但是，问题是 DNS 中用于电子邮件身份验证的 SPF、DKIM 和 DMARC 记录（统称为电子邮件身份验证策略）完全是可选的。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="cbbe9-115">因此，具有强电子邮件身份验证策略的域（如 microsoft.com 和 skype.com）可以防止欺骗，而发布较弱电子邮件身份验证策略或根本没有策略的域则是欺骗活动攻击的主要目标。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="cbbe9-116">截至 2018 年 3 月，在财富 500 强企业中，只有 9% 的域发布了强电子邮件身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="cbbe9-117">其余 91% 的公司可能被攻击者欺骗。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="cbbe9-118">除非已落实其他某种电子邮件筛选机制，否则这些域中的欺骗发件人发送的电子邮件可能会送达用户。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![财富 500 强企业的 DMARC 策略](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="cbbe9-120">未跻身财富 500 强的已发布强电子邮件身份验证策略的中小型公司所占比例较小，而对于北美和西欧以外的电子邮件域，发布强策略的比例仍较小。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="cbbe9-121">这是一个大问题，因为企业可能不知道电子邮件身份验证的工作方式，但攻击者完全了解这一点并且会加以利用。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="cbbe9-122">由于网络钓鱼是一个大问题，并且强电子邮件身份验证策略的采用范围有限，因此 Microsoft 将使用*隐式电子邮件身份验证*来检查入站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="cbbe9-123">隐式电子邮件身份验证建立在对常规电子邮件身份验证策略的各种扩展之上。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="cbbe9-124">这些扩展包括发件人信誉、发件人历史记录、收件人历史记录、行为分析和其他高级技巧。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="cbbe9-125">除非包含其他表明其为合法邮件的信号，否则从未使用电子邮件身份验证策略的域发送的邮件将被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="cbbe9-126">若要查看 Microsoft 的一般声明，请参阅[网络钓鱼第 2 部分 - Microsoft 365 中的增强反欺骗功能](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="cbbe9-127">复合身份验证</span><span class="sxs-lookup"><span data-stu-id="cbbe9-127">Composite authentication</span></span>

<span data-ttu-id="cbbe9-128">虽然 SPF、DKIM 和 DMARC 本身都很有用，但如果邮件没有明确的身份验证记录，它们就无法传递充足的身份验证状态。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="cbbe9-129">为此，Microsoft 开发了一种适用于隐式电子邮件身份验证的算法，将多个信号组合成一个称为_复合身份验证_（或简称为“compauth”）的单一值。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="cbbe9-130">可以在邮件头的“**Authentication-Results**”标头中标记 compauth 值。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="cbbe9-131">Authentication-Results:</span><span class="sxs-lookup"><span data-stu-id="cbbe9-131">Authentication-Results:</span></span><br/><span data-ttu-id="cbbe9-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span><span class="sxs-lookup"><span data-stu-id="cbbe9-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="cbbe9-133">[Authentication-results 邮件头](anti-spam-message-headers.md#authentication-results-message-header)对这些值进行了说明。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="cbbe9-134">通过检查邮件头，管理员（或甚至是最终用户）可以确定 Microsoft 365 如何确定发件人是否是冒充的。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="cbbe9-135">电子邮件身份验证为何并非总能阻止欺骗</span><span class="sxs-lookup"><span data-stu-id="cbbe9-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="cbbe9-136">仅依靠电子邮件身份验证记录来确定传入邮件是否是欺骗邮件具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="cbbe9-137">发送域可能缺少所需的 DNS 记录，或者记录配置错误。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="cbbe9-138">源域已正确配置 DNS 记录，但该域与“发件人”地址中的域不匹配。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="cbbe9-139">SPF 和 DKIM 不需要在“发件人”地址中使用该域。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="cbbe9-140">攻击者或合法服务部门可以注册一个域，为该域配置 SPF 和 DKIM，在“发件人”地址中使用一个完全不同的域，该邮件将通过 SPF 和 DKIM 验证。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="cbbe9-141">复合身份验证可以让这些邮件通过检查（否则它们将无法通过电子邮件验证检查）来解决这些限制。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="cbbe9-142">正如前文所述，隐式电子邮件身份验证使用多个信号来确定邮件是否是合法邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="cbbe9-143">为简单起见，以下示例专注于电子邮件身份验证结果。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="cbbe9-144">其他后端智能因素可以识别通过电子邮件身份验证的欺骗邮件，或未通过电子邮件身份验证的合法邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="cbbe9-145">例如，fabrikam.com 域没有 SPF、DKIM 或 DMARC 记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="cbbe9-146">来自 fabrikam.com 域中的发件人的邮件可能无法通过复合身份验证（请注意 `compauth` 的值和理由）：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="cbbe9-147">如果 fabrikam.com 配置了 SPF，但没有 DKIM 记录，邮件可通过复合身份验证，因为通过 SPF 验证的域与“发件人地址”中的域一致：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="cbbe9-148">如果 fabrikam.com 配置了 SPF，但没有 DKIM 记录，邮件可通过复合身份验证，因为通过 SPF 验证的域与“发件人”地址中的域一致：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="cbbe9-149">如果 SPF 中的域或 DKIM 签名与“发件人”地址中的域不一致，则该邮件可能无法通过复合身份验证：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="cbbe9-150">适用于发送未经身份验证的电子邮件的合法发件人的解决方案</span><span class="sxs-lookup"><span data-stu-id="cbbe9-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="cbbe9-151">Microsoft 365 跟踪谁在向你的组织发送未经身份验证的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="cbbe9-152">如果服务部门认为该发件人不合法，则会将其标记为复合身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="cbbe9-153">要避免这种情况，可使用本小节中的建议。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="cbbe9-154">为你自己的域配置电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="cbbe9-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="cbbe9-155">如果你拥有多个租户或与多个租户进行交互，则可使用此方法解决组织内欺骗和跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="cbbe9-156">它还有助于解决跨域欺骗，即你发送给 Microsoft 365 中的其他客户或由其他提供程序托管的第三方。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="cbbe9-157">[配置域的 SPF 记录](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="cbbe9-158">[为主域配置 DKIM 记录](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="cbbe9-159">[考虑为你的域设置 DMARC 记录](use-dmarc-to-validate-email.md)，以确定合法发件人。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="cbbe9-160">Microsoft 不提供针对 SPF、DKIM 和 DMARC 记录的详细实施指南。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="cbbe9-161">但是，线上提供了很多信息。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="cbbe9-162">此外，还有第三方公司致力于帮助你的组织设置电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="cbbe9-163">你不知道电子邮件的所有来源</span><span class="sxs-lookup"><span data-stu-id="cbbe9-163">You don't know all sources for your email</span></span>

<span data-ttu-id="cbbe9-164">许多域不会发布 SPF 记录，因为它们不知道域中邮件的所有电子邮件来源。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="cbbe9-165">首先发布一个 SPF 记录，其中包含你所知道的所有电子邮件来源（尤其是公司流量所在的位置），然后发布中性 SPF 策略 `?all`。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="cbbe9-166">例如：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="cbbe9-167">此示例意味着，来自公司基础结构的电子邮件将通过电子邮件身份验证，但来自未知来源的电子邮件将回退为中性。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="cbbe9-168">Microsoft 365 会将来自你的企业基础结构的入站电子邮件视为已通过身份验证，但来自未识别来源的电子邮件可能仍被标记为欺骗（具体取决于 Microsoft 365 能否对它进行隐式身份验证）。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="cbbe9-169">不过，这对于所有电子邮件都被 Microsoft 365 标记为欺骗邮件来说，仍是一项改进。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="cbbe9-170">开始使用 `?all` 的 SPF 回退策略后，你可以逐步你的邮件发现和包含更多电子邮件来源，然后使用更严格的策略更新 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="cbbe9-171">使用反欺骗智能保护配置允许发送未经身份验证的电子邮件的人员</span><span class="sxs-lookup"><span data-stu-id="cbbe9-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="cbbe9-172">你也可以使用[反欺骗智能保护](learn-about-spoof-intelligence.md)允许发件人将未经身份验证的邮件传送到你的组织。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="cbbe9-173">对于外部域，欺骗用户是“发件人”地址中的域，而发送基础结构是源 IP 地址（分为 /24 个 CIDR 区域），或者是反向 DNS (PTR) 记录的组织域。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="cbbe9-174">在下面的屏幕截图中，源 IP 可能是 131.107.18.4，PTR 记录为 outbound.mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="cbbe9-175">对于发送基础结构，这将显示为 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="cbbe9-176">若要允许此发件人发送未经身份验证的电子邮件，请将“**否**”更改为“**是**”。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![设置反欺骗允许的发件人](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="cbbe9-178">为发件人/收件人对创建允许条目</span><span class="sxs-lookup"><span data-stu-id="cbbe9-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="cbbe9-179">若要绕过垃圾邮件筛选、网络钓鱼筛选的某些部分，但不绕过针对特定发件人的恶意软件筛选，请参阅 [在 Microsoft 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="cbbe9-180">要求发件人为不归你所有的域配置电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="cbbe9-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="cbbe9-181">由于存在垃圾邮件和网络钓鱼问题，Microsoft 建议对所有电子邮件组织进行电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="cbbe9-182">无需在组织中配置手动替代，可让发送域中的管理员配置其电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="cbbe9-183">即使用户过去不需要发布电子邮件身份验证记录，也应在将电子邮件发送到 Microsoft 时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="cbbe9-184">设置 SPF 以发布域的发送 IP 地址，并设置 DKIM（如果可用）以对邮件进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="cbbe9-185">他们还可以考虑设置 DMARC 记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="cbbe9-186">如果他们使用批量发件人代表他们发送电子邮件，请验证“发件人”地址（如果该地址属于他们）中的域是否与通过 SPF 或 DMARC 检查的域一致。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="cbbe9-187">验证 SPF 记录中是否包括以下位置（如果他们使用了这些地址）：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="cbbe9-188">本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-188">On-premises email servers.</span></span>
  - <span data-ttu-id="cbbe9-189">通过软件即服务 (SaaS) 提供程序发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="cbbe9-190">通过云托管服务（Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 等）发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="cbbe9-191">对于由 ISP 托管的小型域，请根据 ISP 提供的说明配置 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="cbbe9-192">虽然刚开始可能很难让发送域进行身份验证，但随着时间的推移，随着越来越多的电子邮件筛选器开始放弃甚至拒绝他们的电子邮件，这将使他们设置正确的记录以确保更好地交付。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="cbbe9-193">此外，他们的参与有助于防止网络钓鱼，并且可以减少将电子邮件发送到的目标组织中出现欺骗的可能性。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="cbbe9-194">有关基础结构提供商（ISP、ESP 或云托管服务）的信息</span><span class="sxs-lookup"><span data-stu-id="cbbe9-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="cbbe9-195">如果你负责托管域的电子邮件或提供可以发送电子邮件的托管基础结构，则应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cbbe9-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="cbbe9-196">确保你的客户拥有说明应如何配置其 SPF 记录的文档</span><span class="sxs-lookup"><span data-stu-id="cbbe9-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="cbbe9-197">考虑在出站电子邮件上进行 DKIM 签名，即使客户未明确设置它（使用默认域签名）。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="cbbe9-198">你甚至可以使用 DKIM 签名对电子邮件进行双重签名（第一次使用客户的域进行签名（如果已设置该域），第二次使用你公司的 DKIM 签名）</span><span class="sxs-lookup"><span data-stu-id="cbbe9-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="cbbe9-199">即使你对来自平台的电子邮件进行身份验证，也无法保证向 Microsoft 的邮件传递，但至少可确保 Microsoft 不会因为未经过身份验证而将你的电子邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="cbbe9-200">有关服务提供商最佳实践的更多详细信息，请参阅[服务提供商的 M3AAWG 移动消息传递最佳实践](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。</span><span class="sxs-lookup"><span data-stu-id="cbbe9-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
