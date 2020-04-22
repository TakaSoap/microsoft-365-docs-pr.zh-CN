---
title: 使用除名门户将自己从阻止的发件人列表中删除
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: 当您尝试向其电子邮件地址在 Microsoft 365 中的收件人发送电子邮件时，收到一条错误消息？ 如果您认为不应收到错误消息，可以使用除名门户将自己从阻止的发件人列表中删除。
ms.openlocfilehash: 39f2c9335f162f26e8bf07a213236e0e0eefef2a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636400"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="5584d-104">使用除名门户将自己从阻止的发件人列表中删除</span><span class="sxs-lookup"><span data-stu-id="5584d-104">Use the delist portal to remove yourself from the blocked senders list</span></span>

<span data-ttu-id="5584d-105">当您尝试向其电子邮件地址在 Microsoft 365 中的收件人发送电子邮件时，收到一条错误消息？</span><span class="sxs-lookup"><span data-stu-id="5584d-105">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="5584d-106">如果您认为不应收到错误消息，可以使用除名门户将自己从阻止的发件人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="5584d-106">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="5584d-107">阻止的发件人列表是什么？</span><span class="sxs-lookup"><span data-stu-id="5584d-107">What is the blocked senders list?</span></span>

<span data-ttu-id="5584d-108">Microsoft 使用阻止的发件人名单来防止其客户遭受垃圾邮件、欺诈和网络钓鱼网站的攻击。</span><span class="sxs-lookup"><span data-stu-id="5584d-108">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="5584d-109">您的邮件服务器的 IP 地址（即邮件服务器用于在 Internet 上标识自己的地址）被标记为对 Microsoft 365 的潜在威胁，原因是有多种原因。</span><span class="sxs-lookup"><span data-stu-id="5584d-109">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="5584d-110">当 Microsoft 365 将 IP 地址添加到列表中时，它会阻止 IP 地址和我们通过我们的数据中心提供的任何客户之间的进一步通信。</span><span class="sxs-lookup"><span data-stu-id="5584d-110">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="5584d-111">在您收到包含类似于以下错误的邮件回复时，您就知道自己已被添加到该列表中：</span><span class="sxs-lookup"><span data-stu-id="5584d-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="5584d-112">550 5.7.606-649 访问被拒绝，禁止发送 IP [_ip 地址_];若要请求从此列表中删除， https://sender.office.com/请访问并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="5584d-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="5584d-113">有关详细信息，请参阅[Exchange Online 中的电子邮件未送达报告](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="5584d-113">For more information see [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="5584d-114">其中  _IP address_ 是邮件服务器在其上运行的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5584d-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="5584d-115">使用除名门户将自己从阻止的发件人列表中删除</span><span class="sxs-lookup"><span data-stu-id="5584d-115">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="5584d-116">在 Web 浏览器中，请转至 [https://sender.office.com](https://sender.office.com)。</span><span class="sxs-lookup"><span data-stu-id="5584d-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>

2. <span data-ttu-id="5584d-p105">按照页面上的说明执行操作。请确保您使用收到错误消息的电子邮件地址，以及错误消息中指定的 IP 地址。每次访问只能输入一个电子邮件地址和一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5584d-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="5584d-120">Click **Submit**.</span><span class="sxs-lookup"><span data-stu-id="5584d-120">Click **Submit**.</span></span>

    <span data-ttu-id="5584d-121">门户会向您提供的电子邮件地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5584d-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="5584d-122">电子邮件的外观如下所示： ![通过除名门户提交请求时收到的电子邮件的屏幕截图](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="5584d-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="5584d-123">单击除名门户发送给您的电子邮件中的确认链接。</span><span class="sxs-lookup"><span data-stu-id="5584d-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="5584d-124">这将使您返回到除名门户。</span><span class="sxs-lookup"><span data-stu-id="5584d-124">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="5584d-125">In the delist portal, click **Delist IP**.</span><span class="sxs-lookup"><span data-stu-id="5584d-125">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="5584d-126">从阻止发件人列表中删除 IP 地址后，来自该 IP 地址的电子邮件将传递给使用 Microsoft 365 的收件人。</span><span class="sxs-lookup"><span data-stu-id="5584d-126">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="5584d-127">因此，请务必确信从该 IP 地址发送的电子邮件不会被滥用或恶意;否则，可能会再次阻止该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5584d-127">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5584d-128">在删除限制之前，可能需要长达24小时或结果相差很大。</span><span class="sxs-lookup"><span data-stu-id="5584d-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="5584d-129">请参阅[在 office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)和[office 365 中的出站垃圾邮件保护](outbound-spam-controls.md)以防止 IP 被列入黑名单。</span><span class="sxs-lookup"><span data-stu-id="5584d-129">See [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>
