---
title: 默认情况下在 Office 365 中安全
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '有关详细信息，请参阅 Exchange Online Protection (EOP 中的默认安全设置) '
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602027"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="b1914-103">默认情况下在 Office 365 中安全</span><span class="sxs-lookup"><span data-stu-id="b1914-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1914-104">"默认情况下安全" 是一种术语，用于定义尽可能安全的默认设置。</span><span class="sxs-lookup"><span data-stu-id="b1914-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="b1914-105">但是，安全性需要与工作效率平衡。</span><span class="sxs-lookup"><span data-stu-id="b1914-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="b1914-106">这可能包括跨以下各项的平衡：</span><span class="sxs-lookup"><span data-stu-id="b1914-106">This can include balancing across:</span></span>

- <span data-ttu-id="b1914-107">**可用性**：设置不应以用户工作效率为依据。</span><span class="sxs-lookup"><span data-stu-id="b1914-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="b1914-108">**风险**：安全性可能会阻止重要活动。</span><span class="sxs-lookup"><span data-stu-id="b1914-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="b1914-109">**旧版设置**：出于商业原因，可能需要维护某些旧产品和功能的一些配置，即使新的新式设置得到改进也是如此。</span><span class="sxs-lookup"><span data-stu-id="b1914-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="b1914-110">通过 exchange online 中邮箱的 Microsoft 365 组织受到 Exchange Online Protection (EOP) 的保护。</span><span class="sxs-lookup"><span data-stu-id="b1914-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b1914-111">此保护包括：</span><span class="sxs-lookup"><span data-stu-id="b1914-111">This protection includes:</span></span>

- <span data-ttu-id="b1914-112">带有可疑恶意软件的电子邮件将自动被隔离，收件人将收到通知。</span><span class="sxs-lookup"><span data-stu-id="b1914-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="b1914-113">请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1914-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="b1914-114">被标识为高可信度网络钓鱼的电子邮件将根据反垃圾邮件策略操作进行处理。</span><span class="sxs-lookup"><span data-stu-id="b1914-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="b1914-115">请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1914-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="b1914-116">有关 EOP 的详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b1914-116">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="b1914-117">由于 Microsoft 想让我们的客户在默认情况下是安全的，因此某些租户替代不会应用于恶意软件或高可信度的网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="b1914-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="b1914-118">这些替代包括：</span><span class="sxs-lookup"><span data-stu-id="b1914-118">These overrides include:</span></span>

- <span data-ttu-id="b1914-119"> (反垃圾邮件策略的允许的发件人列表或允许的域列表) </span><span class="sxs-lookup"><span data-stu-id="b1914-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="b1914-120">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="b1914-120">Outlook Safe Senders</span></span>
- <span data-ttu-id="b1914-121"> (连接筛选的 IP 允许列表) </span><span class="sxs-lookup"><span data-stu-id="b1914-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="b1914-122">有关这些覆盖的详细信息，可参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="b1914-122">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="b1914-123">"默认安全" 不是一种可以打开或关闭的设置，但也是我们的筛选在框中的工作方式，以防止邮箱中出现潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1914-123">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="b1914-124">应隔离恶意软件和高可信度的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="b1914-124">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="b1914-125">只有管理员可以管理被隔离为恶意软件或高可信度网络钓鱼的邮件，也可以在那里向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="b1914-125">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="b1914-126">有关详细信息，请参阅 [在 EOP 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="b1914-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="b1914-127">有关此操作的原因的详细信息</span><span class="sxs-lookup"><span data-stu-id="b1914-127">More on why we're doing this</span></span>

<span data-ttu-id="b1914-128">默认情况下安全的精神是：我们对邮件采取相同的操作，如果您知道邮件是恶意的，即使有允许的地方也是如此。</span><span class="sxs-lookup"><span data-stu-id="b1914-128">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even if there was an allow in place.</span></span> <span data-ttu-id="b1914-129">这与我们在恶意软件中使用的方法相同，现在我们将此相同的行为扩展到高可信度的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="b1914-129">This is the same approach that we've used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span> <span data-ttu-id="b1914-130">我们的数据表明高可信度的网络钓鱼邮件的误报利率极低，管理员可以使用管理员提交的任何误报来解决。</span><span class="sxs-lookup"><span data-stu-id="b1914-130">Our data indicates that the false positive rate for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span> <span data-ttu-id="b1914-131">我们的数据还表示在反垃圾邮件策略和 Outlook 中的安全发件人中，允许的发件人列表和允许的域列表过于广泛，因而导致更大损害。</span><span class="sxs-lookup"><span data-stu-id="b1914-131">Our data also indicates that the allowed sender lists and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and causing more harm than good.</span></span>

<span data-ttu-id="b1914-132">为了使其成为另一种方式：作为一项安全服务，我们正在代表你，以防止你的用户受到危害。</span><span class="sxs-lookup"><span data-stu-id="b1914-132">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> <span data-ttu-id="b1914-133">此外，默认情况下安全不会完全接管反垃圾邮件策略中的高可信度网络钓鱼邮件的可用选项。</span><span class="sxs-lookup"><span data-stu-id="b1914-133">In addition, secure by default is not a full takeover of your available options for high confidence phishing messages in anti-spam policies.</span></span> <span data-ttu-id="b1914-134">尽管我们建议隔离，但仍可使用的其他操作仍可用 (移动到 "垃圾邮件" 文件夹或重定向到电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="b1914-134">Although we recommend Quarantine, the other actions that have always been available are still available (Move to Junk Email folder or Redirect to an email address).</span></span>

## <a name="exceptions"></a><span data-ttu-id="b1914-135">Exceptions</span><span class="sxs-lookup"><span data-stu-id="b1914-135">Exceptions</span></span>

<span data-ttu-id="b1914-136">允许高可信度仿冒邮件绕过筛选的唯一替代是 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="b1914-136">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="b1914-137">若要使用邮件流规则绕过筛选，请参阅 [使用邮件流规则在邮件中设置 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b1914-137">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="b1914-138">仅在以下情况下，才应考虑使用替代：</span><span class="sxs-lookup"><span data-stu-id="b1914-138">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="b1914-139">网络钓鱼模拟：模拟攻击可帮助您在真正的攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="b1914-139">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="b1914-140">Security/SecOps 邮箱：安全团队使用的专用邮箱)  (好的和坏的中获取未筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1914-140">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="b1914-141">然后，团队可以查看它们是否包含恶意内容。</span><span class="sxs-lookup"><span data-stu-id="b1914-141">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="b1914-142">第三方筛选器：某些第三方供应商建议将 EOP (SCL =-1) ，因为第三方筛选器将管理邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="b1914-142">Third-party filters: Some third-party vendors will recommend turning off EOP (SCL=-1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="b1914-143">Microsoft 不建议关闭 EOP，因为 [Microsoft Defender For Office 365](office-365-atp.md)需要 EOP。</span><span class="sxs-lookup"><span data-stu-id="b1914-143">Microsoft does not recommend turning off EOP as EOP is required for [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b1914-144">相反，此处的建议是为连接器启用 [增强的筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)功能。</span><span class="sxs-lookup"><span data-stu-id="b1914-144">Instead, the recommendation here is to turn on [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>
- <span data-ttu-id="b1914-145">误报：您可能希望临时允许某些邮件仍由 Microsoft [通过管理员提交](admin-submission.md)进行分析。</span><span class="sxs-lookup"><span data-stu-id="b1914-145">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="b1914-146">与所有替代一样，建议它们是临时性的。</span><span class="sxs-lookup"><span data-stu-id="b1914-146">As with all overrides, it is recommended that they are temporary.</span></span>
