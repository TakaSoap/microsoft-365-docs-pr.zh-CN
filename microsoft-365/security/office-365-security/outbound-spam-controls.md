---
title: 出站垃圾邮件保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP Exchange Online Protection (中的出站) ，以及如果您需要发送大量邮件，该怎么办。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538731"
---
# <a name="outbound-spam-protection-in-eop"></a><span data-ttu-id="c60c2-103">EOP 中的出站垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="c60c2-103">Outbound spam protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c60c2-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="c60c2-104">**Applies to**</span></span>
- [<span data-ttu-id="c60c2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c60c2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c60c2-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="c60c2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c60c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c60c2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c60c2-108">在Microsoft 365没有邮箱的 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，我们非常重视管理出站垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, we take managing outbound spam seriously.</span></span> <span data-ttu-id="c60c2-109">即使一个客户有意或无意地从组织发送垃圾邮件，该操作也会降低整个服务的信誉，并可能影响其他客户的电子邮件传递。</span><span class="sxs-lookup"><span data-stu-id="c60c2-109">Even if one customer intentionally or unintentionally sends spam from their organization, that action can degrade the reputation of the whole service and can affect email delivery for other customers.</span></span>

<span data-ttu-id="c60c2-110">本文介绍旨在帮助防止出站垃圾邮件的控件和通知，以及如果您需要发送大量邮件，您可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="c60c2-110">This article describes the controls and notifications that are designed to help prevent outbound spam, and what you can do if you need to send mass mailings.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="c60c2-111">管理员可以执行哪些操作来控制出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c60c2-111">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="c60c2-112">使用内置通知：当用户超出服务或出站垃圾邮件策略的发送 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)限制并限制 [](configure-the-outbound-spam-policy.md)发送电子邮件时，名为 **"** 限制发送电子邮件的用户"的默认警报策略将向 **TenantAdmins** (**全局** 管理员) 组的成员发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c60c2-112">**Use built-in notifications**: When a user exceeds sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) and is restricted from sending email, the default alert policy named **User restricted from sending email** sends email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="c60c2-113">若要配置其他接收这些通知的用户，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="c60c2-113">To configure who else receives these notifications, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="c60c2-114">此外，名为"电子邮件发送限制"和"检测到可疑电子邮件发送模式"的默认警报策略向 **TenantAdmins** (**全局** 管理员组) 发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c60c2-114">Also, the default alert policies named **Email sending limit exceeded** and **Suspicious email sending patterns detected** send email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="c60c2-115">有关警报策略详细信息，请参阅警报策略[Microsoft 365。](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c60c2-115">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

- <span data-ttu-id="c60c2-116">审阅来自第三方电子邮件提供商的垃圾邮件投诉：许多电子邮件服务（如 Outlook.com、Yahoo 和 AOL）提供反馈循环，如果其服务中的任意用户将 Microsoft 365 中的电子邮件标记为垃圾邮件，邮件将打包并发回我们进行审阅。</span><span class="sxs-lookup"><span data-stu-id="c60c2-116">**Review spam complaints from third-party email providers**: Many email services like Outlook.com, Yahoo, and AOL provide a feedback loop where if any user in their service marks an email from Microsoft 365 as spam, the message is packaged up and sent back to us for review.</span></span> <span data-ttu-id="c60c2-117">若要了解有关发件人对 Outlook.com 的支持，请转到 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="c60c2-117">To learn more about sender support for Outlook.com, go to <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>.</span></span>

## <a name="how-eop-controls-outbound-spam"></a><span data-ttu-id="c60c2-118">EOP 如何控制出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c60c2-118">How EOP controls outbound spam</span></span>

- <span data-ttu-id="c60c2-119">**出站电子邮件流量的分离**：将扫描通过服务发送的每封出站邮件是否包含垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-119">**Segregation of outbound email traffic**: Every outbound message that's sent through the service is scanned for spam.</span></span> <span data-ttu-id="c60c2-120">如果邮件被确定为垃圾邮件，则从名为高风险传递池的低信誉辅助 IP 地址 _池进行传递_。</span><span class="sxs-lookup"><span data-stu-id="c60c2-120">If the message is determined to be spam, it's delivered from a secondary, less reputable IP address pool named the _high-risk delivery pool_.</span></span> <span data-ttu-id="c60c2-121">有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c60c2-121">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="c60c2-122">**监视源 IP 地址信誉**：Microsoft 365查询各种第三方 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="c60c2-122">**Monitoring our source IP address reputation**: Microsoft 365 queries various third-party IP block lists.</span></span> <span data-ttu-id="c60c2-123">如果我们用于出站电子邮件的任何 IP 地址显示在这些列表中，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="c60c2-123">An alert is generated if any of the IP addresses that we use for outbound email appear on these lists.</span></span> <span data-ttu-id="c60c2-124">此监视允许我们在垃圾邮件导致信誉下降时快速做出响应。</span><span class="sxs-lookup"><span data-stu-id="c60c2-124">This monitoring allows us to react quickly when spam has caused our reputation to degrade.</span></span> <span data-ttu-id="c60c2-125">生成警报时，我们具有内部文档，概述了如何从阻止列表中 (除名) IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c60c2-125">When an alert is generated, we have internal documentation that outlines how to get our IP addresses remove (delisted) from block lists.</span></span>

- <span data-ttu-id="c60c2-126">禁用发送过多垃圾邮件的帐户：尽管我们将出站垃圾邮件隔离到高风险传送池中，但不允许帐户 (，即遭到入侵的帐户) 无限期发送垃圾邮件。 <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c60c2-126">**Disable accounts that send too much spam**<sup>\*</sup>: Even though we segregate outbound spam into the high-risk delivery pool, we can't allow an account (often, a compromised account) to send spam indefinitely.</span></span> <span data-ttu-id="c60c2-127">我们监视发送垃圾邮件的帐户，当这些帐户超出限制时，将阻止该帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-127">We monitor accounts that are sending spam, and when they exceed an undisclosed limit, the account is blocked from sending email.</span></span> <span data-ttu-id="c60c2-128">单个用户和整个租户有不同的阈值。</span><span class="sxs-lookup"><span data-stu-id="c60c2-128">There are different thresholds for individual users and the entire tenant.</span></span>

- <span data-ttu-id="c60c2-129">禁用发送过快的电子邮件的帐户：除了查找标记为垃圾邮件的邮件的限制之外，还有一些限制在帐户达到总体出站邮件限制时阻止帐户，而不管出站邮件的垃圾邮件筛选裁定如何。 <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c60c2-129">**Disabling accounts that send too much email too quickly**<sup>\*</sup>: In addition to the limits that look for messages marked as spam, there are also limits that block accounts when they reach an overall outbound message limit, regardless the spam filtering verdict on the outbound messages.</span></span> <span data-ttu-id="c60c2-130">遭到入侵的帐户可能会发送零 (之前无法识别) 垃圾邮件筛选器错过的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-130">A compromised account could send zero-day (previously unrecognized) spam that is missed by the spam filter.</span></span> <span data-ttu-id="c60c2-131">由于很难确定合法的大量邮件活动与垃圾邮件活动，因此这些限制有助于最大限度地减少任何潜在损害。</span><span class="sxs-lookup"><span data-stu-id="c60c2-131">Because it can be difficult to identify a legitimate mass mailing campaign vs. a spam campaign, these limits help to minimize any potential damage.</span></span>

<span data-ttu-id="c60c2-132"><sup>\*</sup> 我们不公布确切的限制，因此垃圾邮件制造者无法对系统进行游戏，因此我们可以在必要时增加或减少限制。</span><span class="sxs-lookup"><span data-stu-id="c60c2-132"><sup>\*</sup> We don't advertise the exact limits so spammers can't game the system, and so we can increase or decrease the limits as necessary.</span></span> <span data-ttu-id="c60c2-133">这些限制足够高，以防止一般商业用户超过它们，而低到足以帮助控制垃圾邮件制造者造成的损坏。</span><span class="sxs-lookup"><span data-stu-id="c60c2-133">The limits are high enough to prevent an average business user from ever exceeding them, and low enough to help contain the damage caused by a spammer.</span></span>

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a><span data-ttu-id="c60c2-134">推荐 EOP 发送大量邮件的客户选择</span><span class="sxs-lookup"><span data-stu-id="c60c2-134">Recommendations for customers who want to send mass mailings through EOP</span></span>

<span data-ttu-id="c60c2-135">在想要发送大量电子邮件的客户与保护服务免受损坏的帐户和具有较差收件人获取做法的批量电子邮件发件人之间取得平衡非常困难。</span><span class="sxs-lookup"><span data-stu-id="c60c2-135">It's difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk email senders with poor recipient acquisition practices.</span></span> <span data-ttu-id="c60c2-136">电子邮件源Microsoft 365第三方 IP 阻止列表的成本大于阻止发送过多电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="c60c2-136">The cost of a Microsoft 365 email source landing on a third-party IP block list is greater than blocking a user who's sending too much email.</span></span>

<span data-ttu-id="c60c2-137">如 Exchange Online [Service Description](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)中所述，使用 EOP 发送批量电子邮件不受服务支持，仅允许"尽力"使用。</span><span class="sxs-lookup"><span data-stu-id="c60c2-137">As described in the [Exchange Online Service Description](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), using EOP to send bulk email is not a supported use of the service, and is only permitted on a "best-effort" basis.</span></span> <span data-ttu-id="c60c2-138">对于想要发送批量电子邮件的客户，我们建议采用以下解决方案：</span><span class="sxs-lookup"><span data-stu-id="c60c2-138">For customers who do want to send bulk email, we recommend the following solutions:</span></span>

- <span data-ttu-id="c60c2-139">**通过本地电子邮件服务器发送** 批量电子邮件：客户维护自己的电子邮件基础结构，用于大量邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-139">**Send bulk email through on-premises email servers**: Customers maintain their own email infrastructure for mass mailings.</span></span>

- <span data-ttu-id="c60c2-140">**使用第三方批量电子邮件** 提供商：可以使用多个第三方批量电子邮件解决方案提供商发送大量邮件。</span><span class="sxs-lookup"><span data-stu-id="c60c2-140">**Use a third-party bulk email provider**: There are several third-party bulk email solution providers that you can use to send mass mailings.</span></span> <span data-ttu-id="c60c2-141">这些公司有兴趣与客户合作，以确保良好的电子邮件发送实践。</span><span class="sxs-lookup"><span data-stu-id="c60c2-141">These companies have a vested interest in working with customers to ensure good email sending practices.</span></span>

<span data-ttu-id="c60c2-142">MAAWG 消息、移动、恶意软件反滥用工作组 (在) 发布其成员身份名单 <https://www.maawg.org/about/roster> 。</span><span class="sxs-lookup"><span data-stu-id="c60c2-142">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster at <https://www.maawg.org/about/roster>.</span></span> <span data-ttu-id="c60c2-143">列表中列出了多个批量电子邮件提供商，这些提供商已知是负责的 Internet 公民。</span><span class="sxs-lookup"><span data-stu-id="c60c2-143">Several bulk email providers are on the list, and are known to be responsible internet citizens.</span></span>
