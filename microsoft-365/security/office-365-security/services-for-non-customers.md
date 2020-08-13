---
title: 将邮件发送到 Microsoft 365 的非客户服务
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: 74389d3b975a0ffaebdc1619be40fd3ac74d72f4
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652653"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="265a8-103">将邮件发送到 Microsoft 365 的非客户服务</span><span class="sxs-lookup"><span data-stu-id="265a8-103">Services for non-customers sending mail to Microsoft 365</span></span>

<span data-ttu-id="265a8-104">电子邮件滥用、垃圾邮件和欺诈邮件（网络钓鱼）继续增加整个电子邮件系统的负担。</span><span class="sxs-lookup"><span data-stu-id="265a8-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="265a8-105">为了帮助维护对电子邮件使用的用户信任，Microsoft 已实施各种策略和技术来帮助保护我们的用户。</span><span class="sxs-lookup"><span data-stu-id="265a8-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="265a8-106">然而，Microsoft 知道合法的电子邮件不应受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="265a8-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="265a8-107">因此，我们已经建立了一套服务，帮助发件人通过主动管理其发送信誉来提高将电子邮件传递给 Microsoft 365 用户的能力。</span><span class="sxs-lookup"><span data-stu-id="265a8-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="265a8-108">本概述提供了我们为你的组织提供的好处的相关信息（即使你不是客户）。</span><span class="sxs-lookup"><span data-stu-id="265a8-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="265a8-109">发件人解决方案</span><span class="sxs-lookup"><span data-stu-id="265a8-109">Sender solutions</span></span>

****

|<span data-ttu-id="265a8-110">服务</span><span class="sxs-lookup"><span data-stu-id="265a8-110">Service</span></span>|<span data-ttu-id="265a8-111">优点</span><span class="sxs-lookup"><span data-stu-id="265a8-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="265a8-112">此联机帮助内容</span><span class="sxs-lookup"><span data-stu-id="265a8-112">This online help content</span></span>|<span data-ttu-id="265a8-113">提供：</span><span class="sxs-lookup"><span data-stu-id="265a8-113">Provides:</span></span> <br/> <span data-ttu-id="265a8-114">有关向 EOP 用户提供通信的任何问题的起始点。</span><span class="sxs-lookup"><span data-stu-id="265a8-114">A starting point for any questions related to delivering communications to EOP users.</span></span> <br/><br/> <span data-ttu-id="265a8-115">包含一个包含我们的策略和要求的简单联机指南。</span><span class="sxs-lookup"><span data-stu-id="265a8-115">Includes a simple online guide with our policies and requirements.</span></span> <br/><br/> <span data-ttu-id="265a8-116">Microsoft 所采用的垃圾邮件筛选器和身份验证技术的概述。</span><span class="sxs-lookup"><span data-stu-id="265a8-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span>|
|[<span data-ttu-id="265a8-117">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="265a8-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="265a8-118">提供有关传送问题的自助和升级支持。</span><span class="sxs-lookup"><span data-stu-id="265a8-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="265a8-119">反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="265a8-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="265a8-p102">一种提交 IP 除名请求的工具。在提交此请求前，发件人有责任确保任何源自可疑 IP 的后续邮件不是滥用的或恶意的。</span><span class="sxs-lookup"><span data-stu-id="265a8-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="265a8-122">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="265a8-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="265a8-123">阻止从 Exchange Online 发送垃圾邮件和其他不需要的邮件，并将 internet 和邮件系统打乱。</span><span class="sxs-lookup"><span data-stu-id="265a8-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="265a8-124">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="265a8-124">Microsoft support</span></span>

<span data-ttu-id="265a8-125">Microsoft 为在向 Microsoft 365 的收件人发送邮件时遇到问题的用户提供多种支持选项。</span><span class="sxs-lookup"><span data-stu-id="265a8-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="265a8-126">我们建议您：</span><span class="sxs-lookup"><span data-stu-id="265a8-126">We recommend that you:</span></span>

- <span data-ttu-id="265a8-127">在您接收到的任何未送达报告中，按照说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="265a8-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="265a8-128">请查看[向 Office 365 发送故障排除邮件](troubleshooting-mail-sent-to-office-365.md)中非客户遇到的最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="265a8-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="265a8-129">使用[Microsoft 365 除名门户](https://sender.office.com)提交请求，以将您的 IP 从阻止的发件人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="265a8-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="265a8-130">参阅 [Microsoft 社区论坛](https://community.office365.com/f/)。</span><span class="sxs-lookup"><span data-stu-id="265a8-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="265a8-131">使用另一种方法联系你尝试使用电子邮件发送的客户，并要求他们联系 Microsoft 支持部门，并代表你打开支持票证。</span><span class="sxs-lookup"><span data-stu-id="265a8-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="265a8-132">在某些情况下，出于法律原因，Microsoft 支持必须与拥有被阻止的 IP 空间的发件人直接沟通。</span><span class="sxs-lookup"><span data-stu-id="265a8-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="265a8-133">但是，非客户通常无法开立支持票证。</span><span class="sxs-lookup"><span data-stu-id="265a8-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="265a8-134">有关对 Office 365 的 Microsoft 技术支持的详细信息，请参阅 [支持](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)。</span><span class="sxs-lookup"><span data-stu-id="265a8-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="265a8-135">反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="265a8-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="265a8-136">这是一个自助服务门户，可用于将自己从 Microsoft 365 阻止的发件人列表中删除。</span><span class="sxs-lookup"><span data-stu-id="265a8-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="265a8-137">如果您在尝试向其电子邮件地址位于 Microsoft 365 的收件人发送电子邮件时收到错误消息，并且您认为您不应这样做，请使用此门户。</span><span class="sxs-lookup"><span data-stu-id="265a8-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="265a8-138">有关详细信息，请参阅[使用除名门户来将自己从阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="265a8-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="265a8-139">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="265a8-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="265a8-140">有时，第三方使用 Microsoft365 来发送垃圾邮件，从而违反我们的使用条款和策略。</span><span class="sxs-lookup"><span data-stu-id="265a8-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="265a8-141">如果您收到来自 Office 365 的任何垃圾邮件，您可以将这些邮件报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="265a8-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="265a8-142">有关说明，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="265a8-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
