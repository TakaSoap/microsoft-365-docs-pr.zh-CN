---
title: 邮件流仪表板中的出站和入站邮件流见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可在安全与合规中心的"邮件流"仪表板中了解出站和&见解。
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826889"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="b2361-103">安全电子邮件合规中心中的出站和&入站邮件</span><span class="sxs-lookup"><span data-stu-id="b2361-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="b2361-104">安全 & **合规中心的** 邮件流仪表板中的 [出站和](mail-flow-insights-v2.md) 入站邮件流见解将 [来自连接器报表](view-mail-flow-reports.md#connector-report) 的信息和以前 **的 TLS 概述报告** 组合在一个位置。</span><span class="sxs-lookup"><span data-stu-id="b2361-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="b2361-105">小部件显示在向组织和从组织发送邮件时用于连接的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="b2361-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="b2361-106">当这两端提供 TLS 时，TLS 与其他电子邮件服务建立的连接都由 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="b2361-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="b2361-107">小部件提供邮件流的最后一周的快照。</span><span class="sxs-lookup"><span data-stu-id="b2361-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![安全与合规中心的邮件流仪表板中的"出站和出站&小部件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="b2361-109">小部件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护相关。</span><span class="sxs-lookup"><span data-stu-id="b2361-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="b2361-110">有关详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="b2361-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="b2361-111">使用连接器配置邮件流</span><span class="sxs-lookup"><span data-stu-id="b2361-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="b2361-112">Exchange Online 如何使用 TLS 保护电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="b2361-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="b2361-113">有关 Microsoft 365 加密的技术参考详细信息</span><span class="sxs-lookup"><span data-stu-id="b2361-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="b2361-114">由 TLS 管理员在传输中 (保护) </span><span class="sxs-lookup"><span data-stu-id="b2361-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="b2361-115">当单击 **小部件上的** "查看详细信息"时 \*\*，TLS () \*\* 浮出控件中受保护的邮件) 出发，以及如何为进入和离开组织的邮件提供 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="b2361-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在"出站和 (" (中) 单击"查看详细信息"后，由 TLS 管理中保护的邮件，传输中受 TLS 保护的浮出控件](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="b2361-117">目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="b2361-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="b2361-118">通常，您需要了解用于合规性审核的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="b2361-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="b2361-119">您可能没有与它们所拥有的大多数源和目标电子邮件服务器 (没有直接关系，也没有 Microsoft) ，因此您没有多项选项来改进这些服务器使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="b2361-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="b2361-120">但是，你可以 [使用连接器，](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 以确保对您电子邮件服务器和 Microsoft 365 之间发送的邮件实现最佳的 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="b2361-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="b2361-121">Microsoft 365 和你自己的属于合作伙伴的电子邮件服务器或服务器之间的邮件流通常比常规邮件更加重要和更敏感，因此您需要对这些邮件应用额外的安全性和漏性。</span><span class="sxs-lookup"><span data-stu-id="b2361-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="b2361-122">您可以升级或修复您自己的电子邮件服务器，以改进正在使用的 TLS 加密，或联系合作伙伴执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="b2361-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="b2361-123">连接器 **报告显示** 使用 Microsoft 365 连接器的邮件的邮件流卷和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="b2361-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="b2361-124">您可以单击连接器 **报告链接** 以转到连接器 [报告](view-mail-flow-reports.md#connector-report)。</span><span class="sxs-lookup"><span data-stu-id="b2361-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="b2361-125">如果检测到关联条件，"连接器报告 **"** 页上可能提供了以下见解：</span><span class="sxs-lookup"><span data-stu-id="b2361-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="b2361-126">**显示重要 TLS1.0 邮件流的入站合作伙伴连接器**</span><span class="sxs-lookup"><span data-stu-id="b2361-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="b2361-127">**显示重要 TLS1.0 邮件流的入站 OnPremises 连接器**</span><span class="sxs-lookup"><span data-stu-id="b2361-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="b2361-128">对于 TLS 1.0 连接，你确实需要升级电子邮件服务器或您的合作伙伴的服务器，以避免当 Microsoft 365 最终弃用 TLS 1.0 支持时出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="b2361-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2361-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2361-129">See also</span></span>

<span data-ttu-id="b2361-130">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="b2361-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
