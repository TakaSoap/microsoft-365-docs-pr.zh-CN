---
title: 出站邮件的高风险传递池
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 了解如何使用高风险传递池来保护 Office 365 数据中心中的电子邮件服务器的声誉。
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895355"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a><span data-ttu-id="98a2c-103">Office 365 中出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="98a2c-103">High-risk delivery pool for outbound messages in Office 365</span></span>

<span data-ttu-id="98a2c-104">Office 365 数据中心中的电子邮件服务器可能暂时 guilty 发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-104">Email servers in the Office 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="98a2c-105">例如，内部部署电子邮件组织中的恶意软件或恶意垃圾邮件攻击，可通过 Office 365 发送出站邮件或损坏的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="98a2c-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Office 365, or compromised Office 365 accounts.</span></span> <span data-ttu-id="98a2c-106">这些方案可能会导致出现在第三方阻止列表中的受影响的 Office 365 数据中心服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="98a2c-106">These scenarios can result in the IP address of the affected Office 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="98a2c-107">使用这些阻止列表的目标电子邮件组织将拒绝来自这些邮件源的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="98a2c-108">为防止出现这种情况，通过_高风险传递池_发送来自确定为垃圾邮件的 Office 365 数据中心服务器的所有出站邮件，或超出[服务](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)的发送限制或[出站垃圾邮件策略](configure-the-outbound-spam-policy.md)的所有出站邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-108">To prevent this, all outbound messages from Office 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="98a2c-109">高风险传递池是仅用于发送 "低质量" 邮件（例如，垃圾邮件和[退信](backscatter-messages-and-eop.md)）的出站电子邮件的辅助 IP 地址池。</span><span class="sxs-lookup"><span data-stu-id="98a2c-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="98a2c-110">使用高风险传递池有助于阻止出站电子邮件的常规 IP 地址池发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="98a2c-111">出站电子邮件的常规 IP 地址池维护发送 "高质量" 邮件的信誉，从而降低了这些 IP 地址在 IP 阻止列表中出现的可能性。</span><span class="sxs-lookup"><span data-stu-id="98a2c-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="98a2c-112">高风险传递池中的 IP 地址可能会保留在 IP 阻止列表中，但这是设计的。</span><span class="sxs-lookup"><span data-stu-id="98a2c-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="98a2c-113">无法保证传递给预期的收件人，因为很多电子邮件组织不接受来自高风险传递池的邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="98a2c-114">有关详细信息，请参阅[在 Office 365 中控制出站垃圾邮件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="98a2c-114">For more information, see [Control outbound spam in Office 365](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="98a2c-115">源电子邮件域没有记录且在公用 DNS 中定义的任何 MX 记录都不会通过高风险传递池路由（无论其垃圾邮件或发送限制处置）的邮件。</span><span class="sxs-lookup"><span data-stu-id="98a2c-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="98a2c-116">退回邮件</span><span class="sxs-lookup"><span data-stu-id="98a2c-116">Bounce messages</span></span>

<span data-ttu-id="98a2c-117">出站高风险传递池管理所有未送达报告（也称为 Ndr、弹跳邮件、传递状态通知或 Dsn）的传递。</span><span class="sxs-lookup"><span data-stu-id="98a2c-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="98a2c-118">Ndr 中的电涌可能的原因包括：</span><span class="sxs-lookup"><span data-stu-id="98a2c-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="98a2c-119">对使用服务的客户之一产生影响的欺骗活动。</span><span class="sxs-lookup"><span data-stu-id="98a2c-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="98a2c-120">目录搜集攻击。</span><span class="sxs-lookup"><span data-stu-id="98a2c-120">A directory harvest attack.</span></span>

- <span data-ttu-id="98a2c-121">垃圾邮件攻击。</span><span class="sxs-lookup"><span data-stu-id="98a2c-121">A spam attack.</span></span>

- <span data-ttu-id="98a2c-122">一个欺诈性电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="98a2c-122">A rogue email server.</span></span>

<span data-ttu-id="98a2c-123">所有这些问题都会导致服务处理的 Ndr 数量突然增加。</span><span class="sxs-lookup"><span data-stu-id="98a2c-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="98a2c-124">许多情况下，这些 Ndr 似乎是垃圾邮件发送给其他电子邮件服务器和服务（也称为_[退信](backscatter-messages-and-eop.md)_）。</span><span class="sxs-lookup"><span data-stu-id="98a2c-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
