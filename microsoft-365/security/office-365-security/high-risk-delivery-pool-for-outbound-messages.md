---
title: 出站传递池
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
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用传递池来保护 Microsoft 365 数据中心中的电子邮件服务器的声誉。
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201485"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="e4971-103">出站传递池</span><span class="sxs-lookup"><span data-stu-id="e4971-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4971-104">Microsoft 365 数据中心中的电子邮件服务器可能暂时 guilty 发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="e4971-105">例如，在内部部署电子邮件组织中通过 Microsoft 365 发送出站邮件的恶意软件或恶意垃圾邮件攻击，或者是 Microsoft 365 帐户受到危害。</span><span class="sxs-lookup"><span data-stu-id="e4971-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="e4971-106">攻击者还会尝试通过 Microsoft 365 转发中继邮件来避免检测。</span><span class="sxs-lookup"><span data-stu-id="e4971-106">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="e4971-107">这些方案可能会导致出现在第三方阻止列表中的受影响的 Microsoft 365 数据中心服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e4971-107">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="e4971-108">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-108">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="e4971-109">高风险传递池</span><span class="sxs-lookup"><span data-stu-id="e4971-109">High-risk delivery pool</span></span>
<span data-ttu-id="e4971-110">为防止出现这种情况，通过_高风险传递池_发送来自确定为垃圾邮件的 Microsoft 365 datacenter server 中的所有出站邮件，或超出[服务](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)的发送限制或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)的所有出站邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-110">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="e4971-111">高风险传递池是仅用于发送 "低质量" 邮件的出站电子邮件的单独 IP 地址池 (例如，垃圾邮件和 [退信](backscatter-messages-and-eop.md)) 。</span><span class="sxs-lookup"><span data-stu-id="e4971-111">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="e4971-112">使用高风险传递池有助于阻止出站电子邮件的常规 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-112">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="e4971-113">出站电子邮件的常规 IP 地址池维护发送 "高质量" 邮件的信誉，从而降低了这些 IP 地址在 IP 阻止列表中出现的可能性。</span><span class="sxs-lookup"><span data-stu-id="e4971-113">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="e4971-114">高风险传递池中的 IP 地址可能会保留在 IP 阻止列表中，但这是设计的。</span><span class="sxs-lookup"><span data-stu-id="e4971-114">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="e4971-115">无法保证传递给预期的收件人，因为很多电子邮件组织不接受来自高风险传递池的邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-115">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="e4971-116">有关详细信息，请参阅 [控制出站垃圾邮件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="e4971-116">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e4971-117">源电子邮件域没有记录且在公用 DNS 中定义的任何 MX 记录都不会通过高风险传递池路由（无论其垃圾邮件或发送限制处置）的邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-117">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="e4971-118">退回邮件</span><span class="sxs-lookup"><span data-stu-id="e4971-118">Bounce messages</span></span>

<span data-ttu-id="e4971-119">出站高风险传递池管理所有未送达报告的传递 (也称为 Ndr、退回邮件、传递状态通知或 Dsn) 。</span><span class="sxs-lookup"><span data-stu-id="e4971-119">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="e4971-120">Ndr 中的电涌可能的原因包括：</span><span class="sxs-lookup"><span data-stu-id="e4971-120">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="e4971-121">对使用服务的客户之一产生影响的欺骗活动。</span><span class="sxs-lookup"><span data-stu-id="e4971-121">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="e4971-122">目录搜集攻击。</span><span class="sxs-lookup"><span data-stu-id="e4971-122">A directory harvest attack.</span></span>
- <span data-ttu-id="e4971-123">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="e4971-123">A spam attack.</span></span>
- <span data-ttu-id="e4971-124">一个欺诈性电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="e4971-124">A rogue email server.</span></span>

<span data-ttu-id="e4971-125">所有这些问题都会导致服务处理的 Ndr 数量突然增加。</span><span class="sxs-lookup"><span data-stu-id="e4971-125">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="e4971-126">许多情况下，这些 Ndr 看上去是垃圾邮件发送到其他电子邮件服务器和服务 (也称为 _[退信](backscatter-messages-and-eop.md)_) 。</span><span class="sxs-lookup"><span data-stu-id="e4971-126">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="e4971-127">中继池</span><span class="sxs-lookup"><span data-stu-id="e4971-127">Relay pool</span></span>

<span data-ttu-id="e4971-128">从 Microsoft 365 转发或中继的邮件是使用特殊中继池发送的，因为最终目标不应将 Microsoft 365 视为实际发件人。</span><span class="sxs-lookup"><span data-stu-id="e4971-128">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="e4971-129">由于 autoforwarding 或中继电子邮件不在 Microsoft 365 中，因此我们也需要隔离此流量，这一点也非常重要。</span><span class="sxs-lookup"><span data-stu-id="e4971-129">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="e4971-130">与高风险传递池类似，一个单独的 IP 地址池用于中继邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-130">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="e4971-131">此地址池不会发布，因为它可能会经常更改。</span><span class="sxs-lookup"><span data-stu-id="e4971-131">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="e4971-132">Microsoft 365 需要验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="e4971-132">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="e4971-133">若要执行此操作，电子邮件身份验证 (SPF、DKIM 和 DMARC) 需要在收到我们的邮件时传递。</span><span class="sxs-lookup"><span data-stu-id="e4971-133">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="e4971-134">在我们可以对发件人进行身份验证的情况下，我们将使用发件人改写来帮助收件人知道转发的邮件来自受信任的源。</span><span class="sxs-lookup"><span data-stu-id="e4971-134">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="e4971-135">您可以阅读有关如何工作的详细信息，以及您可以执行哪些操作以帮助确保发送域在 [发件人重写方案 (SRS) ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)中传递身份验证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e4971-135">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
