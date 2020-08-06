---
title: 邮件流仪表板中的出站和入站邮件流洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的出站和入站邮件流洞察力。
ms.openlocfilehash: 347e53c51c347f12795008d39458773a94ff433f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577365"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="e319e-103">安全 & 合规中心中的出站和入站邮件流洞察力</span><span class="sxs-lookup"><span data-stu-id="e319e-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="e319e-104">Security & 合规中心的[邮件流仪表板](mail-flow-insights-v2.md)中的**出站和入站邮件流**洞察力将[连接器报告](view-mail-flow-reports.md#connector-report)中的信息和以前的**TLS 概述报告**合并到一个位置。</span><span class="sxs-lookup"><span data-stu-id="e319e-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="e319e-105">当邮件传递到组织或从组织中传递时，该小组件将显示用于连接的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="e319e-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="e319e-106">当双方提供 TLS 时，使用其他电子邮件服务建立的连接将由 TLS 进行加密。</span><span class="sxs-lookup"><span data-stu-id="e319e-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="e319e-107">小组件提供邮件流的最后一周的快照。</span><span class="sxs-lookup"><span data-stu-id="e319e-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Security & 合规中心的邮件流仪表板中的出站和入站邮件流小组件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="e319e-109">小组件中的信息与 Microsoft 365 中的连接器和 TLS 邮件保护有关。</span><span class="sxs-lookup"><span data-stu-id="e319e-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="e319e-110">有关详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="e319e-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="e319e-111">使用连接器配置邮件流</span><span class="sxs-lookup"><span data-stu-id="e319e-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="e319e-112">Exchange Online 如何使用 TLS 保护电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="e319e-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="e319e-113">有关 Microsoft 365 中的加密的技术参考详细信息</span><span class="sxs-lookup"><span data-stu-id="e319e-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="e319e-114">TLS 在 (传输中保护的邮件) </span><span class="sxs-lookup"><span data-stu-id="e319e-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="e319e-115">当您单击小部件上的 "**查看详细信息**" 时，\*\*受 TLS 保护的邮件 (由 TLS) \*\*浮出控件向您显示进入和离开组织的邮件的 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="e319e-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在单击 "出站和入站电子邮件" 小组件上的 "查看详细信息" 之后，在传输 (由 TLS) 浮出的邮件](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="e319e-117">目前，TLS 1.2 是 Microsoft 365 提供的最安全的 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="e319e-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="e319e-118">通常，您需要知道正在用于合规性审核的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="e319e-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="e319e-119">您可能没有与源和目标电子邮件服务器的直接关系 (你不拥有它们，也不会) Microsoft。因此，Microsoft 不，因此不会有许多选项可用于改进这些服务器所使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="e319e-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="e319e-120">不过，您可以使用[连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)来确保在电子邮件服务器和 Microsoft 365 之间发送的邮件的最佳可用 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="e319e-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="e319e-121">在 Microsoft 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间流动的邮件通常比常规邮件更重要且敏感，因此您需要对这些邮件应用额外的安全和 vigilance。</span><span class="sxs-lookup"><span data-stu-id="e319e-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="e319e-122">您可以升级或修复自己的电子邮件服务器，以改进正在使用的 TLS 加密，或与您的合作伙伴进行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="e319e-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="e319e-123">**连接器报告**为使用 Microsoft 365 连接器的邮件显示邮件流卷和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="e319e-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="e319e-124">您可以单击 "**连接器报告**" 链接以转到[连接器报告](view-mail-flow-reports.md#connector-report)。</span><span class="sxs-lookup"><span data-stu-id="e319e-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="e319e-125">如果检测到相关的条件，**连接器报告**页上可能会提供以下见解：</span><span class="sxs-lookup"><span data-stu-id="e319e-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="e319e-126">**入站合作伙伴连接器查看有效的 TLS 1.0 邮件流**</span><span class="sxs-lookup"><span data-stu-id="e319e-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="e319e-127">**入站 OnPremises 连接器查看有效的 TLS 1.0 邮件流**</span><span class="sxs-lookup"><span data-stu-id="e319e-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="e319e-128">对于 TLS 1.0 连接，确实需要将您的电子邮件服务器或合作伙伴的服务器升级或修复，以避免在 Microsoft 365 中最终弃用 TLS 1.0 支持时出现的任何问题。</span><span class="sxs-lookup"><span data-stu-id="e319e-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="e319e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e319e-129">See also</span></span>

<span data-ttu-id="e319e-130">有关邮件流仪表板中的其他见解的信息，请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e319e-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
