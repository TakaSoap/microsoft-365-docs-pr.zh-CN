---
title: 发件人策略框架 (SPF) 防止欺骗
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解 Microsoft 365 如何使用 DNS 中的发件人策略框架 (SPF) TXT 记录，以确保目标电子邮件系统信任从自定义域发送的邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 972f283f6138bafcebd877a19f0bfc429e0eed03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203249"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="bd815-103">Microsoft 365 如何使用发件人策略框架 (SPF) 来防止欺骗</span><span class="sxs-lookup"><span data-stu-id="bd815-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bd815-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bd815-104">**Applies to**</span></span>
- [<span data-ttu-id="bd815-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bd815-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bd815-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bd815-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bd815-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd815-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="bd815-108">**摘要：** 本文介绍了 Microsoft 365 如何在 DNS 中使用发件人策略框架 (SPF) TXT 记录，以确保目标电子邮件系统信任从自定义域发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="bd815-109">这适用于从 Microsoft 365 发送的出站邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="bd815-110">从 Microsoft 365 发送给 Microsoft 365 中的收件人的邮件将始终通过 SPF。</span><span class="sxs-lookup"><span data-stu-id="bd815-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="bd815-p102">SPF TXT 记录是一个 DNS 记录，通过验证发出电子邮件的域的域名，帮助阻止欺骗和钓鱼。SPF 根据发送域的可疑所有者来验证发件人的 IP 地址，从而验证电子邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="bd815-p102">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="bd815-p103">Internet 工程任务组 (IETF) 于 2014 年弃用 SPF 记录类型。请务必在 DNS 中改用 TXT 记录来发布 SPF 信息。为清楚起见，本文的其余部分使用 SPF TXT 记录一词。</span><span class="sxs-lookup"><span data-stu-id="bd815-p103">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="bd815-116">域管理员在 DNS 的 TXT 记录中发布 SPF 信息。</span><span class="sxs-lookup"><span data-stu-id="bd815-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="bd815-117">SPF 信息可以标识得到授权的出站电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="bd815-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="bd815-118">目标电子邮件系统验证邮件是否来自得到授权的出站电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="bd815-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="bd815-119">如果你已熟悉 SPF，或者你拥有一个简单的部署，并且只需了解在 DNS for Microsoft 365 的 SPF TXT 记录中要包含哪些内容，可以转到在 [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)中设置 SPF 以帮助防止欺骗。</span><span class="sxs-lookup"><span data-stu-id="bd815-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="bd815-120">如果你没有完全托管在 Microsoft 365 中的部署，或者希望详细了解 SPF 的工作原理或如何排查 Microsoft 365 的 SPF 问题，请继续阅读。</span><span class="sxs-lookup"><span data-stu-id="bd815-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="bd815-121">以前，如果还使用了 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="bd815-122">现在，不再需要这样做。</span><span class="sxs-lookup"><span data-stu-id="bd815-122">This is no longer required.</span></span> <span data-ttu-id="bd815-123">此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。</span><span class="sxs-lookup"><span data-stu-id="bd815-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="bd815-124">无需立即进行更改，但如果收到"查找过多"错误，请修改 SPF TXT 记录，如在 [Microsoft 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md)中设置 SPF 以帮助防止欺骗中所述。</span><span class="sxs-lookup"><span data-stu-id="bd815-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="bd815-125">SPF 在 Microsoft 365 中防止欺骗和钓鱼的工作原理</span><span class="sxs-lookup"><span data-stu-id="bd815-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="bd815-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="bd815-p106">SPF 确定是否允许发件人代表域发送邮件。如果不允许发件人发送邮件，即电子邮件无法通过接收服务器上的 SPF 检查，那么在该服务器上配置垃圾邮件策略会确定如何处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-p106">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="bd815-129">每个 SPF TXT 记录包含三个部分：SPF TXT 记录声明、允许从你的域和可以代表你的域发送邮件的外部域发送邮件的 IP 地址，以及强制规则。</span><span class="sxs-lookup"><span data-stu-id="bd815-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="bd815-130">三个部分俱全，才算是有效的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="bd815-131">本文介绍如何形成 SPF TXT 记录，并提供在 Microsoft 365 中处理服务的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="bd815-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="bd815-132">此外，还提供了说明链接，指导你如何使用你的域注册机构将记录发布到 DNS。</span><span class="sxs-lookup"><span data-stu-id="bd815-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="bd815-133">SPF 基础知识：允许从自定义域发送邮件的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="bd815-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="bd815-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="bd815-135">看看 SPF 规则的基本语法：</span><span class="sxs-lookup"><span data-stu-id="bd815-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="bd815-136">v=spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="bd815-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="bd815-137">例如，假设 contoso.com 存在以下 SPF 规则：</span><span class="sxs-lookup"><span data-stu-id="bd815-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="bd815-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="bd815-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="bd815-139">在本示例中，SPF 规则指示接收电子邮件服务器仅为域 contoso.com 接受来自这些 IP 地址的邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="bd815-140">IP 地址 #1</span><span class="sxs-lookup"><span data-stu-id="bd815-140">IP address #1</span></span>

- <span data-ttu-id="bd815-141">IP 地址 #2</span><span class="sxs-lookup"><span data-stu-id="bd815-141">IP address #2</span></span>

- <span data-ttu-id="bd815-142">IP 地址 #3</span><span class="sxs-lookup"><span data-stu-id="bd815-142">IP address #3</span></span>

<span data-ttu-id="bd815-p108">此 SPF 规则指示接收电子邮件服务器，如果邮件是从 contoso.com 发送，而不是从这三个 IP 地址中的任何一个发送，则接收服务器应将强制规则应用于邮件。强制规则通常是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="bd815-p108">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="bd815-p109">**硬失败。** 在邮件信封中用"硬失败"标记邮件，然后此类型的邮件遵照接收服务器的配置垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="bd815-p109">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="bd815-p110">**软失败。** 在邮件信封中用"软失败"标记邮件。通常，电子邮件服务器配置为始终传递这些邮件。大多数最终用户不会看到此标记。</span><span class="sxs-lookup"><span data-stu-id="bd815-p110">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span>

- <span data-ttu-id="bd815-p111">**中性。** 不执行任何操作，即不标记邮件信封。通常将此选项保留用于测试，而且也很少使用。</span><span class="sxs-lookup"><span data-stu-id="bd815-p111">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="bd815-p112">下面的示例显示了 SPF 在不同情况中的工作原理。在这些示例中，contoso.com 是发件人，woodgrovebank.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="bd815-p112">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="bd815-156">示例 1：直接从发送人发送到收件人的邮件的电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="bd815-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="bd815-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="bd815-158">SPF 最适用于从发件人到收件人的路径是直接路径的情况，例如：</span><span class="sxs-lookup"><span data-stu-id="bd815-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![关系图显示 SPF 如何在将电子邮件直接从服务器发送到服务器时对其进行身份验证。](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="bd815-160">Woodgrovebank.com 接收邮件时，如果 IP 地址 #1 在 contoso.com 的 SPF TXT 记录中，则消息通过 SPF 检查并进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="bd815-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="bd815-161">示例 2：欺骗性发件人地址无法通过 SPF 检查</span><span class="sxs-lookup"><span data-stu-id="bd815-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="bd815-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="bd815-163">假设欺诈者找到办法欺骗 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="bd815-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![关系图显示 SPF 如何在欺骗服务器发送电子邮件时对其进行身份验证。](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="bd815-165">由于 IP 地址 #12 不在 contoso.com 的 SPF TXT 记录中，邮件无法通过 SPF 检查，收件人可以选择将其标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="bd815-166">示例 3：SPF 和转发的邮件</span><span class="sxs-lookup"><span data-stu-id="bd815-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="bd815-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="bd815-p113">SPF 的一个缺点是它对转发的电子邮件不起作用。例如，假设 woodgrovebank.com 的用户已经设置了转发规则将所有电子邮件发送到 outlook.com 帐户：</span><span class="sxs-lookup"><span data-stu-id="bd815-p113">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![关系图显示转发邮件时，SPF 如何无法对电子邮件进行身份验证。](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="bd815-p114">此邮件最初可以通过 woodgrovebank.com 的 SPF 检查，但无法通过 outlook.com 的 SPF 检查，因为 IP #25 不在 contoso.com 的 SPF TXT 记录中。Outlook.com 则可能将邮件标记为垃圾邮件。若要解决此问题，请结合使用 SPF 和其他电子邮件身份验证方法（如 DKIM 和 DMARC）。</span><span class="sxs-lookup"><span data-stu-id="bd815-p114">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="bd815-174">SPF 基础知识：包括可以代表您的域发送邮件的第三方域</span><span class="sxs-lookup"><span data-stu-id="bd815-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="bd815-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="bd815-p115">除 IP 地址外，您还可以配置您的 SPF TXT 记录以包括域作为发件人。这些都作为"include"语句添加到 SPF TXT 记录中。例如，contoso.com 可能想要包括所有来自 contoso.net 以及它另外拥有的 contoso.org 的邮件服务器的 IP 地址。为了实现此目的，contoso.com 发布了 SPF TXT 记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd815-p115">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="bd815-180">当接收服务器在 DNS 中看到此记录时，它还对 SPF TXT 记录执行 DNS 查找，查找 contoso.net，然后查找 contoso.org。如果它在记录中找到了其他 include 语句 contoso.net 或 contoso.org，它也会遵循这些语句。</span><span class="sxs-lookup"><span data-stu-id="bd815-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="bd815-181">为了帮助防止拒绝服务攻击，一封电子邮件的 DNS 查找的最大次数是 10 次。</span><span class="sxs-lookup"><span data-stu-id="bd815-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="bd815-182">每个 include 语句都表示一个额外的 DNS 查找。</span><span class="sxs-lookup"><span data-stu-id="bd815-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="bd815-183">如果邮件超过 10 次限制，则该邮件将无法通过 SPF 检查。</span><span class="sxs-lookup"><span data-stu-id="bd815-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="bd815-184">邮件达到此限制后，根据接收服务器的配置方式，发件人可能会收到一条消息，指出邮件生成了"查找次数过多"或"已超出邮件的最大跃点计数" (当查找循环并超过 DNS 超时) 时可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="bd815-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="bd815-185">有关如何避免这种情况的提示，请参阅疑难解答 [：Microsoft 365 中 SPF 的最佳实践](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="bd815-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="bd815-186">SPF TXT 记录和 Microsoft 365 的要求</span><span class="sxs-lookup"><span data-stu-id="bd815-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="bd815-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="bd815-188">如果在设置 Microsoft 365 时设置邮件，则已经创建了一个 SPF TXT 记录，该记录将 Microsoft 邮件服务器标识为域的合法邮件源。</span><span class="sxs-lookup"><span data-stu-id="bd815-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="bd815-189">此记录可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="bd815-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="bd815-190">如果你是完全托管的客户，即没有发送出站邮件的本地邮件服务器，这是唯一需要为 Office 365 发布的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="bd815-191">如果你有混合部署 (即 你在本地拥有一些邮箱，一些邮箱托管在 Microsoft 365) 中，或者如果你是 Exchange Online Protection (EOP) 独立客户 (，则你的组织使用 EOP 来保护你的本地邮箱) ，你应当将每个本地边缘邮件服务器的出站 IP 地址添加到 DNS 中的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="bd815-192">为 Microsoft 365 形成 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="bd815-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="bd815-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="bd815-p118">请参考本文中的语法信息，构成自定义域的 SPF TXT 记录。尽管还有其他语法选项本文未提及，这些都是最常用的选项。在构成记录后，需要在域注册机构更新记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-p118">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="bd815-197">有关 Microsoft 365 需要包括的域的信息，请参阅 [SPF 所需的](../../enterprise/external-domain-name-system-records.md)外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="bd815-198">使用[分步操作说明](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online)更新域注册机构的 SPF (TXT) 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-198">Use the [step-by-step instructions](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="bd815-199">Microsoft 365 的 SPF TXT 记录语法</span><span class="sxs-lookup"><span data-stu-id="bd815-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="bd815-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="bd815-201">Microsoft 365 的典型 SPF TXT 记录具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd815-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="bd815-202">例如：</span><span class="sxs-lookup"><span data-stu-id="bd815-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="bd815-203">其中：</span><span class="sxs-lookup"><span data-stu-id="bd815-203">where:</span></span>

- <span data-ttu-id="bd815-p120">**v=spf1** 是必需的，用于将 TXT 记录定义为 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-p120">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="bd815-p121">**ip4** 表示您使用的是 IP 第 4 版地址。**ip6** 表示您使用的是 IP 第 6 版地址。如果您使用的是 IPv6 IP 地址，则将 **ip4** 替换为本文示例中的 **ip6**。您还可以使用 CIDR 表示法指定 IP 地址范围，例如 **ip4:192.168.0.1/26**。</span><span class="sxs-lookup"><span data-stu-id="bd815-p121">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="bd815-210">_IP address_ 是要添加到 SPF TXT 记录的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bd815-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="bd815-211">通常情况下，这是组织的出站邮件服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bd815-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="bd815-212">可以列出多个出站邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="bd815-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="bd815-213">有关详细信息，请参阅示例：多个出站本地邮件服务器和 [Microsoft 365 的 SPF TXT 记录](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。</span><span class="sxs-lookup"><span data-stu-id="bd815-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="bd815-214">_domain name_ 是您想要添加为合法发件人的域。</span><span class="sxs-lookup"><span data-stu-id="bd815-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="bd815-215">有关 Microsoft 365 应包含的域名列表，请参阅 [SPF 所需的外部 DNS 记录](../../enterprise/external-domain-name-system-records.md)。</span><span class="sxs-lookup"><span data-stu-id="bd815-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](../../enterprise/external-domain-name-system-records.md).</span></span>

- <span data-ttu-id="bd815-216">强制规则通常是下列之一：</span><span class="sxs-lookup"><span data-stu-id="bd815-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="bd815-217">-all</span><span class="sxs-lookup"><span data-stu-id="bd815-217">-all</span></span>

    <span data-ttu-id="bd815-p124">表示硬失败。如果您知道您的域的所有授权 IP 地址，请在 SPF TXT 记录中列出这些地址并使用 -all（硬失败）限定符。此外，如果您仅使用 SPF，即不使用 DMARC 或 DKIM，您应使用 -all 限定符。我们建议您始终使用此限定符。</span><span class="sxs-lookup"><span data-stu-id="bd815-p124">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="bd815-222">~all</span><span class="sxs-lookup"><span data-stu-id="bd815-222">~all</span></span>

    <span data-ttu-id="bd815-p125">表示软失败。如果您不确定是否有 IP 地址的完整列表，那么您应该使用 ~all（软失败）限定符。此外，如果您使用的是 p=quarantine 或 p=reject 的 DMARC，则可以使用 ~all。否则，请使用 -all。</span><span class="sxs-lookup"><span data-stu-id="bd815-p125">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>

  - <span data-ttu-id="bd815-227">?all</span><span class="sxs-lookup"><span data-stu-id="bd815-227">?all</span></span>

    <span data-ttu-id="bd815-p126">表示中性。这在测试 SPF 时使用。不建议您在实时部署中使用此限定符。</span><span class="sxs-lookup"><span data-stu-id="bd815-p126">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="bd815-231">示例：Microsoft 365 发送所有邮件时使用的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="bd815-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="bd815-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="bd815-233">如果所有邮件都由 Microsoft 365 发送，在 SPF TXT 记录中使用此记录：</span><span class="sxs-lookup"><span data-stu-id="bd815-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="bd815-234">示例：具有一个本地部署和 Microsoft 365 的混合Exchange Server SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="bd815-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="bd815-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="bd815-236">在混合环境中，如果本地 Exchange Server 的 IP 地址为 192.168.0.1，为了将 SPF 强制规则设置为硬故障，请构成如下 SPF TXT 记录：</span><span class="sxs-lookup"><span data-stu-id="bd815-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="bd815-237">示例：多个出站本地邮件服务器和 Microsoft 365 的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="bd815-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="bd815-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="bd815-p127">如果有多个出站邮件服务器，可以在 SPF TXT 记录中添加每个邮件服务器的 IP 地址，并用空格（后跟"ip4:"语句）分隔每个 IP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="bd815-p127">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="bd815-241">下一步：为 Microsoft 365 设置 SPF</span><span class="sxs-lookup"><span data-stu-id="bd815-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="bd815-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="bd815-243">创建 SPF TXT 记录后，请按照在 Microsoft [365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 中设置 SPF 中的步骤操作，以帮助防止欺骗，以将其添加到你的域。</span><span class="sxs-lookup"><span data-stu-id="bd815-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="bd815-244">尽管 SPF 旨在帮助防止欺骗，但还有 SPF 无法防止的欺骗技术。</span><span class="sxs-lookup"><span data-stu-id="bd815-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="bd815-245">为了防止这些，设置 SPF 后，还应为 Microsoft 365 配置 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="bd815-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="bd815-246">若要开始，请参阅使用 [DKIM 验证从 Microsoft 365](use-dkim-to-validate-outbound-email.md)中的自定义域发送的出站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bd815-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="bd815-247">然后，请参阅[使用 DMARC 验证 Microsoft 365 中的电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="bd815-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="bd815-248">疑难解答：Microsoft 365 中 SPF 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="bd815-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="bd815-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="bd815-p129">只能为自定义域创建一个 SPF TXT 记录。创建多个记录会导致轮循机制发生，并且 SPF 也会失败。为了避免发生这种情况，可以为每个子域单独创建记录。例如，为 contoso.com 创建一个记录，为 bulkmail.contoso.com 创建另一个记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-p129">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="bd815-p130">如果在传递邮件之前，电子邮件引起超过 10 次 DNS 查找，那么接收邮件服务器将使用永久性错误进行响应，也称为  _permerror_，并且会导致邮件无法通过 SPF 检查。接收服务器还可能使用未送达报告 (NDR) 进行响应，其中包含一个类似以下的错误：</span><span class="sxs-lookup"><span data-stu-id="bd815-p130">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="bd815-256">邮件超出跃点计数。</span><span class="sxs-lookup"><span data-stu-id="bd815-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="bd815-257">邮件需要的查找次数过多。</span><span class="sxs-lookup"><span data-stu-id="bd815-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="bd815-258">避免在将第三方域与 Microsoft 365 一同使用时出现"查找过多"错误</span><span class="sxs-lookup"><span data-stu-id="bd815-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="bd815-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="bd815-p131">第三方域的一些 SPF TXT 记录指示接收服务器执行大量 DNS 查找。例如，在撰写本文时，Salesforce.com 的记录中包含 5 个 include 语句：</span><span class="sxs-lookup"><span data-stu-id="bd815-p131">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="bd815-p132">若要避免此错误，您可以实现一个允许任何人发送批量电子邮件的策略，例如，必须使用为此专门创建的一个子域。然后，您可以为包含批量电子邮件的子域定义不同的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="bd815-p132">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="bd815-p133">在某些情况下，如 salesforce.com 示例，您必须使用您的 SPF TXT 记录中的域，但在其他情况下，第三方可能已创建要用于此目的的一个子域。例如，exacttarget.com 已经创建了一个需要用于您的 SPF TXT 记录的子域：</span><span class="sxs-lookup"><span data-stu-id="bd815-p133">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="bd815-266">当您的 SPF TXT 记录中包含第三方域时，您需要与第三方进行确认要使用哪些域或子域以避免运行次数达到 10 次查找限制。</span><span class="sxs-lookup"><span data-stu-id="bd815-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="bd815-267">如何查看当前 SPF TXT 记录，并确定它需要的查找次数</span><span class="sxs-lookup"><span data-stu-id="bd815-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="bd815-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="bd815-p134">可以使用 nslookup 查看 DNS 记录，包括 SPF TXT 记录。或者，如果需要，还可以使用许多免费的联机工具来查看 SPF TXT 记录的内容。通过查看 SPF TXT 记录并遵循 include 语句链和重定向，可以确定记录需要的 DNS 查找次数。一些联机工具甚至会计算并显示查找次数。跟踪查找次数将有助于防止从组织发送的邮件触发接收服务器生成永久性错误（称为 permerror）。</span><span class="sxs-lookup"><span data-stu-id="bd815-p134">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bd815-274">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="bd815-274">For more information</span></span>
<span data-ttu-id="bd815-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="bd815-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="bd815-276">需要有关添加 SPF TXT 记录的？</span><span class="sxs-lookup"><span data-stu-id="bd815-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="bd815-277">阅读文章在任何 DNS 托管提供商为 [Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) 创建 DNS 记录，详细了解在 Microsoft 365 中将发件人策略框架与自定义域一同使用。</span><span class="sxs-lookup"><span data-stu-id="bd815-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md#add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="bd815-278">[反垃圾邮件邮件头包括](anti-spam-message-headers.md) Microsoft 365 用于 SPF 检查的语法和标头字段。</span><span class="sxs-lookup"><span data-stu-id="bd815-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>
