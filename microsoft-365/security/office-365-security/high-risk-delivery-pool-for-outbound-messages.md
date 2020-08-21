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
description: 了解如何在 Microsoft 365 数据中心中使用传递池来保护电子邮件服务器的信誉。
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827733"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="ecd8b-103">出站传递池</span><span class="sxs-lookup"><span data-stu-id="ecd8b-103">Outbound delivery pools</span></span>

<span data-ttu-id="ecd8b-104">Microsoft 365 数据中心的电子邮件服务器可能暂时会强烈影响发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="ecd8b-105">例如，本地电子邮件组织（通过 Microsoft 365 或 Microsoft 365 帐户入站邮件）中进行的恶意软件或恶意垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="ecd8b-106">攻击者还通过 Microsoft 365 转发功能中继邮件来避免检测。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-106">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="ecd8b-107">这些方案可能会导致受影响的 Microsoft 365 数据中心服务器的 IP 地址出现在第三方阻止列表中。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-107">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="ecd8b-108">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件来源的邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-108">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="ecd8b-109">高风险传送池</span><span class="sxs-lookup"><span data-stu-id="ecd8b-109">High-risk delivery pool</span></span>
<span data-ttu-id="ecd8b-110">为了防止发生这种限制，来自 Microsoft 365 数据中心服务器（已确定为垃圾邮件或超过服务或出站垃圾邮件策略的发送[限制）](configure-the-outbound-spam-policy.md)的所有出站邮件均将通过_高风险传送池发送_。 [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="ecd8b-110">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="ecd8b-111">高风险传送池是用于出站电子邮件的单独 IP 地址池，它仅用于发送"低质量"邮件 (例如垃圾邮件[和退信) 。](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ecd8b-111">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="ecd8b-112">使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-112">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="ecd8b-113">出站电子邮件的正常 IP 地址池维护"高质量"邮件发送信誉，这样可以降低这些 IP 地址出现在 IP 阻止列表中的可能性。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-113">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="ecd8b-114">高风险传送池中的 IP 地址将保留在 IP 阻止列表中的可能性，但这是按设计使不可行的。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-114">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="ecd8b-115">无法保证传递到预期收件人，因为许多电子邮件组织不会接受来自高风险传送池的邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-115">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="ecd8b-116">有关详细信息，请参阅"[控制出站垃圾邮件"。](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="ecd8b-116">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ecd8b-117">不管源电子邮件域没有 A 记录也没有公共 DNS 中定义的 MX 记录的邮件，无论其垃圾邮件或发送限制处置如何，都始终会通过高风险传送池路由。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-117">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="ecd8b-118">退回邮件</span><span class="sxs-lookup"><span data-stu-id="ecd8b-118">Bounce messages</span></span>

<span data-ttu-id="ecd8b-119">出站高风险传送池管理所有未送达报告 (也称为 NDR、退回邮件、传递状态通知或 DSN) 。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-119">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="ecd8b-120">NDR 中可能出现的问题的原因包括：</span><span class="sxs-lookup"><span data-stu-id="ecd8b-120">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="ecd8b-121">欺骗活动会影响使用该服务之一的客户。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-121">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="ecd8b-122">帐户收集攻击。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-122">A directory harvest attack.</span></span>
- <span data-ttu-id="ecd8b-123">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-123">A spam attack.</span></span>
- <span data-ttu-id="ecd8b-124">未创建电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-124">A rogue email server.</span></span>

<span data-ttu-id="ecd8b-125">所有这些问题都可能会导致服务处理 NDR 的数量显然增加。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-125">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="ecd8b-126">在很多情况下，这些 NDR 对其他电子邮件服务器和服务组 (（也称为_[退信式垃圾邮件) 。](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="ecd8b-126">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="ecd8b-127">中继池</span><span class="sxs-lookup"><span data-stu-id="ecd8b-127">Relay pool</span></span>

<span data-ttu-id="ecd8b-128">通过使用特殊中继池发送转发或中继来自 Microsoft 365 的邮件，因为最终目标不应将 Microsoft 365 视为实际的发件人。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-128">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="ecd8b-129">我们根据某些要求，我们也必须隔离此通信，因为 Microsoft 365 的自动转发或中继电子邮件存在合法和无效的方案。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-129">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="ecd8b-130">与高风险传送池类似，单独的 IP 地址池用于中继邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-130">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="ecd8b-131">该地址库未发布，因为它可能会经常更改。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-131">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="ecd8b-132">Microsoft 365 需要验证原始发件人是否为合法邮件，以便我们可以自信地传递转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-132">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="ecd8b-133">为此，电子邮件身份验证必须 (符合 SPF、DKIM 和 DMARC) 通过邮件发送给我们时需要通过。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-133">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="ecd8b-134">如果我们可以对发件人进行身份验证，我们使用发件人重写来帮助收件人知道转发的邮件来自受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-134">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="ecd8b-135">可以详细了解这一如何工作，以及可以如何帮助确保发送域通过 [S) RS 域的发件人 (写入 ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)。</span><span class="sxs-lookup"><span data-stu-id="ecd8b-135">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
