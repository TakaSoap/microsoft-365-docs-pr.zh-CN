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
description: 了解如何使用传递池来保护数据中心中电子邮件Microsoft 365信誉。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5881b20eaed8387988d01b69a4acd022c5924a2
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409136"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="37636-103">出站传递池</span><span class="sxs-lookup"><span data-stu-id="37636-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37636-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="37636-104">**Applies to**</span></span>
- [<span data-ttu-id="37636-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37636-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="37636-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="37636-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="37636-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37636-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="37636-108">数据中心内的电子邮件Microsoft 365可能暂时没有发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="37636-109">例如，内部部署电子邮件组织中通过邮件发送出站邮件或帐户遭到入侵Microsoft 365恶意软件或Microsoft 365攻击。</span><span class="sxs-lookup"><span data-stu-id="37636-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="37636-110">攻击者还尝试通过邮件转发来中继邮件，Microsoft 365检测。</span><span class="sxs-lookup"><span data-stu-id="37636-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="37636-111">这些方案可能导致受影响的数据中心服务器的 IP 地址Microsoft 365第三方阻止列表上出现。</span><span class="sxs-lookup"><span data-stu-id="37636-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="37636-112">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="37636-113">高风险传送池</span><span class="sxs-lookup"><span data-stu-id="37636-113">High-risk delivery pool</span></span>
<span data-ttu-id="37636-114">为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件（被确定为垃圾邮件或超过服务或出站垃圾邮件策略的发送限制）[](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)都通过高风险 [](configure-the-outbound-spam-policy.md)传递池 _发送_。</span><span class="sxs-lookup"><span data-stu-id="37636-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="37636-115">高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量" (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="37636-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="37636-116">使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="37636-117">出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。</span><span class="sxs-lookup"><span data-stu-id="37636-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="37636-118">将高风险传送池中的 IP 地址置于 IP 阻止列表的可能性仍然很高，但这是设计使的。</span><span class="sxs-lookup"><span data-stu-id="37636-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="37636-119">不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="37636-120">有关详细信息，请参阅控制 [出站垃圾邮件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="37636-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="37636-121">源电子邮件域没有 A 记录且公共 DNS 中未定义 MX 记录的邮件始终通过高风险传送池路由，无论其垃圾邮件或发送限制处置如何。</span><span class="sxs-lookup"><span data-stu-id="37636-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="37636-122">退回邮件</span><span class="sxs-lookup"><span data-stu-id="37636-122">Bounce messages</span></span>

<span data-ttu-id="37636-123">出站高风险传递池管理所有未送达报告（也称为 (、退回邮件、传递状态通知或 DSN) ）。</span><span class="sxs-lookup"><span data-stu-id="37636-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="37636-124">NDR 中出现激增的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="37636-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="37636-125">影响使用该服务的其中一个客户的欺骗活动。</span><span class="sxs-lookup"><span data-stu-id="37636-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="37636-126">目录收集攻击。</span><span class="sxs-lookup"><span data-stu-id="37636-126">A directory harvest attack.</span></span>
- <span data-ttu-id="37636-127">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="37636-127">A spam attack.</span></span>
- <span data-ttu-id="37636-128">未授权电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="37636-128">A rogue email server.</span></span>

<span data-ttu-id="37636-129">所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。</span><span class="sxs-lookup"><span data-stu-id="37636-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="37636-130">在许多情况下，这些 NDR 似乎为其他电子邮件服务器和服务的垃圾邮件 (也称为退 _[) 。](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="37636-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="37636-131">中继池</span><span class="sxs-lookup"><span data-stu-id="37636-131">Relay pool</span></span>

<span data-ttu-id="37636-132">在某些情况下，通过 Microsoft 365 转发或中继的邮件会使用特殊的中继池发送，因为目标不应Microsoft 365实际发件人。</span><span class="sxs-lookup"><span data-stu-id="37636-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="37636-133">隔离此电子邮件通信很重要，因为存在用于自动转发或中继电子邮件从 Microsoft 365 的合法和无效Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="37636-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="37636-134">与高风险传送池类似，单独的 IP 地址池用于中继邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="37636-135">此地址池不会发布，因为它可能会经常更改，并且不是已发布的 SPF 记录的一Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="37636-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="37636-136">Microsoft 365需要验证原始发件人是否合法，以便我们可以放心地传递转发的邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="37636-137">转发/中继邮件应满足以下条件之一，以避免使用中继池：</span><span class="sxs-lookup"><span data-stu-id="37636-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="37636-138">出站发件人位于接受 [域中](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="37636-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="37636-139">当邮件发送到邮件时，SPF Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="37636-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="37636-140">当邮件发送到发件人域时，发件人域上的 DKIM 通过Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="37636-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="37636-141">通过查看出站服务器 IP (中继池将位于 40.95.0.0/16 范围) ，或者通过查看出站服务器名称 (将在名称) 中显示"rly"，可以判断邮件是通过中继池发送的。</span><span class="sxs-lookup"><span data-stu-id="37636-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="37636-142">在我们可以验证发件人的情况下，我们使用发件人重写方案 (SRS) 来帮助收件人电子邮件系统知道转发的邮件来自受信任的来源。</span><span class="sxs-lookup"><span data-stu-id="37636-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="37636-143">您可以阅读有关工作原理和操作方法的更多信息，以帮助确保发送域在发件人重写方案 ([SRS](/office365/troubleshoot/antispam/sender-rewriting-scheme)) 中通过Office 365。</span><span class="sxs-lookup"><span data-stu-id="37636-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="37636-144">若要使 DKIM 正常工作，请确保为发送域启用 DKIM。</span><span class="sxs-lookup"><span data-stu-id="37636-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="37636-145">例如，fabrikam.com 是 contoso.com 的一部分，在组织的接受域中定义。</span><span class="sxs-lookup"><span data-stu-id="37636-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="37636-146">如果邮件发件人 sender@fabrikam.com，需要为邮件发件人启用 DKIM fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="37636-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="37636-147">可以在使用 DKIM 验证从自定义域发送的出站电子邮件中阅读如何[启用。](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="37636-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="37636-148">若要添加自定义域，请按照将域添加到域[Microsoft 365。](../../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="37636-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="37636-149">如果域的 MX 记录指向第三方服务或本地电子邮件服务器，则应该使用增强的 [连接器筛选](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="37636-149">If the MX record for your domain points to a third party service or an on-premises email server, you should use [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="37636-150">增强的筛选可确保 SPF 验证对入站邮件正确无误，并避免通过中继池发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="37636-150">Enhanced Filtering ensures SPF validation is correct for inbound mail and will avoid sending email through the relay pool.</span></span>

