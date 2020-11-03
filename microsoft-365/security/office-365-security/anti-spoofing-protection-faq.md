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
- m365initiative-defender-office365
description: 管理员可以查看有关 Exchange Online Protection (EOP) 中的 "反欺骗" 保护的常见问题和解答。
ms.openlocfilehash: a5b0484e41e3df7a7b6ad16e69a4f7062b19b554
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844388"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="5308a-103">防欺骗保护常见问题</span><span class="sxs-lookup"><span data-stu-id="5308a-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5308a-104">本文提供了有关使用 Exchange Online 中的邮箱或独立 Exchange Online Protection (EOP) 组织（无需 Exchange Online 邮箱）的 Microsoft 365 组织的反欺诈保护的常见问题和解答。</span><span class="sxs-lookup"><span data-stu-id="5308a-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="5308a-105">有关反垃圾邮件保护的问题和解答，请参阅 [反垃圾邮件保护常见问题解答](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="5308a-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="5308a-106">有关反恶意软件保护的问题和解答，请参阅 [反恶意软件保护常见问题解答](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5308a-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="5308a-107">为什么 Microsoft 选择未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="5308a-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="5308a-108">Microsoft 认为，继续允许未经身份验证的入站电子邮件的风险要高于丢失合法入站电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="5308a-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="5308a-109">Junking 未通过身份验证的入站电子邮件是否会导致合法电子邮件被标记为垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="5308a-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="5308a-110">如果 Microsoft 在2018中启用此功能，则会发生误报 (将正常的邮件标记为坏) 。</span><span class="sxs-lookup"><span data-stu-id="5308a-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="5308a-111">但是，随着时间的推移，发件人会根据要求进行调整。</span><span class="sxs-lookup"><span data-stu-id="5308a-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="5308a-112">对于大多数电子邮件路径，misidentified 为欺骗的邮件数变得可忽略。</span><span class="sxs-lookup"><span data-stu-id="5308a-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="5308a-113">Microsoft 本身在将新的电子邮件身份验证要求部署到客户之前，先将其在几周内采纳。</span><span class="sxs-lookup"><span data-stu-id="5308a-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="5308a-114">虽然最初出现了中断，但此现象逐渐减少了。</span><span class="sxs-lookup"><span data-stu-id="5308a-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="5308a-115">在没有 Defender for Office 365 的情况下，Microsoft 365 客户是否可以使用欺骗版智能？</span><span class="sxs-lookup"><span data-stu-id="5308a-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="5308a-116">是。</span><span class="sxs-lookup"><span data-stu-id="5308a-116">Yes.</span></span> <span data-ttu-id="5308a-117">从10月2018起，欺骗智能可供具有邮箱的 Exchange Online 中的所有组织和独立 EOP 组织（无 Exchange Online 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="5308a-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="5308a-118">如何向 Microsoft 报告垃圾邮件或非垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="5308a-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="5308a-119">参见 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="5308a-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="5308a-120">我是管理员，我不知道我的电子邮件域中的邮件的所有来源！</span><span class="sxs-lookup"><span data-stu-id="5308a-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="5308a-121">请参阅 [您不知道您的电子邮件的所有来源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="5308a-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="5308a-122">如果我对我的组织禁用反欺骗保护，会发生什么？</span><span class="sxs-lookup"><span data-stu-id="5308a-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="5308a-123">我们不建议禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="5308a-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="5308a-124">禁用保护将允许在您的组织中传递更多的网络钓鱼和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="5308a-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="5308a-125">并不是所有的网络钓鱼都是哄骗，并且并非所有欺骗邮件都将丢失。</span><span class="sxs-lookup"><span data-stu-id="5308a-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="5308a-126">但是，风险会更高。</span><span class="sxs-lookup"><span data-stu-id="5308a-126">However, your risk will be higher.</span></span>

<span data-ttu-id="5308a-127">现在，已 [为连接器提供增强的筛选功能](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ，如果在 EOP 之前通过其他服务路由电子邮件，则我们不再建议关闭反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="5308a-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="5308a-128">反欺骗保护意味着我将免受所有网络钓鱼的阻止？</span><span class="sxs-lookup"><span data-stu-id="5308a-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="5308a-129">遗憾的是，不会。</span><span class="sxs-lookup"><span data-stu-id="5308a-129">Unfortunately, no.</span></span> <span data-ttu-id="5308a-130">攻击者将使用其他技术 (例如，在免费的电子邮件服务) 中受到危害的帐户或帐户。</span><span class="sxs-lookup"><span data-stu-id="5308a-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="5308a-131">但是，反网络钓鱼保护的工作速度更好，可以检测到这些其他类型的网络钓鱼方法。</span><span class="sxs-lookup"><span data-stu-id="5308a-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="5308a-132">EOP 中的保护层设计为协同工作并在彼此之上建立。</span><span class="sxs-lookup"><span data-stu-id="5308a-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="5308a-133">其他大型电子邮件服务是否阻止未经身份验证的入站电子邮件？</span><span class="sxs-lookup"><span data-stu-id="5308a-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="5308a-134">几乎所有大型电子邮件服务都实现传统 SPF、DKIM 和 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="5308a-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="5308a-135">有些服务有其他更严格的检查，但并不像 EOP 那样阻止未经过身份验证的电子邮件，并将其视为欺骗性的邮件。</span><span class="sxs-lookup"><span data-stu-id="5308a-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="5308a-136">但是，该行业越来越多地意识到有关未经身份验证的电子邮件的问题，尤其是由于网络钓鱼问题而引起的。</span><span class="sxs-lookup"><span data-stu-id="5308a-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="5308a-137">我是否仍然需要启用高级垃圾邮件筛选器设置 "SPF record： hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) 如果我启用反欺骗？</span><span class="sxs-lookup"><span data-stu-id="5308a-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) if I enable anti-spoofing?</span></span>

<span data-ttu-id="5308a-138">不正确。</span><span class="sxs-lookup"><span data-stu-id="5308a-138">No.</span></span> <span data-ttu-id="5308a-139">此 ASF 设置不再是必需的。</span><span class="sxs-lookup"><span data-stu-id="5308a-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="5308a-140">反欺骗保护考虑两种 SPF 硬失败和一组更广泛的条件。</span><span class="sxs-lookup"><span data-stu-id="5308a-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="5308a-141">如果已启用防欺骗和“SPF 记录:硬故障”( _MarkAsSpamSpfRecordHardFail_ )，可能会收到更多误报。</span><span class="sxs-lookup"><span data-stu-id="5308a-141">If you have anti-spoofing enabled and the **SPF record: hard fail** ( _MarkAsSpamSpfRecordHardFail_ ) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="5308a-142">我们建议您禁用此功能，因为它几乎没有额外的优势来检测垃圾邮件或网络钓鱼邮件，而是生成大多数误报。</span><span class="sxs-lookup"><span data-stu-id="5308a-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="5308a-143">有关详细信息，请参阅 [EOP 中的高级垃圾邮件筛选器 (ASF) 设置](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="5308a-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="5308a-144">发件人重写方案是否有助于修复转发的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="5308a-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="5308a-145">SRS 仅部分修复了转发电子邮件的问题。</span><span class="sxs-lookup"><span data-stu-id="5308a-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="5308a-146">通过重写 SMTP **邮件** ，SRS 可以确保转发的邮件在下一个目的地传递 SPF。</span><span class="sxs-lookup"><span data-stu-id="5308a-146">By rewriting the SMTP **MAIL FROM** , SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="5308a-147">但是，由于反欺骗是基于 "发件人 **地址" 或 "DKIM** " 签名域 (中的 " **发件** 人地址" 或其他信号) ，因此不能阻止将 SRS 转发的电子邮件标记为欺骗。</span><span class="sxs-lookup"><span data-stu-id="5308a-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
