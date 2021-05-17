---
title: 有关发送到 Microsoft 365 的邮件的疑难解答
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文提供有关将电子邮件发送到收件箱的问题的疑难解答信息，Microsoft 365 &客户进行批量邮件Microsoft 365最佳实践。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c3017b0e7d0c583c9038f695f9f47010ff92c18a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203734"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="553c9-103">有关发送到 Microsoft 365 的邮件的疑难解答</span><span class="sxs-lookup"><span data-stu-id="553c9-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="553c9-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="553c9-104">**Applies to**</span></span>
- [<span data-ttu-id="553c9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="553c9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="553c9-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="553c9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="553c9-107">本文提供发件人在尝试向 Microsoft 365 中的收件箱发送电子邮件时遇到问题的疑难解答信息，以及批量发邮件给客户的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="553c9-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="553c9-108">您是否正在管理您的 IP 和域的发送信誉？</span><span class="sxs-lookup"><span data-stu-id="553c9-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="553c9-109">EOP 筛选技术旨在为用户和其他 Microsoft Microsoft 365产品（如 Exchange Server）提供反垃圾邮件Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="553c9-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="553c9-110">我们还利用 SPF、DKIM、DMARC 和电子邮件身份验证技术来帮助解决欺骗和网络钓鱼的问题，通过验证发送电子邮件的域是否被授权执行此操作来帮助解决。</span><span class="sxs-lookup"><span data-stu-id="553c9-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="553c9-111">EOP 筛选受到许多因素的影响，如发送 IP、域、身份验证、列表精度、投诉率和内容等相关因素。</span><span class="sxs-lookup"><span data-stu-id="553c9-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="553c9-112">其中，拉低发件人信誉和传送电子邮件能力的关键因素之一是他们的垃圾邮件投诉率。</span><span class="sxs-lookup"><span data-stu-id="553c9-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="553c9-113">您是否正从新的 IP 地址发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="553c9-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="553c9-p102">如果您之前没有使用这个 IP 地址发送电子邮件，那么通常在我们的系统里不会为其建立任何信誉。因此，来自新 IP 的电子邮件更有可能遇到传送问题。一旦 IP 建立了非发送垃圾邮件的信誉，EOP 通常会允许更好的电子邮件传送体验。</span><span class="sxs-lookup"><span data-stu-id="553c9-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="553c9-p103">添加到域（在现有 SPF 记录下验证的）的新 IP 通常继承了一些域的发送信誉的额外优势。如果您的域有良好的发送信誉，那么新 IP 可能会有更快的加速时间体验。一个新的 IP 可以在几周内或更快的时间内完全加速，这取决于容量、列表精度和垃圾邮件投诉率。</span><span class="sxs-lookup"><span data-stu-id="553c9-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="553c9-120">确认您的 DNS 设置正确</span><span class="sxs-lookup"><span data-stu-id="553c9-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="553c9-121">有关如何创建和维护 DNS 记录的说明，包括邮件路由所需的 MX 记录，您将需要联系您的 DNS 托管提供者。</span><span class="sxs-lookup"><span data-stu-id="553c9-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="553c9-122">确保您没有将自己标识为不可路由的 IP</span><span class="sxs-lookup"><span data-stu-id="553c9-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="553c9-p104">我们可能不接受来自反向 DNS 查找失败的发件人的电子邮件。在某些情况下，当合法发件人在尝试打开一个 EOP 的连接时，他们错误地将自己标识为非面向 Internet 的可路由的 IP。为专用（不可路由的）网保留的 IP 地址包括：</span><span class="sxs-lookup"><span data-stu-id="553c9-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="553c9-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="553c9-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="553c9-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="553c9-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="553c9-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="553c9-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="553c9-129">在邮件中向用户 (NDR) 未送达报告Office 365</span><span class="sxs-lookup"><span data-stu-id="553c9-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="553c9-p105">出现一些传送问题是因为发件人的 IP 地址被 Microsoft 阻止或用户账户由于以前的垃圾邮件活动被标识为已禁止的发件人。如果您认为您错误地收到了 NDR，首先按照在 NDR 邮件中解决此问题的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="553c9-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="553c9-132">有关你收到的错误的详细信息，请参阅电子邮件未送达报告中的错误代码列表[Exchange Online。](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="553c9-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="553c9-133">例如，如果您收到以下 NDR，则表明发送 IP 地址已被 Microsoft 阻止：</span><span class="sxs-lookup"><span data-stu-id="553c9-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="553c9-134">若要请求从此列表中删除，可以使用除名门户将自己从阻止 [的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="553c9-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="553c9-135">我的电子邮件已登陆到收件人的"垃圾邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="553c9-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="553c9-136">如果某封邮件被 EOP 错误地标识为垃圾邮件，您可以与收件人一起将此误报邮件提交给 Microsoft 垃圾邮件分析团队，他们将对该邮件进行评估和分析。</span><span class="sxs-lookup"><span data-stu-id="553c9-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="553c9-137">有关详细信息，请参见[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="553c9-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="553c9-138">来自我的 IP 地址的流量被 EOP 限制</span><span class="sxs-lookup"><span data-stu-id="553c9-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="553c9-139">如果您收到来自 EOP 的 NDR，则表明您的 IP 地址被 EOP 限制，例如：</span><span class="sxs-lookup"><span data-stu-id="553c9-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="553c9-p107">您收到了 NDR，因为从 IP 地址检测出可疑活动，且该地址在接受进一步评估时已暂时受限。如果通过评估后该怀疑被解除，则该限制将很快取消。</span><span class="sxs-lookup"><span data-stu-id="553c9-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="553c9-142">我无法从邮件中的发件人Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="553c9-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="553c9-143">为了从我们的用户接收邮件，请确保您的网络允许来自 EOP 在我们的数据中心使用的 IP 地址的连接。</span><span class="sxs-lookup"><span data-stu-id="553c9-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="553c9-144">有关详细信息，请参阅Exchange Online Protection [IP 地址](../../enterprise/urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="553c9-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="553c9-145">向用户发送批量电子邮件Microsoft 365最佳实践</span><span class="sxs-lookup"><span data-stu-id="553c9-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="553c9-146">如果你经常向用户进行批量电子邮件Microsoft 365，并且希望确保你的电子邮件以安全且及时的方式到达，请按照本部分中的提示操作。</span><span class="sxs-lookup"><span data-stu-id="553c9-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="553c9-147">确保"发送者"名称反映发送邮件的人</span><span class="sxs-lookup"><span data-stu-id="553c9-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="553c9-p109">邮件主题应是邮件内容的简要概括，且邮件正文应清楚并简洁地表明优惠、服务或产品的相关内容。 例如：</span><span class="sxs-lookup"><span data-stu-id="553c9-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>

<span data-ttu-id="553c9-150">正确：</span><span class="sxs-lookup"><span data-stu-id="553c9-150">Correct:</span></span>

> <span data-ttu-id="553c9-151">来源：marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="553c9-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="553c9-152">主题：更新了 Christmas christmas 的目录！</span><span class="sxs-lookup"><span data-stu-id="553c9-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="553c9-153">不正确：</span><span class="sxs-lookup"><span data-stu-id="553c9-153">Incorrect:</span></span>

> <span data-ttu-id="553c9-154">来源：someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="553c9-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="553c9-155">主题： 目录</span><span class="sxs-lookup"><span data-stu-id="553c9-155">Subject: Catalogs</span></span>

<span data-ttu-id="553c9-156">越容易让人知道您是谁、在做什么，您在通过大部分垃圾邮件筛选器传送邮件时遇到的困难就会越少。</span><span class="sxs-lookup"><span data-stu-id="553c9-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="553c9-157">始终在营销邮件中包含“取消订阅”选项</span><span class="sxs-lookup"><span data-stu-id="553c9-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="553c9-p110">营销邮件，尤其是新闻稿，应始终包含取消订阅未来邮件的方法。例如：</span><span class="sxs-lookup"><span data-stu-id="553c9-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="553c9-p111">一些发件人通过要求收件人发送一封主题包含"取消订阅"的电子邮件到特定别名的方法包含此选项。与上面一键单击的示例相比较，此方法并不可取。如果您一定要选择要求收件人发送邮件，请确保当他们单击链接时，所有要求的字段都已被预设。</span><span class="sxs-lookup"><span data-stu-id="553c9-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="553c9-163">为营销电子邮件或新闻稿注册使用双重加入方案。</span><span class="sxs-lookup"><span data-stu-id="553c9-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="553c9-p112">如果您的公司要求或鼓励用户注册他们的联系信息以访问您的产品或服务，则推荐本行业的最佳做法。一些公司是在注册阶段自动注册他们的用户，用于营销电子邮件或电子新闻稿，但是这在世界范围内的电子邮件筛选中，被认为是可疑的市场营销活动。</span><span class="sxs-lookup"><span data-stu-id="553c9-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="553c9-166">在注册过程中，如果"是，请向我发送您的新闻稿"或"是，请向我发送您的优惠"复选框在默认情况下处于选中状态，没有仔细查看的用户可能会无意中注册他们并不想接收的营销邮件或新闻稿。</span><span class="sxs-lookup"><span data-stu-id="553c9-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="553c9-p113">我们建议使用双重加入方案来代替，这意味着营销电子邮件或新闻稿的复选框在默认状态下处于未选中的状态。此外，用户一旦提交了注册表，就会收到一封带有 URL 的验证电子邮件，允许他们确认是否决定接收营销电子邮件。</span><span class="sxs-lookup"><span data-stu-id="553c9-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="553c9-169">这将有助于确保只有想要接收营销电子邮件的用户注册电子邮件，随后清除任何可疑的电子邮件营销活动的发送公司。</span><span class="sxs-lookup"><span data-stu-id="553c9-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="553c9-170">确保电子邮件消息内容透明且可跟踪。</span><span class="sxs-lookup"><span data-stu-id="553c9-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="553c9-p114">与发送电子邮件的方法同样重要的，是邮件包含的内容。在创建电子邮件的内容时，使用以下最佳做法确保您的电子邮件不会被电子邮件筛选服务标记。</span><span class="sxs-lookup"><span data-stu-id="553c9-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="553c9-173">当电子邮件要求收件人将发件人添加到通讯簿时，应清楚地表明此操作无法保证邮件传送。</span><span class="sxs-lookup"><span data-stu-id="553c9-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="553c9-p115">包含在邮件正文中的重定向应当是相似且一致的，不能是多样的和各不相同的。本文中的重定向不指向邮件，例如链接和文档。如果您有大量广告或"取消订阅"链接或"更新配置文件"链接，它们应全部指向同一个域。例如：</span><span class="sxs-lookup"><span data-stu-id="553c9-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>

  <span data-ttu-id="553c9-178">正确 (所有域都是同一) ：</span><span class="sxs-lookup"><span data-stu-id="553c9-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="553c9-179">所有 (域均不同时) ：</span><span class="sxs-lookup"><span data-stu-id="553c9-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="553c9-180">请避免包含大容量图片和附件的内容，或仅含一张图片的邮件。</span><span class="sxs-lookup"><span data-stu-id="553c9-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="553c9-181">您的公开隐私或 P3P 设置应清楚地说明跟踪像素（Web bug 或信号）的状态。</span><span class="sxs-lookup"><span data-stu-id="553c9-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="553c9-182">从您的数据库中删除不正确的电子邮件别名</span><span class="sxs-lookup"><span data-stu-id="553c9-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="553c9-p116">在您的数据库中创建跳回的任何电子邮件别名都是不必要的，它将使您的出站邮件面临风险 - 会受到电子邮件筛选服务的进一步审查。请确保您的电子邮件数据库是最新的。</span><span class="sxs-lookup"><span data-stu-id="553c9-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>