---
title: 非客户向 Microsoft 365 发送邮件的服务
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 为了维护用户对使用电子邮件的信任，Microsoft 已出台多项帮助保护我们的用户的策略和技术。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879d2c9d3bc2af0f78a25eb1381a74b67171e939
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290759"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="bb753-103">非客户向 Microsoft 365 发送邮件的服务</span><span class="sxs-lookup"><span data-stu-id="bb753-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bb753-104">电子邮件滥用、垃圾邮件和欺诈邮件（网络钓鱼）继续增加整个电子邮件系统的负担。</span><span class="sxs-lookup"><span data-stu-id="bb753-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="bb753-105">为了帮助保持用户对电子邮件使用的信任，Microsoft 已制定各种策略和技术来帮助保护我们的用户。</span><span class="sxs-lookup"><span data-stu-id="bb753-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="bb753-106">然而，Microsoft 知道合法的电子邮件不应受到负面影响。</span><span class="sxs-lookup"><span data-stu-id="bb753-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="bb753-107">因此，我们建立了一套服务，通过主动管理发件人的发送信誉来帮助发件人提高向 Microsoft 365 用户传递电子邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="bb753-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="bb753-108">本概述提供有关我们向组织提供的好处的信息，即使你不是客户。</span><span class="sxs-lookup"><span data-stu-id="bb753-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="bb753-109">发件人解决方案</span><span class="sxs-lookup"><span data-stu-id="bb753-109">Sender solutions</span></span>

****

|<span data-ttu-id="bb753-110">服务</span><span class="sxs-lookup"><span data-stu-id="bb753-110">Service</span></span>|<span data-ttu-id="bb753-111">优点</span><span class="sxs-lookup"><span data-stu-id="bb753-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="bb753-112">此联机帮助内容</span><span class="sxs-lookup"><span data-stu-id="bb753-112">This online help content</span></span>|<span data-ttu-id="bb753-113">提供：</span><span class="sxs-lookup"><span data-stu-id="bb753-113">Provides:</span></span> <ul><li><span data-ttu-id="bb753-114">与向 EOP 用户传递通信的任何问题的起点。</span><span class="sxs-lookup"><span data-stu-id="bb753-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="bb753-115">包含一个简单的在线指南，其中包含我们的策略和要求。</span><span class="sxs-lookup"><span data-stu-id="bb753-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="bb753-116">Microsoft 所采用垃圾邮件筛选器和身份验证技术的概述。</span><span class="sxs-lookup"><span data-stu-id="bb753-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="bb753-117">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="bb753-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="bb753-118">提供有关传送问题的自助和升级支持。</span><span class="sxs-lookup"><span data-stu-id="bb753-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="bb753-119">反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="bb753-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="bb753-p102">一种提交 IP 除名请求的工具。在提交此请求前，发件人有责任确保任何源自可疑 IP 的后续邮件不是滥用的或恶意的。</span><span class="sxs-lookup"><span data-stu-id="bb753-p102">A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="bb753-122">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="bb753-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="bb753-123">防止从 Exchange Online 发送垃圾邮件和其他不需要的邮件，使 Internet 和邮件系统变得混乱。</span><span class="sxs-lookup"><span data-stu-id="bb753-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="bb753-124">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="bb753-124">Microsoft support</span></span>

<span data-ttu-id="bb753-125">Microsoft 为向 Microsoft 365 收件人发送邮件时遇到问题的人提供了多种支持选项。</span><span class="sxs-lookup"><span data-stu-id="bb753-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="bb753-126">我们建议您：</span><span class="sxs-lookup"><span data-stu-id="bb753-126">We recommend that you:</span></span>

- <span data-ttu-id="bb753-127">在您接收到的任何未送达报告中，按照说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="bb753-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="bb753-128">请查看[向 Office 365 发送故障排除邮件](troubleshooting-mail-sent-to-office-365.md)中非客户遇到的最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="bb753-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="bb753-129">使用 [Microsoft 365](https://sender.office.com) 除名门户提交从阻止的发件人列表中删除 IP 的请求。</span><span class="sxs-lookup"><span data-stu-id="bb753-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="bb753-130">参阅 [Microsoft 社区论坛](https://community.office365.com/f/)。</span><span class="sxs-lookup"><span data-stu-id="bb753-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="bb753-131">使用另一种方法联系你尝试发送电子邮件的客户，让他们联系 Microsoft 支持部门并代表你打开支持票证。</span><span class="sxs-lookup"><span data-stu-id="bb753-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="bb753-132">在某些情况下，出于法律原因，Microsoft 支持必须与拥有被阻止的 IP 空间的发件人直接沟通。</span><span class="sxs-lookup"><span data-stu-id="bb753-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="bb753-133">但是，非客户通常无法开立支持票证。</span><span class="sxs-lookup"><span data-stu-id="bb753-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="bb753-134">有关对 Office 365 的 Microsoft 技术支持的详细信息，请参阅 [支持](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)。</span><span class="sxs-lookup"><span data-stu-id="bb753-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="bb753-135">反垃圾邮件 IP 除名门户</span><span class="sxs-lookup"><span data-stu-id="bb753-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="bb753-136">这是一个自助服务门户，可用于将自己从 Microsoft 365 阻止的发件人名单中删除。</span><span class="sxs-lookup"><span data-stu-id="bb753-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="bb753-137">如果你尝试向电子邮件地址在 Microsoft 365 中的收件人发送电子邮件，并且你认为你不应是收件人，请使用此门户。</span><span class="sxs-lookup"><span data-stu-id="bb753-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="bb753-138">有关详细信息，请参阅[使用除名门户来将自己从阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="bb753-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="bb753-139">源自 Exchange Online 的垃圾邮件的滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="bb753-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="bb753-140">有时，第三方会使用 Microsoft365 发送垃圾邮件，这违反了我们的使用条款和策略。</span><span class="sxs-lookup"><span data-stu-id="bb753-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="bb753-141">如果收到来自 Office 365 的任何垃圾邮件，可以将这些邮件报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="bb753-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="bb753-142">有关说明，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bb753-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
