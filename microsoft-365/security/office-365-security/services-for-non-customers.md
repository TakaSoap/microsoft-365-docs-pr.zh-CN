---
title: 非客户向 Office 365 发送邮件的服务
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 为了维护用户对使用电子邮件的信任，Microsoft 已出台多项帮助保护我们的用户的策略和技术。
ms.openlocfilehash: 9e7985aed7c0b5b5c14c64d49e70ec6c731cb8b9
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032788"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a><span data-ttu-id="e50e0-103">非客户向 Office 365 发送邮件的服务</span><span class="sxs-lookup"><span data-stu-id="e50e0-103">Services for non-customers sending mail to Office 365</span></span>

<span data-ttu-id="e50e0-p101">电子邮件滥用、垃圾邮件和欺诈邮件（网络钓鱼）继续增加整个电子邮件系统的负担。为了维护用户对使用电子邮件的信任，Microsoft 已出台多项帮助保护我们的用户的策略和技术。然而，Microsoft 知道合法的电子邮件不应受到负面影响。因此，我们建立了一系列服务，通过主动管理他们的发送信誉，来帮助发件人提高他们向 Office 365 用户传送电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="e50e0-p101">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem. To help maintain user trust in the use of email, Microsoft has put in place various policies and technologies to help protect our users. However, Microsoft understands that legitimate email should not be negatively affected. Therefore, we have established a suite of services to help senders improve their ability to deliver email to Office 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="e50e0-108">本概述提供了我们为您的组织所提供优势的相关信息（即使您不是 Office 365 客户）。</span><span class="sxs-lookup"><span data-stu-id="e50e0-108">This overview provides information about benefits we provide to your organization even if you aren't an Office 365 customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="e50e0-109">发件人解决方案</span><span class="sxs-lookup"><span data-stu-id="e50e0-109">Sender solutions</span></span>

|<span data-ttu-id="e50e0-110">**服务**</span><span class="sxs-lookup"><span data-stu-id="e50e0-110">**Service**</span></span>|<span data-ttu-id="e50e0-111">**优势**</span><span class="sxs-lookup"><span data-stu-id="e50e0-111">**Benefits**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e50e0-112">此联机帮助内容</span><span class="sxs-lookup"><span data-stu-id="e50e0-112">This online help content</span></span>| <span data-ttu-id="e50e0-113">提供：</span><span class="sxs-lookup"><span data-stu-id="e50e0-113">Provides:</span></span>  <br/>  <span data-ttu-id="e50e0-114">有关向 EOP 用户传送通信的任何问题的起点</span><span class="sxs-lookup"><span data-stu-id="e50e0-114">A starting point for any questions related to delivering communications to EOP users</span></span>  <br/>  <span data-ttu-id="e50e0-115">包括有关我们的策略和要求的简单在线指南</span><span class="sxs-lookup"><span data-stu-id="e50e0-115">Includes a simple online guide with our policies and requirements</span></span>  <br/>  <span data-ttu-id="e50e0-116">Microsoft 采用的垃圾邮件筛选器和身份验证技术的概述</span><span class="sxs-lookup"><span data-stu-id="e50e0-116">An overview of the junk email filters and authentication technologies employed by Microsoft</span></span>|
|[<span data-ttu-id="e50e0-117">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="e50e0-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="e50e0-118">提供有关传送问题的自助和升级支持。</span><span class="sxs-lookup"><span data-stu-id="e50e0-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="e50e0-119">Office 365 反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="e50e0-119">Office 365 Anti-Spam IP Delist Portal</span></span>](#office-365-anti-spam-ip-delist-portal)|<span data-ttu-id="e50e0-p102">一种提交 IP 除名请求的工具。在提交此请求前，发件人有责任确保任何源自可疑 IP 的后续邮件不是滥用的或恶意的。</span><span class="sxs-lookup"><span data-stu-id="e50e0-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="e50e0-122">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="e50e0-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="e50e0-123">阻止从 Exchange Online 发送垃圾邮件或其他不必要的邮件，并阻止 Internet 和邮件系统出现混乱。</span><span class="sxs-lookup"><span data-stu-id="e50e0-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the Internet and your mail system.</span></span>|

## <a name="microsoft-support"></a><span data-ttu-id="e50e0-124">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="e50e0-124">Microsoft support</span></span>

<span data-ttu-id="e50e0-p103">Microsoft 提供了多种支持方案，以支持向 Office 365 收件箱发送邮件遇到问题的用户。我们建议您：</span><span class="sxs-lookup"><span data-stu-id="e50e0-p103">Microsoft offers several support options for people having trouble sending mail to Office 365 inboxes. We recommend that you:</span></span>

- <span data-ttu-id="e50e0-127">在您接收到的任何未送达报告中，按照说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="e50e0-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="e50e0-128">请查看[向 Office 365 发送故障排除邮件](troubleshooting-mail-sent-to-office-365.md)中非客户遇到的最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="e50e0-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="e50e0-129">使用 [Office 365 除名门户](https://sender.office.com)提交请求以将您的 IP 从被阻止的发件人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="e50e0-129">Use the [Office 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="e50e0-130">参阅 [Microsoft 社区论坛](https://community.office365.com/f/)。</span><span class="sxs-lookup"><span data-stu-id="e50e0-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="e50e0-p104">使用另一种方法联系您正在尝试发送邮件的 Office 365 客户，让他们联系 Microsoft 支持，并代表您开立支持票证。在某些情况下，出于法律原因，Microsoft 支持必须与拥有被阻止的 IP 空间的发件人直接沟通。但是，非客户通常无法开立支持票证。</span><span class="sxs-lookup"><span data-stu-id="e50e0-p104">Contact the Office 365 customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf. In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked. However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="e50e0-134">有关对 Office 365 的 Microsoft 技术支持的详细信息，请参阅 [支持](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)。</span><span class="sxs-lookup"><span data-stu-id="e50e0-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="office-365-anti-spam-ip-delist-portal"></a><span data-ttu-id="e50e0-135">Office 365 反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="e50e0-135">Office 365 Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="e50e0-p105">您可以使用这个自助式门户将自己从 Office 365 阻止的发件人名单中删除。如果您在尝试向收件人发送电子邮件时收到一条您认为不应该收到的错误消息（该收件人的电子邮件地址在 Office 365 中），那么您可以使用该门户。有关详细信息，请参阅[使用除名门户来将自己从 Office 365 阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="e50e0-p105">This is a self-service portal you can use to remove yourself from the Office 365 blocked senders list. Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Office 365 and you don't think you should be. For more information, see [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="e50e0-139">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="e50e0-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="e50e0-140">有时第三方使用 Office 365 来发送垃圾邮件，违反了我们的使用条款和策略。</span><span class="sxs-lookup"><span data-stu-id="e50e0-140">Sometimes Office 365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="e50e0-141">如果您收到来自 Office 365 的任何垃圾邮件，您可以将这些邮件报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e50e0-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="e50e0-142">有关说明，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="e50e0-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
