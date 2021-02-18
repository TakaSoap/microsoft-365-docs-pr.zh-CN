---
title: EOP 如何验证"自"地址以防止钓鱼
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Outlook.com 接受或拒绝的电子邮件地址类型，以帮助防止网络钓鱼。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ced200c2e521533c1dec8a9d0917add7ca058f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287815"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="68f30-103">EOP 如何验证"自"地址以防止钓鱼</span><span class="sxs-lookup"><span data-stu-id="68f30-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="68f30-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="68f30-104">**Applies to**</span></span>
- [<span data-ttu-id="68f30-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="68f30-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="68f30-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="68f30-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="68f30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68f30-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="68f30-108">网络钓鱼攻击是任何电子邮件组织的持续威胁。</span><span class="sxs-lookup"><span data-stu-id="68f30-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="68f30-109">除了在发件人电子邮件地址 [ (欺骗) ，](anti-spoofing-protection.md)攻击者通常使用"发件人"地址中违反 Internet 标准的值。</span><span class="sxs-lookup"><span data-stu-id="68f30-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="68f30-110">为了帮助防止此类网络钓鱼，Exchange Online Protection (EOP) 和 Outlook.com 现在要求入站邮件包含符合 RFC 的"源"地址，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="68f30-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="68f30-111">2017 年 11 月启用此强制。</span><span class="sxs-lookup"><span data-stu-id="68f30-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="68f30-112">**注意**：</span><span class="sxs-lookup"><span data-stu-id="68f30-112">**Notes**:</span></span>

- <span data-ttu-id="68f30-113">如果您定期收到来自组织的电子邮件，如本文所述，其"From"地址格式不正确，请鼓励这些组织更新其电子邮件服务器，以遵守现代安全标准。</span><span class="sxs-lookup"><span data-stu-id="68f30-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="68f30-114">"代表 (发件人"字段和) 列表所使用的发件人字段不受这些要求的影响。</span><span class="sxs-lookup"><span data-stu-id="68f30-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="68f30-115">有关详细信息，请参阅以下博客文章：我们引用电子邮件的"发件人"时意味着什么[？。](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)</span><span class="sxs-lookup"><span data-stu-id="68f30-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="68f30-116">电子邮件标准概述</span><span class="sxs-lookup"><span data-stu-id="68f30-116">An overview of email message standards</span></span>

<span data-ttu-id="68f30-117">标准 SMTP 电子邮件由 *邮件信封* 和邮件内容组成。</span><span class="sxs-lookup"><span data-stu-id="68f30-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="68f30-118">邮件信封包含在 SMTP 服务器之间传输和传递邮件所需的信息。</span><span class="sxs-lookup"><span data-stu-id="68f30-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="68f30-119">邮件内容包含邮件头字段（统称为 *邮件头*）和邮件正文。</span><span class="sxs-lookup"><span data-stu-id="68f30-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="68f30-120">RFC [5321](https://tools.ietf.org/html/rfc5321)中描述了邮件信封，RFC [5322](https://tools.ietf.org/html/rfc5322)中描述了邮件头。</span><span class="sxs-lookup"><span data-stu-id="68f30-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="68f30-121">收件人永远不会看到实际的邮件信封，因为它由邮件传输进程生成，并且实际上不是邮件的一部分。</span><span class="sxs-lookup"><span data-stu-id="68f30-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="68f30-122">地址 (MAIL `5321.MailFrom` **FROM** 地址、P1 发件人或信封发件人) 是在邮件的 SMTP 传输中使用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="68f30-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="68f30-123">虽然发件人可以指定不同的返回路径电子邮件地址，但此电子邮件地址通常记录在邮件头 (的"返回路径"头字段中) 。 </span><span class="sxs-lookup"><span data-stu-id="68f30-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="68f30-124">该 (也称为发件人地址或 P2 发件人) 是"发件人"头字段中的电子邮件地址，是电子邮件客户端中显示的发件人 `5322.From` 电子邮件地址。 </span><span class="sxs-lookup"><span data-stu-id="68f30-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="68f30-125">The From address is the focus of the requirements in this article.</span><span class="sxs-lookup"><span data-stu-id="68f30-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="68f30-126">"From"地址在若干 RFC (中详细定义，例如 RFC 5322 第 3.2.3、3.4 和 3.4.1 节和 [RFC 3696](https://tools.ietf.org/html/rfc3696)) 。</span><span class="sxs-lookup"><span data-stu-id="68f30-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="68f30-127">寻址存在许多变化，并且被视为有效或无效的寻址。</span><span class="sxs-lookup"><span data-stu-id="68f30-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="68f30-128">为了简单，我们建议采用以下格式和定义：</span><span class="sxs-lookup"><span data-stu-id="68f30-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="68f30-129">**显示名称**：描述电子邮件地址所有者的可选短语。</span><span class="sxs-lookup"><span data-stu-id="68f30-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="68f30-130">我们建议您始终使用双引号显示名称" (") ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="68f30-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="68f30-131">如果显示名称 _逗号，则必须_ 使用每个 RFC 5322 的双引号将字符串括起来。</span><span class="sxs-lookup"><span data-stu-id="68f30-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="68f30-132">如果 From 地址包含显示名称，则 EmailAddress 值必须括在尖括号 (< >) 如下所示。</span><span class="sxs-lookup"><span data-stu-id="68f30-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="68f30-133">Microsoft 强烈建议你在电子邮件地址和显示名称之间插入空格。</span><span class="sxs-lookup"><span data-stu-id="68f30-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="68f30-134">**EmailAddress：** 电子邮件地址使用以下格式 `local-part@domain` ：</span><span class="sxs-lookup"><span data-stu-id="68f30-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="68f30-135">**local-part：** 一个标识与地址关联的邮箱的字符串。</span><span class="sxs-lookup"><span data-stu-id="68f30-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="68f30-136">此值在域中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="68f30-136">This value is unique within the domain.</span></span> <span data-ttu-id="68f30-137">通常，使用邮箱所有者的用户名或 GUID。</span><span class="sxs-lookup"><span data-stu-id="68f30-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="68f30-138">**domain**： FQDN (FQDN) 托管由电子邮件地址的本地部分标识的邮箱的电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="68f30-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="68f30-139">这些是 EmailAddress 值的一些额外注意事项：</span><span class="sxs-lookup"><span data-stu-id="68f30-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="68f30-140">仅一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="68f30-140">Only one email address.</span></span>
  - <span data-ttu-id="68f30-141">建议您不要用空格分隔尖括号。</span><span class="sxs-lookup"><span data-stu-id="68f30-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="68f30-142">不要在电子邮件地址后添加其他文本。</span><span class="sxs-lookup"><span data-stu-id="68f30-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="68f30-143">有效和无效的 From 地址示例</span><span class="sxs-lookup"><span data-stu-id="68f30-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="68f30-144">以下 From 电子邮件地址有效：</span><span class="sxs-lookup"><span data-stu-id="68f30-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="68f30-145">`From: < sender@contoso.com >` (建议不要这样做，因为尖括号和电子邮件地址之间存在空格。) </span><span class="sxs-lookup"><span data-stu-id="68f30-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="68f30-146">`From: Microsoft 365 <sender@contoso.com>` (建议不要这样做，显示名称双引号括起来。) </span><span class="sxs-lookup"><span data-stu-id="68f30-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="68f30-147">以下 From 电子邮件地址无效：</span><span class="sxs-lookup"><span data-stu-id="68f30-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="68f30-148">**No From address**： Some automated messages don't include a From address.</span><span class="sxs-lookup"><span data-stu-id="68f30-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="68f30-149">过去，当 Microsoft 365 或 Outlook.com收到不含"收件人"地址的邮件时，该服务添加了以下默认的"From： 地址"，使邮件可交付：</span><span class="sxs-lookup"><span data-stu-id="68f30-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="68f30-150">现在，不再接受地址为空的邮件。</span><span class="sxs-lookup"><span data-stu-id="68f30-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="68f30-151">`From: Microsoft 365 sender@contoso.com` (显示名称，但电子邮件地址未括在尖括号中。) </span><span class="sxs-lookup"><span data-stu-id="68f30-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="68f30-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (电子邮件地址后添加文本。) </span><span class="sxs-lookup"><span data-stu-id="68f30-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="68f30-153">`From: Sender, Example <sender.example@contoso.com>` (该显示名称包含逗号，但不用双引号括起来。) </span><span class="sxs-lookup"><span data-stu-id="68f30-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="68f30-154">`From: "Microsoft 365 <sender@contoso.com>"` (整个值错误地用双引号括起来。) </span><span class="sxs-lookup"><span data-stu-id="68f30-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="68f30-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (显示名称，但电子邮件地址未括在尖括号中。) </span><span class="sxs-lookup"><span data-stu-id="68f30-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="68f30-156">`From: Microsoft 365<sender@contoso.com>` (括号和左尖显示名称之间没有空格。) </span><span class="sxs-lookup"><span data-stu-id="68f30-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="68f30-157">`From: "Microsoft 365"<sender@contoso.com>` (双引号和左尖括号之间没有空格。) </span><span class="sxs-lookup"><span data-stu-id="68f30-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="68f30-158">禁止自动答复自定义域</span><span class="sxs-lookup"><span data-stu-id="68f30-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="68f30-159">该值不能用于禁止 `From: <>` 自动答复。</span><span class="sxs-lookup"><span data-stu-id="68f30-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="68f30-160">相反，你需要为自定义域设置空 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="68f30-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="68f30-161">自动答复 (自动答复) 自动答复，因为响应服务器无法将邮件发送到任何已发布的地址。</span><span class="sxs-lookup"><span data-stu-id="68f30-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="68f30-162">选择无法接收电子邮件的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="68f30-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="68f30-163">例如，如果你的主域contoso.com，你可以选择noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="68f30-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="68f30-164">此域的空 MX 记录由单个时间段组成。</span><span class="sxs-lookup"><span data-stu-id="68f30-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="68f30-165">例如：</span><span class="sxs-lookup"><span data-stu-id="68f30-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="68f30-166">有关设置 MX 记录的信息，请参阅在任何 DNS 托管提供商上为 [Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)创建 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="68f30-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="68f30-167">有关发布空 MX 的信息，请参阅[RFC 7505。](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="68f30-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="68f30-168">替代"自地址强制"</span><span class="sxs-lookup"><span data-stu-id="68f30-168">Override From address enforcement</span></span>

<span data-ttu-id="68f30-169">若要绕过入站电子邮件的发件人地址要求，可以使用 IP 允许列表 (连接筛选) 或邮件流规则 (也称为传输规则) ，如 [Microsoft 365](create-safe-sender-lists-in-office-365.md)中的"创建安全发件人列表"中所述。</span><span class="sxs-lookup"><span data-stu-id="68f30-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="68f30-170">无法覆盖从 Microsoft 365 发送的出站电子邮件的 From 地址要求。</span><span class="sxs-lookup"><span data-stu-id="68f30-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="68f30-171">此外，Outlook.com支持，也不允许任何种类的覆盖。</span><span class="sxs-lookup"><span data-stu-id="68f30-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="68f30-172">在 Microsoft 365 中防止和防范网络攻击的其他方法</span><span class="sxs-lookup"><span data-stu-id="68f30-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="68f30-173">若要详细了解如何加强组织抵御网络钓鱼、垃圾邮件、数据泄露和其他威胁，请参阅保护 [Microsoft 365 商业](../../admin/security-and-compliance/secure-your-business-data.md)版计划的前 10 种方法。</span><span class="sxs-lookup"><span data-stu-id="68f30-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
