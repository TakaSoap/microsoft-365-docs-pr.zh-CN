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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用传递池保护 Microsoft 365 数据中心中电子邮件服务器的信誉。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289801"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="2f5a3-103">出站传递池</span><span class="sxs-lookup"><span data-stu-id="2f5a3-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2f5a3-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2f5a3-104">**Applies to**</span></span>
- [<span data-ttu-id="2f5a3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2f5a3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2f5a3-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2f5a3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2f5a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2f5a3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2f5a3-108">Microsoft 365 数据中心中的电子邮件服务器可能暂时有发送垃圾邮件的念念。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="2f5a3-109">例如，内部部署电子邮件组织中通过 Microsoft 365 发送出站邮件或遭到入侵的 Microsoft 365 帐户的恶意软件或恶意垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="2f5a3-110">攻击者还尝试通过 Microsoft 365 转发中继邮件来避免检测。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="2f5a3-111">这些方案可能会导致受影响的 Microsoft 365 数据中心服务器的 IP 地址显示在第三方阻止列表中。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="2f5a3-112">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="2f5a3-113">高风险传递池</span><span class="sxs-lookup"><span data-stu-id="2f5a3-113">High-risk delivery pool</span></span>
<span data-ttu-id="2f5a3-114">为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件被确定为垃圾邮件或超出服务发送限制或出站垃圾邮件 [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)策略的所有出 [](configure-the-outbound-spam-policy.md)站邮件都通过高风险传递池 _发送_。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="2f5a3-115">高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量"邮件 (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2f5a3-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="2f5a3-116">使用高风险传递池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="2f5a3-117">出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="2f5a3-118">高风险传递池中的 IP 地址将保留在 IP 阻止列表上的可能性非常真实，但这是设计使的。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="2f5a3-119">不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="2f5a3-120">有关详细信息，请参阅"[控制出站垃圾邮件"。](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="2f5a3-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2f5a3-121">源电子邮件域没有 A 记录且在公共 DNS 中未定义 MX 记录的邮件始终通过高风险传递池路由，无论其垃圾邮件或发送限制处置如何。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="2f5a3-122">退回邮件</span><span class="sxs-lookup"><span data-stu-id="2f5a3-122">Bounce messages</span></span>

<span data-ttu-id="2f5a3-123">出站高风险传递池管理所有未送达报告（也称为 (、退回邮件、传递状态通知或 DSN）的) 。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="2f5a3-124">NDR 中激增的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="2f5a3-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="2f5a3-125">影响使用该服务的客户之一的欺骗活动。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="2f5a3-126">目录收集攻击。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-126">A directory harvest attack.</span></span>
- <span data-ttu-id="2f5a3-127">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-127">A spam attack.</span></span>
- <span data-ttu-id="2f5a3-128">未授权电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-128">A rogue email server.</span></span>

<span data-ttu-id="2f5a3-129">所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="2f5a3-130">许多时候，这些 NDR 对于其他电子邮件服务器和服务 (_[也称为退退垃圾邮件](backscatter-messages-and-eop.md)_) 。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="2f5a3-131">中继池</span><span class="sxs-lookup"><span data-stu-id="2f5a3-131">Relay pool</span></span>

<span data-ttu-id="2f5a3-132">转发或中继自 Microsoft 365 的邮件使用特殊的中继池发送，因为最终目标不应将 Microsoft 365 视为实际发件人。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="2f5a3-133">隔离此流量也很重要，因为存在从 Microsoft 365 自动转发或中继电子邮件的合法和无效方案。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="2f5a3-134">与高风险传递池类似，单独的 IP 地址池用于中继邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="2f5a3-135">此地址池不会发布，因为它可能会经常更改。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="2f5a3-136">Microsoft 365 需要验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="2f5a3-137">为此，需要在邮件 (SPF、DKIM 和 DMARC) 传递电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="2f5a3-138">在我们可以对发件人进行身份验证的情况下，我们使用发件人重写来帮助收件人知道转发的邮件来自受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="2f5a3-139">您可以阅读有关工作原理以及您可以执行哪些操作来帮助确保发送域通过发件人重写方案 ([SRS ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)) 。</span><span class="sxs-lookup"><span data-stu-id="2f5a3-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
