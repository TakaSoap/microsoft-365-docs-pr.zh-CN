---
title: 防欺骗保护常见问题
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection (EOP) 中的反欺骗保护的常见问题和) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d0805b5ca9e951234679ed8b3d03b6bdfced2be
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175885"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="4c676-103">防欺骗保护常见问题</span><span class="sxs-lookup"><span data-stu-id="4c676-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4c676-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="4c676-104">**Applies to**</span></span>
- [<span data-ttu-id="4c676-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4c676-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4c676-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="4c676-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4c676-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c676-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4c676-108">本文提供有关 Exchange Online 中具有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织的反欺骗保护的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="4c676-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="4c676-109">有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="4c676-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="4c676-110">有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="4c676-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="4c676-111">为什么 Microsoft 选择垃圾邮件未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="4c676-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="4c676-112">Microsoft 认为，继续允许未经身份验证的入站电子邮件的风险高于丢失合法入站电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="4c676-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="4c676-113">垃圾邮件未经身份验证的入站电子邮件是否会导致合法电子邮件被标记为垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="4c676-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="4c676-114">当 Microsoft 在 2018 年启用此功能时， (邮件被标记为错误，) 。</span><span class="sxs-lookup"><span data-stu-id="4c676-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="4c676-115">但是，随着时间的推移，发件人会根据要求进行调整。</span><span class="sxs-lookup"><span data-stu-id="4c676-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="4c676-116">对于大多数电子邮件路径来说，被错误识别为欺骗邮件的邮件数量可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="4c676-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="4c676-117">Microsoft 本身在将新的电子邮件身份验证要求部署到客户之前，已经过几周才采用了该要求。</span><span class="sxs-lookup"><span data-stu-id="4c676-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="4c676-118">虽然最初出现了中断，但此现象逐渐减少了。</span><span class="sxs-lookup"><span data-stu-id="4c676-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="4c676-119">没有适用于 Office 365 的 Defender 的 Microsoft 365 客户是否可以使用欺骗智能？</span><span class="sxs-lookup"><span data-stu-id="4c676-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="4c676-120">是。</span><span class="sxs-lookup"><span data-stu-id="4c676-120">Yes.</span></span> <span data-ttu-id="4c676-121">自 2018 年 10 日起，欺骗智能适用于在 Exchange Online 中拥有邮箱的所有组织和没有 Exchange Online 邮箱的独立 EOP 组织。</span><span class="sxs-lookup"><span data-stu-id="4c676-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="4c676-122">如何向 Microsoft 报告垃圾邮件或非垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="4c676-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="4c676-123">参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="4c676-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="4c676-124">我是管理员，不知道我的电子邮件域中的所有邮件源！</span><span class="sxs-lookup"><span data-stu-id="4c676-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="4c676-125">See [You't know all sources for your email.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="4c676-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="4c676-126">如果我为组织禁用反欺骗保护，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="4c676-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="4c676-127">建议不要禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="4c676-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="4c676-128">禁用保护将允许在组织中传递更多网络钓鱼和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="4c676-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="4c676-129">并非所有网络钓鱼都是欺骗，并且并非所有欺骗邮件都会丢失。</span><span class="sxs-lookup"><span data-stu-id="4c676-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="4c676-130">但是，您的风险将更高。</span><span class="sxs-lookup"><span data-stu-id="4c676-130">However, your risk will be higher.</span></span>

<span data-ttu-id="4c676-131">现在 [，连接器的](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 增强筛选功能可用，我们不再建议在 EOP 之前通过其他服务路由电子邮件时关闭反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="4c676-131">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="4c676-132">反欺骗保护是否意味着将保护我免受所有钓鱼？</span><span class="sxs-lookup"><span data-stu-id="4c676-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="4c676-133">遗憾的是，否。</span><span class="sxs-lookup"><span data-stu-id="4c676-133">Unfortunately, no.</span></span> <span data-ttu-id="4c676-134">攻击者将适应使用其他技术 (例如，在免费电子邮件服务中遭到入侵的帐户) 。</span><span class="sxs-lookup"><span data-stu-id="4c676-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="4c676-135">但是，防钓鱼保护可以更好地检测这些其他类型的网络钓鱼方法。</span><span class="sxs-lookup"><span data-stu-id="4c676-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="4c676-136">EOP 中的保护层相互协作并相互构建。</span><span class="sxs-lookup"><span data-stu-id="4c676-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="4c676-137">其他大型电子邮件服务是否阻止未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="4c676-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="4c676-138">几乎所有大型电子邮件服务都实施传统的 SPF、DKIM 和 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="4c676-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="4c676-139">某些服务具有其他更严格的检查，但很少会执行 EOP 来阻止未经身份验证的电子邮件，并视为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="4c676-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="4c676-140">但是，行业越来越了解未经身份验证的电子邮件的问题，尤其是由于网络钓鱼问题。</span><span class="sxs-lookup"><span data-stu-id="4c676-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="4c676-141">如果启用反欺骗，我是否需要启用"高级垃圾邮件筛选器"设置"SPF 记录： 硬失败" (_MarkAsSpamSpfRecordHardFail_) ？</span><span class="sxs-lookup"><span data-stu-id="4c676-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="4c676-142">否。</span><span class="sxs-lookup"><span data-stu-id="4c676-142">No.</span></span> <span data-ttu-id="4c676-143">不再需要此 ASF 设置。</span><span class="sxs-lookup"><span data-stu-id="4c676-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="4c676-144">反欺骗保护会考虑 SPF 硬失败和更广泛的条件集。</span><span class="sxs-lookup"><span data-stu-id="4c676-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="4c676-145">如果已启用防欺骗和“SPF 记录:硬故障”(_MarkAsSpamSpfRecordHardFail_)，可能会收到更多误报。</span><span class="sxs-lookup"><span data-stu-id="4c676-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="4c676-146">建议您禁用此功能，因为它几乎没有提供检测垃圾邮件或网络钓鱼邮件的其他好处，而是会生成大部分误报。</span><span class="sxs-lookup"><span data-stu-id="4c676-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="4c676-147">有关详细信息，请参阅 [EOP 中的"高级垃圾邮件筛选器 (ASF) 设置](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="4c676-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="4c676-148">发件人重写方案是否有助于修复转发的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="4c676-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="4c676-149">SRS 仅部分修复了转发电子邮件的问题。</span><span class="sxs-lookup"><span data-stu-id="4c676-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="4c676-150">通过重写 SMTP MAIL **FROM，SRS** 可以确保转发的邮件通过下一个目标的 SPF。</span><span class="sxs-lookup"><span data-stu-id="4c676-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="4c676-151">但是，由于反欺骗基于"收件人"地址以及 **MAIL FROM** 或 DKIM 签名域 (或其他信号) ，因此无法阻止 SRS 转发的电子邮件被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="4c676-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
