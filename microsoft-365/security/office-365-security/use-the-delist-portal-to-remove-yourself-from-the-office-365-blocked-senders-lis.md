---
title: 将自己从阻止的发件人名单中删除
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 本文将了解如何使用除名门户将自己从阻止的Microsoft 365列表中。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203706"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="073dc-103">使用除名门户将自己从阻止的发件人名单中删除</span><span class="sxs-lookup"><span data-stu-id="073dc-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="073dc-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="073dc-104">**Applies to**</span></span>
- [<span data-ttu-id="073dc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="073dc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="073dc-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="073dc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="073dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="073dc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="073dc-108">当您尝试向电子邮件地址位于邮箱中的收件人发送电子邮件时，是否收到Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="073dc-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="073dc-109">如果您认为不应收到错误消息，您可以使用除名门户将自己从阻止的发件人名单中删除。</span><span class="sxs-lookup"><span data-stu-id="073dc-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="073dc-110">阻止的发件人名单是什么？</span><span class="sxs-lookup"><span data-stu-id="073dc-110">What is the blocked senders list?</span></span>

<span data-ttu-id="073dc-111">Microsoft 使用阻止的发件人名单来防止其客户遭受垃圾邮件、欺诈和网络钓鱼网站的攻击。</span><span class="sxs-lookup"><span data-stu-id="073dc-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="073dc-112">您的邮件服务器的 IP 地址（即您的邮件服务器在 Internet 上用于标识自身的地址）被标记为对邮件Microsoft 365各种原因之一的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="073dc-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="073dc-113">当Microsoft 365 IP 地址添加到列表中时，它会阻止 IP 地址与任何客户通过我们的数据中心进行进一步的通信。</span><span class="sxs-lookup"><span data-stu-id="073dc-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="073dc-114">在您收到包含类似于以下错误的邮件回复时，您就知道自己已被添加到该列表中：</span><span class="sxs-lookup"><span data-stu-id="073dc-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="073dc-115">550 5.7.606-649 访问被拒绝，已禁止发送 IP [_IP 地址_];若要请求从此列表删除，请访问 <https://sender.office.com/> 并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="073dc-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="073dc-116">有关详细信息，请参阅电子邮件[中的未送达Exchange Online。](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="073dc-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="073dc-117">其中  _IP address_ 是邮件服务器在其上运行的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="073dc-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="073dc-118">使用除名门户将自己从阻止的发件人名单中删除</span><span class="sxs-lookup"><span data-stu-id="073dc-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="073dc-119">在 Web 浏览器中，请转至 <https://sender.office.com>。</span><span class="sxs-lookup"><span data-stu-id="073dc-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="073dc-p104">按照页面上的说明执行操作。请确保您使用收到错误消息的电子邮件地址，以及错误消息中指定的 IP 地址。每次访问只能输入一个电子邮件地址和一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="073dc-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="073dc-123">Click **Submit**.</span><span class="sxs-lookup"><span data-stu-id="073dc-123">Click **Submit**.</span></span>

    <span data-ttu-id="073dc-124">门户会向您提供的电子邮件地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="073dc-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="073dc-125">电子邮件将如下所示：通过除名门户提交请求时收到 ![ 的电子邮件的屏幕截图](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="073dc-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="073dc-126">单击除名门户发送给您的电子邮件中的确认链接。</span><span class="sxs-lookup"><span data-stu-id="073dc-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="073dc-127">这将使您返回到除名门户。</span><span class="sxs-lookup"><span data-stu-id="073dc-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="073dc-128">In the delist portal, click **Delist IP**.</span><span class="sxs-lookup"><span data-stu-id="073dc-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="073dc-129">从阻止的发件人列表中删除 IP 地址后，来自该 IP 地址的电子邮件将传递给使用"发件人"Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="073dc-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="073dc-130">因此，请确保你确信从该 IP 地址发送的电子邮件不会滥用或恶意;否则，可能会再次阻止 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="073dc-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="073dc-131">可能需要最多 24 小时，或者结果在删除限制之前可能会有很大差异。</span><span class="sxs-lookup"><span data-stu-id="073dc-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="073dc-132">请参阅 [在 EOP 中创建](create-safe-sender-lists-in-office-365.md) 安全发件人列表和 [EOP](outbound-spam-controls.md) 中的出站垃圾邮件保护，以防止阻止 IP。</span><span class="sxs-lookup"><span data-stu-id="073dc-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>