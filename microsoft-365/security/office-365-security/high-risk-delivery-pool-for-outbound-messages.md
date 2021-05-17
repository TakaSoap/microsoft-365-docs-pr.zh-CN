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
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599907"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="aed9e-103">出站传递池</span><span class="sxs-lookup"><span data-stu-id="aed9e-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="aed9e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="aed9e-104">**Applies to**</span></span>
- [<span data-ttu-id="aed9e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="aed9e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="aed9e-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="aed9e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="aed9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aed9e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="aed9e-108">数据中心内的电子邮件Microsoft 365可能暂时没有发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="aed9e-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="aed9e-109">例如，内部部署电子邮件组织中通过邮件发送出站邮件或帐户遭到入侵Microsoft 365恶意软件或Microsoft 365攻击。</span><span class="sxs-lookup"><span data-stu-id="aed9e-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="aed9e-110">攻击者还尝试通过邮件转发来中继邮件，Microsoft 365检测。</span><span class="sxs-lookup"><span data-stu-id="aed9e-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="aed9e-111">这些方案可能导致受影响的数据中心服务器的 IP 地址Microsoft 365第三方阻止列表上出现。</span><span class="sxs-lookup"><span data-stu-id="aed9e-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="aed9e-112">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aed9e-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="aed9e-113">高风险传送池</span><span class="sxs-lookup"><span data-stu-id="aed9e-113">High-risk delivery pool</span></span>
<span data-ttu-id="aed9e-114">为了防止这种情况，来自 Microsoft 365 数据中心服务器的所有出站邮件（被确定为垃圾邮件或超过服务或出站垃圾邮件策略的发送限制）[](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)都通过高风险 [](configure-the-outbound-spam-policy.md)传递池 _发送_。</span><span class="sxs-lookup"><span data-stu-id="aed9e-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="aed9e-115">高风险传递池是出站电子邮件的单独 IP 地址池，仅用于发送"低质量" (例如垃圾邮件和退信) 。 [](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="aed9e-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="aed9e-116">使用高风险传送池有助于防止出站电子邮件的正常 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="aed9e-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="aed9e-117">出站电子邮件的正常 IP 地址池维护发送"高质量"邮件的信誉，这会降低这些 IP 地址出现在 IP 阻止列表上的可能性。</span><span class="sxs-lookup"><span data-stu-id="aed9e-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="aed9e-118">将高风险传送池中的 IP 地址置于 IP 阻止列表的可能性仍然很高，但这是设计使的。</span><span class="sxs-lookup"><span data-stu-id="aed9e-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="aed9e-119">不保证向目标收件人传递邮件，因为许多电子邮件组织不接受来自高风险传递池的邮件。</span><span class="sxs-lookup"><span data-stu-id="aed9e-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="aed9e-120">有关详细信息，请参阅控制 [出站垃圾邮件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="aed9e-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aed9e-121">源电子邮件域没有 A 记录且公共 DNS 中未定义 MX 记录的邮件始终通过高风险传送池路由，无论其垃圾邮件或发送限制处置如何。</span><span class="sxs-lookup"><span data-stu-id="aed9e-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="aed9e-122">退回邮件</span><span class="sxs-lookup"><span data-stu-id="aed9e-122">Bounce messages</span></span>

<span data-ttu-id="aed9e-123">出站高风险传递池管理所有未送达报告（也称为 (、退回邮件、传递状态通知或 DSN) ）。</span><span class="sxs-lookup"><span data-stu-id="aed9e-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="aed9e-124">NDR 中出现激增的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="aed9e-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="aed9e-125">影响使用该服务的其中一个客户的欺骗活动。</span><span class="sxs-lookup"><span data-stu-id="aed9e-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="aed9e-126">目录收集攻击。</span><span class="sxs-lookup"><span data-stu-id="aed9e-126">A directory harvest attack.</span></span>
- <span data-ttu-id="aed9e-127">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="aed9e-127">A spam attack.</span></span>
- <span data-ttu-id="aed9e-128">未授权电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="aed9e-128">A rogue email server.</span></span>

<span data-ttu-id="aed9e-129">所有这些问题都可能导致服务正在处理的 NDR 数量突然增加。</span><span class="sxs-lookup"><span data-stu-id="aed9e-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="aed9e-130">在许多情况下，这些 NDR 似乎为其他电子邮件服务器和服务的垃圾邮件 (也称为退 _[) 。](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="aed9e-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
