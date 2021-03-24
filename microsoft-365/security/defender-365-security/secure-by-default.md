---
title: Office 365 中的默认安全
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: '详细了解 Exchange Online Protection (EOP) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1b495a9c985077dfc88d1da7a221bb60ca10df9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056289"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="70f6f-103">Office 365 中的默认安全</span><span class="sxs-lookup"><span data-stu-id="70f6f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="70f6f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="70f6f-104">**Applies to**</span></span>
- [<span data-ttu-id="70f6f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="70f6f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="70f6f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="70f6f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="70f6f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70f6f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="70f6f-108">"默认保护"一词用于定义尽可能安全的默认设置。</span><span class="sxs-lookup"><span data-stu-id="70f6f-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="70f6f-109">但是，安全性需要与生产力平衡。</span><span class="sxs-lookup"><span data-stu-id="70f6f-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="70f6f-110">这可能包括以下各点之间的平衡：</span><span class="sxs-lookup"><span data-stu-id="70f6f-110">This can include balancing across:</span></span>

- <span data-ttu-id="70f6f-111">**可用性**：设置不应影响用户工作效率。</span><span class="sxs-lookup"><span data-stu-id="70f6f-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="70f6f-112">**风险**：安全性可能会阻止重要活动。</span><span class="sxs-lookup"><span data-stu-id="70f6f-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="70f6f-113">**旧设置**：出于业务原因，可能需要维护较旧产品和功能的一些配置，即使新的新式设置已改进。</span><span class="sxs-lookup"><span data-stu-id="70f6f-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="70f6f-114">在 Exchange Online 中拥有邮箱的 Microsoft 365 组织受 Exchange Online Protection (EOP) 。</span><span class="sxs-lookup"><span data-stu-id="70f6f-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="70f6f-115">此保护包括：</span><span class="sxs-lookup"><span data-stu-id="70f6f-115">This protection includes:</span></span>

- <span data-ttu-id="70f6f-116">包含可疑恶意软件的电子邮件将自动隔离，并通知收件人。</span><span class="sxs-lookup"><span data-stu-id="70f6f-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="70f6f-117">请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70f6f-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="70f6f-118">标识为高可信度网络钓鱼的电子邮件将按照反垃圾邮件策略操作进行处理。</span><span class="sxs-lookup"><span data-stu-id="70f6f-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="70f6f-119">请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70f6f-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="70f6f-120">有关 EOP 详细信息，请参阅 [Exchange Online Protection overview](exchange-online-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="70f6f-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="70f6f-121">由于 Microsoft 默认希望保护我们的客户安全，因此某些租户替代不适用于恶意软件或高可信度网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="70f6f-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="70f6f-122">这些替代包括：</span><span class="sxs-lookup"><span data-stu-id="70f6f-122">These overrides include:</span></span>

- <span data-ttu-id="70f6f-123">允许发件人列表或允许的域 (反垃圾邮件策略) </span><span class="sxs-lookup"><span data-stu-id="70f6f-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="70f6f-124">Outlook 安全发件人</span><span class="sxs-lookup"><span data-stu-id="70f6f-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="70f6f-125">IP 允许列表 (连接筛选) </span><span class="sxs-lookup"><span data-stu-id="70f6f-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="70f6f-126">有关这些替代项详细信息，请参阅创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="70f6f-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70f6f-127">我们正在弃用 EOP 反垃圾邮件策略中的高可信度网络钓鱼电子邮件裁定的"将邮件移动到垃圾邮件文件夹"操作。</span><span class="sxs-lookup"><span data-stu-id="70f6f-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="70f6f-128">对高可信度网络钓鱼邮件使用此操作的反垃圾邮件策略将转换为隔离 **邮件**。</span><span class="sxs-lookup"><span data-stu-id="70f6f-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="70f6f-129">高 **可信度网络钓鱼** 邮件的"将邮件重定向到电子邮件地址"操作不受影响。</span><span class="sxs-lookup"><span data-stu-id="70f6f-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="70f6f-130">默认情况下，"安全"不是可以打开或关闭的设置，而是我们的筛选开箱即用来将潜在危险或不需要的邮件从邮箱中排除的方式。</span><span class="sxs-lookup"><span data-stu-id="70f6f-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="70f6f-131">应隔离恶意软件和高可信度网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="70f6f-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="70f6f-132">只有管理员才能管理被隔离为恶意软件或高可信度网络钓鱼的邮件，并且他们还可以从该邮件向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="70f6f-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="70f6f-133">有关详细信息，请参阅在 EOP 中以管理员角色管理隔离 [的邮件和文件](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="70f6f-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="70f6f-134">有关我们这样做的原因的更多</span><span class="sxs-lookup"><span data-stu-id="70f6f-134">More on why we're doing this</span></span>

<span data-ttu-id="70f6f-135">默认情况下，确保安全的提示是：即使您知道邮件是恶意邮件，我们将对邮件执行相同的操作，即使已配置的异常将允许传递该邮件。</span><span class="sxs-lookup"><span data-stu-id="70f6f-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="70f6f-136">这是我们一直对恶意软件使用的相同方法，现在我们正在将相同的行为扩展到高可信度网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="70f6f-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="70f6f-137">我们的数据显示，与隔离相比，用户点击垃圾邮件文件夹中邮件中的恶意链接的可能性是 30 倍。</span><span class="sxs-lookup"><span data-stu-id="70f6f-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="70f6f-138">我们的数据还表明，对于高可信度网络钓鱼 (误报率) 误报率非常低，管理员可以通过管理员提交来解决任何误报。</span><span class="sxs-lookup"><span data-stu-id="70f6f-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="70f6f-139">我们还确定反垃圾邮件策略中的允许发件人和允许的域列表和 Outlook 中的安全发件人过于广泛，并且导致危害大于好。</span><span class="sxs-lookup"><span data-stu-id="70f6f-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="70f6f-140">另一方面：作为一项安全服务，我们代表你采取行动，防止你的用户遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="70f6f-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="70f6f-141">Exceptions</span><span class="sxs-lookup"><span data-stu-id="70f6f-141">Exceptions</span></span>

<span data-ttu-id="70f6f-142">允许高可信度网络钓鱼邮件绕过筛选的唯一替代是 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="70f6f-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="70f6f-143">若要使用邮件流规则绕过筛选，请参阅使用邮件流[规则设置邮件中的 SCL。](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="70f6f-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="70f6f-144">只应考虑在下列情况下使用替代：</span><span class="sxs-lookup"><span data-stu-id="70f6f-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="70f6f-145">网络钓鱼模拟：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="70f6f-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="70f6f-146">Security/SecOps 邮箱：安全团队用于获取未筛选邮件的专用邮箱 (好和坏) 。</span><span class="sxs-lookup"><span data-stu-id="70f6f-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="70f6f-147">然后，团队可以查看它们是否包含恶意内容。</span><span class="sxs-lookup"><span data-stu-id="70f6f-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="70f6f-148">第三方筛选器：当域的 MX 记录不指向 Office 365 时，默认情况下安全不适用。</span><span class="sxs-lookup"><span data-stu-id="70f6f-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="70f6f-149">误报：你可能希望暂时允许 Microsoft 通过管理员提交分析某些 [邮件](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="70f6f-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="70f6f-150">与所有替代一样，建议它们为临时替代。</span><span class="sxs-lookup"><span data-stu-id="70f6f-150">As with all overrides, it is recommended that they are temporary.</span></span>
