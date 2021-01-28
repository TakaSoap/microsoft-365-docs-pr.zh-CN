---
title: 邮件流仪表板中的出站和入站邮件流见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以在安全与合规中心的邮件流仪表板中了解出站和入站&见解。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029818"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="80a1f-103">安全与合规中心中的出站和入站&见解</span><span class="sxs-lookup"><span data-stu-id="80a1f-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="80a1f-104">安全 [&](https://protection.office.com)**与** 合规中心内邮件流仪表板 [](mail-flow-insights-v2.md)中的出站和入站邮件流见解将连接器报告中的信息和以前的 **TLS** [](view-mail-flow-reports.md#connector-report)概述报告中的信息合并在一处。</span><span class="sxs-lookup"><span data-stu-id="80a1f-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="80a1f-105">小组件在邮件发送到组织或从组织发送邮件时显示用于连接的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="80a1f-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="80a1f-106">当 TLS 由双方提供时，TLS 会加密与其他电子邮件服务建立的连接。</span><span class="sxs-lookup"><span data-stu-id="80a1f-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="80a1f-107">小部件提供上一周的邮件流的快照。</span><span class="sxs-lookup"><span data-stu-id="80a1f-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![安全与合规中心的"邮件流"仪表板中的"出站和入站&小组件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="80a1f-109">小部件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护相关。</span><span class="sxs-lookup"><span data-stu-id="80a1f-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="80a1f-110">有关详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="80a1f-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="80a1f-111">使用连接器配置邮件流</span><span class="sxs-lookup"><span data-stu-id="80a1f-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="80a1f-112">Exchange Online 如何使用 TLS 保护电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="80a1f-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="80a1f-113">有关 Microsoft 365 中加密的技术参考详细信息</span><span class="sxs-lookup"><span data-stu-id="80a1f-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="80a1f-114">在传输过程中受 TLS (保护) </span><span class="sxs-lookup"><span data-stu-id="80a1f-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="80a1f-115">单击小组件 **上的"** 查看详细信息"时，受 **TLS** (保护的邮件) 显示对进入和离开组织的邮件的 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="80a1f-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在传输过程中 (由 TLS) 在单击"出站和入站电子邮件"小部件上的"查看详细信息"后出现的) 显示](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="80a1f-117">目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="80a1f-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="80a1f-118">通常，你需要知道用于合规性审核的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="80a1f-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="80a1f-119">你可能与大部分源和目标电子邮件服务器没有直接关系 (而 Microsoft) 也不拥有，因此，你没有很多选项可以改进这些服务器使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="80a1f-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="80a1f-120">但是，您可以使用 [连接器来确保](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 电子邮件服务器和 Microsoft 365 之间发送的邮件的最佳 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="80a1f-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="80a1f-121">Microsoft 365 和属于合作伙伴的您自己的电子邮件服务器之间的邮件流通常比常规邮件更加重要和敏感，因此你需要为这些邮件应用额外的安全性和安全性。</span><span class="sxs-lookup"><span data-stu-id="80a1f-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="80a1f-122">您可以升级或修复自己的电子邮件服务器，以改进所使用的 TLS 加密，或联系合作伙伴以执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="80a1f-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="80a1f-123">连接器 **报告** 显示使用 Microsoft 365 连接器的邮件的邮件流卷和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="80a1f-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="80a1f-124">You can click the **Connector report** link to go to the [Connector report.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="80a1f-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="80a1f-125">如果检测到关联条件，则连接器报告页面上可能会提供以下见解：</span><span class="sxs-lookup"><span data-stu-id="80a1f-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="80a1f-126">**入站合作伙伴连接器看到大量 TLS1.0 邮件流**</span><span class="sxs-lookup"><span data-stu-id="80a1f-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="80a1f-127">**入站 OnPremises 连接器看到大量 TLS1.0 邮件流**</span><span class="sxs-lookup"><span data-stu-id="80a1f-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="80a1f-128">对于 TLS 1.0 连接，你确实需要升级或修复电子邮件服务器或合作伙伴的服务器，以避免在 Microsoft 365 中最终弃用 TLS 1.0 支持时出现任何问题。</span><span class="sxs-lookup"><span data-stu-id="80a1f-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="80a1f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80a1f-129">See also</span></span>

<span data-ttu-id="80a1f-130">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="80a1f-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
