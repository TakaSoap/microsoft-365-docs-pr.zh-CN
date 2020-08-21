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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以在 Exchange Online Protection 或 EOP 项目中查看有关反欺骗保护的常见问题 () 。
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826669"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="c53a2-103">防欺骗保护常见问题</span><span class="sxs-lookup"><span data-stu-id="c53a2-103">Anti-spoofing protection FAQ</span></span>

<span data-ttu-id="c53a2-104">本主题为在 Exchange Online 中有邮箱的 Microsoft 365 组织反欺骗保护或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织提供了常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="c53a2-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="c53a2-105">有关反垃圾邮件保护的问题和解答，请参阅"[反垃圾邮件保护常见问题解答"。](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="c53a2-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="c53a2-106">有关反恶意软件保护的问题和解答，请参阅 ["反恶意软件保护常见问题解答"](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="c53a2-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="c53a2-107">为什么 Microsoft 选择垃圾未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="c53a2-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="c53a2-108">由于网络钓鱼攻击的影响，并且电子邮件身份验证已存在超过 15 年，因此 Microsoft 相信允许未经身份验证的入站电子邮件允许使用漏报电子邮件的风险高于丢失合法入站电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="c53a2-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="c53a2-109">垃圾邮件是否有未经身份验证的入站电子邮件会导致合法电子邮件被标记为垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="c53a2-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="c53a2-110">在 2018 年启用此功能时，可能会出现一些误报， (有正常消息被标记为错误) 。</span><span class="sxs-lookup"><span data-stu-id="c53a2-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="c53a2-111">但是，随着时间的了解，发件人已根据新的发件人身份验证要求进行调整，并且对于大多数电子邮件路径而被错误识别为欺骗邮件的邮件数量都是不可忽略的。</span><span class="sxs-lookup"><span data-stu-id="c53a2-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="c53a2-112">Microsoft 本身在部署到客户之前先几周采用新电子邮件身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="c53a2-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="c53a2-113">虽然最初出现了中断，但此现象逐渐减少了。</span><span class="sxs-lookup"><span data-stu-id="c53a2-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a><span data-ttu-id="c53a2-114">非 ATP 的 Microsoft 365 客户是否提供欺骗智能？</span><span class="sxs-lookup"><span data-stu-id="c53a2-114">Is spoof intelligence available to Microsoft 365 customers without ATP?</span></span>

<span data-ttu-id="c53a2-115">是。</span><span class="sxs-lookup"><span data-stu-id="c53a2-115">Yes.</span></span> <span data-ttu-id="c53a2-116">自 2018 年 10 月起，欺骗智能适用于所有在 Exchange Online 中有邮箱的组织和无 Exchange Online 邮箱的独立 EOP 组织。</span><span class="sxs-lookup"><span data-stu-id="c53a2-116">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="c53a2-117">反欺骗技术最初仅部署到订阅 Office 365 企业版 E5 订阅或 Office 365 高级威胁防护 (Office 365 ATP) 加载项的组织。</span><span class="sxs-lookup"><span data-stu-id="c53a2-117">Anti-spoofing technology was initially deployed only to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (Office 365 ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="c53a2-118">如何向 Microsoft 报告垃圾邮件或非垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="c53a2-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="c53a2-119">参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="c53a2-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="c53a2-120">我是管理员，并且不知道电子邮件域中邮件的所有来源！</span><span class="sxs-lookup"><span data-stu-id="c53a2-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="c53a2-121">请参阅 [你并不知道电子邮件的所有来源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="c53a2-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="c53a2-122">如果对组织禁用反欺骗保护会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="c53a2-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="c53a2-123">我们不建议这样做，因为你将接触到更多错过的网络钓鱼和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c53a2-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="c53a2-124">并非所有网络钓鱼都是欺骗性的，并且并非所有欺骗都会错过。</span><span class="sxs-lookup"><span data-stu-id="c53a2-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="c53a2-125">但是，你面临的风险将高于启用反欺骗的客户。</span><span class="sxs-lookup"><span data-stu-id="c53a2-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="c53a2-126">既 [然可以使用连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 功能，在将电子邮件传递到 EOP 之前，如果 MX 记录指向了其他服务器或服务，我们不再建议您关闭反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="c53a2-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="c53a2-127">反欺骗防护是否意味着我将防止所有网络钓鱼？</span><span class="sxs-lookup"><span data-stu-id="c53a2-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="c53a2-128">遗遗而无法。</span><span class="sxs-lookup"><span data-stu-id="c53a2-128">Unfortunately, no.</span></span> <span data-ttu-id="c53a2-129">攻击者会不断采用其他技术， (例如，免费电子邮件服务组中被泄漏的帐户或) 。</span><span class="sxs-lookup"><span data-stu-id="c53a2-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="c53a2-130">但是，反网络钓鱼防护可以更好地检测这些其他类型的网络钓鱼方法。</span><span class="sxs-lookup"><span data-stu-id="c53a2-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="c53a2-131">EOP 中的保护层是通过一起设计的，并且是相当构建的。</span><span class="sxs-lookup"><span data-stu-id="c53a2-131">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="c53a2-132">其他大型电子邮件服务是否会阻止未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="c53a2-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="c53a2-133">几上所有大型电子邮件服务都实施传统的 SPF、DKIM 和 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="c53a2-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="c53a2-134">某些服务拥有其他更严格的检查，但少量使用 EOP 阻止未经身份验证的电子邮件并将其视为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="c53a2-134">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="c53a2-135">但是，行业更加注解了有关未经身份验证的电子邮件问题的更加了解，特别是网络钓鱼问题。</span><span class="sxs-lookup"><span data-stu-id="c53a2-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="c53a2-136">如果启用反欺骗，是否仍需要启用高级垃圾邮件筛选 ("SPF 记录：硬失败"许可证标记标记标记 _) A"_ 重点失败"？</span><span class="sxs-lookup"><span data-stu-id="c53a2-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="c53a2-137">不正确。</span><span class="sxs-lookup"><span data-stu-id="c53a2-137">No.</span></span> <span data-ttu-id="c53a2-138">不再需要此 ASF 设置，因为反欺骗不仅考虑 SPF 硬失败，还会考虑更广泛的标准。</span><span class="sxs-lookup"><span data-stu-id="c53a2-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="c53a2-139">如果已启用防欺骗和“SPF 记录:硬故障”\*\*\*\*(_MarkAsSpamSpfRecordHardFail_)，可能会收到更多误报。</span><span class="sxs-lookup"><span data-stu-id="c53a2-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="c53a2-140">我们建议您禁用此功能，因为它几乎对检测垃圾邮件或网络钓鱼邮件提供其他任何好处，而是会生成大部分误报。</span><span class="sxs-lookup"><span data-stu-id="c53a2-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="c53a2-141">有关详细信息，请参阅" [高级垃圾邮件筛选 (EOP 中) ASF 筛选器设置](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="c53a2-141">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="c53a2-142">发件人重写方案是否帮助修复转发的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="c53a2-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="c53a2-143">SRS 仅部分修复了转发电子邮件的问题。</span><span class="sxs-lookup"><span data-stu-id="c53a2-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="c53a2-144">通过重写 SMTP **MAIL FROM，SRS**可以确保转发的邮件在下一个目标位置通过 SPF。</span><span class="sxs-lookup"><span data-stu-id="c53a2-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="c53a2-145">但是，由于反欺骗基于发件人地址以及**MAIL FROM** **From**或 DKIM 签名域 (或其他信号) ，因此防止将 SRS 转发的电子邮件标记为欺骗邮件不够。</span><span class="sxs-lookup"><span data-stu-id="c53a2-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
