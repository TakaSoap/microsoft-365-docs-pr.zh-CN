---
title: 配置垃圾邮件保护
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的出站垃圾邮件控件，以及在需要发送大量邮件时应怎么办。
ms.openlocfilehash: 1097b768b955f2fa99c552ceda7564bef33a1aa7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202383"
---
# <a name="outbound-spam-protection-in-eop"></a><span data-ttu-id="2d187-103">EOP 中的出站垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="2d187-103">Outbound spam protection in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2d187-104">在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，我们会认真管理出站垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, we take managing outbound spam seriously.</span></span> <span data-ttu-id="2d187-105">如果一个客户有意或无意地从其组织中发送垃圾邮件，则可能会降低整个服务的声誉，并可能影响其他客户的电子邮件传递。</span><span class="sxs-lookup"><span data-stu-id="2d187-105">One customer who intentionally or unintentionally sends spam from their organization can degrade the reputation of the whole service, and can affect email delivery for other customers.</span></span>

<span data-ttu-id="2d187-106">本主题介绍旨在帮助阻止出站垃圾邮件的控件和通知，以及在需要发送大量邮件的情况下可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2d187-106">This topic describes the controls and notifications that are designed to help prevent outbound spam, and what you can do if you need to send mass mailings.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="2d187-107">管理员可控制出站垃圾邮件的操作</span><span class="sxs-lookup"><span data-stu-id="2d187-107">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="2d187-108">**使用内置通知**：当用户超过了 [服务](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 或 [出站垃圾邮件策略](configure-the-outbound-spam-policy.md) 的发送限制且被限制为发送电子邮件时，名为 " **用户限制发送电子邮件** " 的默认通知策略将电子邮件通知发送给 **TenantAdmins** (**全局管理员**) 组的成员。</span><span class="sxs-lookup"><span data-stu-id="2d187-108">**Use built-in notifications**: When a user exceeds sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) and is restricted from sending email, the default alert policy named **User restricted from sending email** sends email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="2d187-109">若要配置其他人接收这些通知的人，请参阅 [验证受限制用户的通知设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。</span><span class="sxs-lookup"><span data-stu-id="2d187-109">To configure who else receives these notifications, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="2d187-110">此外，检测到的默认通知策略已 **超过电子邮件发送限制** ，并且 **检测到可疑电子** 邮件发送模式将电子邮件通知发送给 **TenantAdmins** (**全局管理员**) 组的成员。</span><span class="sxs-lookup"><span data-stu-id="2d187-110">Also, the default alert policies named **Email sending limit exceeded** and **Suspicious email sending patterns detected** send email notifications to members of the **TenantAdmins** (**Global admins**) group.</span></span> <span data-ttu-id="2d187-111">若要详细了解警报策略，请参阅[安全与合规中心内的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2d187-111">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

- <span data-ttu-id="2d187-112">**查看来自第三方电子邮件提供商的垃圾邮件投诉**：许多电子邮件服务（如 Outlook.com、YAHOO 和 AOL）在其服务中的任何用户将来自 Microsoft 365 的电子邮件标记为垃圾邮件时，将该邮件打包并发回我们进行审阅。</span><span class="sxs-lookup"><span data-stu-id="2d187-112">**Review spam complaints from third party email providers**: Many email services like Outlook.com, Yahoo and AOL provide a feedback loop where if any user in their service marks an email from Microsoft 365 as spam, the message is packaged up and sent back to us for review.</span></span> <span data-ttu-id="2d187-113">若要了解有关 Outlook.com 的发件人支持的详细信息，请转到 <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="2d187-113">To learn more about sender support for Outlook.com, go to <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>.</span></span>

## <a name="how-eop-controls-outbound-spam"></a><span data-ttu-id="2d187-114">EOP 如何控制出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2d187-114">How EOP controls outbound spam</span></span>

- <span data-ttu-id="2d187-115">**出站电子邮件流量的划分**：扫描通过该服务发送的每个出站邮件是否有垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-115">**Segregation of outbound email traffic**: Every outbound message that's sent through the service is scanned for spam.</span></span> <span data-ttu-id="2d187-116">如果将邮件确定为垃圾邮件，则会从名为 " _高风险传递池_" 的次要、不太知名的 IP 地址池进行传递。</span><span class="sxs-lookup"><span data-stu-id="2d187-116">If the message is determined to be spam, it's delivered from a secondary, less reputable IP address pool named the _high-risk delivery pool_.</span></span> <span data-ttu-id="2d187-117">有关详细信息，请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2d187-117">For more information, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span>

- <span data-ttu-id="2d187-118">**监视源 IP 地址信誉**： Microsoft 365 查询各种第三方 ip 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="2d187-118">**Monitoring our source IP address reputation**: Microsoft 365 queries various third party IP block lists.</span></span> <span data-ttu-id="2d187-119">如果在这些列表中显示了用于出站电子邮件的任何 IP 地址，则会生成警报。</span><span class="sxs-lookup"><span data-stu-id="2d187-119">An alert is generated if any of the IP addresses that we use for outbound email appear on these lists.</span></span> <span data-ttu-id="2d187-120">这使我们能够在垃圾邮件导致名誉下降时快速做出反应。</span><span class="sxs-lookup"><span data-stu-id="2d187-120">This allows us to react quickly when spam has caused our reputation to degrade.</span></span> <span data-ttu-id="2d187-121">生成警报时，我们将介绍如何将 IP 地址从阻止列表中删除 (delisted) 的内部文档。</span><span class="sxs-lookup"><span data-stu-id="2d187-121">When an alert is generated, we have internal documentation that outlines how to get our IP addresses remove (delisted) from block lists.</span></span>

- <span data-ttu-id="2d187-122">**禁用发送过多垃圾邮件的帐户** <sup>\*</sup> ：即使我们将出站垃圾邮件与高风险传递池进行了隔离，我们也无法允许帐户 (经常发送垃圾邮件的帐户) 。</span><span class="sxs-lookup"><span data-stu-id="2d187-122">**Disable accounts that send too much spam**<sup>\*</sup>: Even though we segregate outbound spam into the high-risk delivery pool, we can't allow an account (often, a compromised account) to send spam indefinitely.</span></span> <span data-ttu-id="2d187-123">我们监视发送垃圾邮件的帐户，当它们超过 undisclosed 限制时，将阻止该帐户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-123">We monitor accounts that are sending spam, and when they exceed an undisclosed limit, the account is blocked from sending email.</span></span> <span data-ttu-id="2d187-124">单个用户和整个租户具有不同的阈值。</span><span class="sxs-lookup"><span data-stu-id="2d187-124">There are different thresholds for individual users and the entire tenant.</span></span>

- <span data-ttu-id="2d187-125">**禁用发送过多电子邮件的帐户太快** <sup>\*</sup> ：除了查找标记为垃圾邮件的邮件的限制之外，还会阻止在邮箱访问总出站邮件限制时阻止帐户，而不考虑出站邮件上的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="2d187-125">**Disabling accounts that send too much email too quickly**<sup>\*</sup>: In addition to the limits that look for messages marked as spam, there are also limits that block accounts when they reach an overall outbound message limit, regardless the spam filtering verdict on the outbound messages.</span></span> <span data-ttu-id="2d187-126">已损坏的帐户可能会发送垃圾邮件筛选器错过的零天 (之前无法识别) 垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-126">A compromised account could send zero-day (previously unrecognized) spam that is missed by the spam filter.</span></span> <span data-ttu-id="2d187-127">由于很难确定合法的大宗邮件市场活动与垃圾邮件市场活动，因此这些限制有助于最大限度地减少任何潜在的损坏。</span><span class="sxs-lookup"><span data-stu-id="2d187-127">Because it can be difficult to identify a legitimate mass mailing campaign vs. a spam campaign, these limits help to minimize any potential damage.</span></span>

<span data-ttu-id="2d187-128"><sup>\*</sup> 我们不会公布确切的限制，因此垃圾邮件制造者无法将系统游戏，因此我们可以根据需要增加或减少限制。</span><span class="sxs-lookup"><span data-stu-id="2d187-128"><sup>\*</sup> We don't advertise the exact limits so spammers can't game the system, and so we can increase or decrease the limits as necessary.</span></span> <span data-ttu-id="2d187-129">这些限制值足够高，以防止一般的业务用户超过它们，并且足够低，以帮助包含垃圾邮件发送者导致的损坏。</span><span class="sxs-lookup"><span data-stu-id="2d187-129">The limits are high enough to prevent an average business user from ever exceeding them, and low enough to help contain the damage caused by a spammer.</span></span>

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a><span data-ttu-id="2d187-130">有关想要通过 EOP 发送大宗邮件的客户的建议</span><span class="sxs-lookup"><span data-stu-id="2d187-130">Recommendations for customers who want to send mass mailings through EOP</span></span>

<span data-ttu-id="2d187-131">在想要发送大量电子邮件的客户之间，很难对其进行权衡，而是通过较差的收件人获取实践来保护服务免受受损帐户和批量电子邮件发件人的侵袭。</span><span class="sxs-lookup"><span data-stu-id="2d187-131">It's difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk email senders with poor recipient acquisition practices.</span></span> <span data-ttu-id="2d187-132">第三方 IP 阻止列表上的 Microsoft 365 电子邮件源登录的成本大于阻止发送过多电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="2d187-132">The cost of a Microsoft 365 email source landing on a third party IP block list is greater than blocking a user who's sending too much email.</span></span>

<span data-ttu-id="2d187-133">如 [Exchange Online 服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)中所述，使用 EOP 发送批量电子邮件不是服务的受支持的使用，并且仅在 "最大努力" 的基础上允许。</span><span class="sxs-lookup"><span data-stu-id="2d187-133">As described in the [Exchange Online Service Description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), using EOP to send bulk email is not a supported use of the service, and is only permitted on a "best-effort" basis.</span></span> <span data-ttu-id="2d187-134">对于想要发送批量电子邮件的客户，我们建议采用以下解决方案：</span><span class="sxs-lookup"><span data-stu-id="2d187-134">For customers who do want to send bulk email, we recommend the following solutions:</span></span>

- <span data-ttu-id="2d187-135">**通过内部部署电子邮件服务器发送批量电子邮件**：这意味着客户将需要维护其自己的电子邮件基础结构以实现大宗邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-135">**Send bulk email through on-premises email servers**: This means that customers will need to maintain their own email infrastructure for mass mailings.</span></span>

- <span data-ttu-id="2d187-136">**使用第三方批量电子邮件提供程序**：您可以使用多个第三方批量电子邮件解决方案提供程序来发送大宗邮件。</span><span class="sxs-lookup"><span data-stu-id="2d187-136">**Use a third party bulk email provider**: There are several third party bulk email solution providers that you can use to send mass mailings.</span></span> <span data-ttu-id="2d187-137">这些公司在与客户合作以确保良好的电子邮件发送实践方面有 vested 的兴趣。</span><span class="sxs-lookup"><span data-stu-id="2d187-137">These companies have a vested interest in working with customers to ensure good email sending practices.</span></span>

<span data-ttu-id="2d187-138">邮件、移动、恶意软件防滥用工作组 (MAAWG) 发布其成员名单的位置 <https://www.maawg.org/about/roster> 。</span><span class="sxs-lookup"><span data-stu-id="2d187-138">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster at <https://www.maawg.org/about/roster>.</span></span> <span data-ttu-id="2d187-139">在列表中有多个批量电子邮件提供商，并且已知是负责 internet 公民。</span><span class="sxs-lookup"><span data-stu-id="2d187-139">Several bulk email providers are on the list, and are known to be responsible internet citizens.</span></span>
