---
title: '零小时自动清除 (ZAP) '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 (ZAP) 如何在 Exchange Online 邮箱中追溯将传递的邮件移动到追溯被发现为垃圾邮件或网络钓鱼的 "垃圾邮件" 文件夹或隔离中的零小时自动清除。
ms.openlocfilehash: fd5186bc40d2d80097e6292d86ea113a41e0dd52
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131137"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="7eea5-103">Exchange Online 中的零小时自动清除 (ZAP) </span><span class="sxs-lookup"><span data-stu-id="7eea5-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="7eea5-104">ZAP 的基本功能</span><span class="sxs-lookup"><span data-stu-id="7eea5-104">Basic features of ZAP</span></span>

<span data-ttu-id="7eea5-105">在 Exchange Online 中有邮箱的 Microsoft 365 组织中，零小时自动清除 (ZAP) 是一种电子邮件保护功能，追溯检测并 neutralizes 已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="7eea5-106">ZAP 在独立的 Exchange Online Protection (EOP) 保护本地 Exchange 邮箱的环境中不起作用。</span><span class="sxs-lookup"><span data-stu-id="7eea5-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="7eea5-107">ZAP 的工作方式</span><span class="sxs-lookup"><span data-stu-id="7eea5-107">How ZAP works</span></span>

<span data-ttu-id="7eea5-108">垃圾邮件和恶意软件签名每天都会在服务中实时更新。</span><span class="sxs-lookup"><span data-stu-id="7eea5-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="7eea5-109">但是，用户仍可以出于各种原因（包括内容在传递给用户后 weaponized 的情况）接收恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="7eea5-110">ZAP 通过持续监控对服务中的垃圾邮件和恶意软件签名的更新来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="7eea5-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="7eea5-111">ZAP 可以查找和删除用户邮箱中已有的邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="7eea5-112">对于用户而言，ZAP 操作是无缝的;如果检测到并移动了邮件，则不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="7eea5-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="7eea5-113">[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则 (也称为 "传输规则) "、"收件箱规则" 或 "其他筛选器" 优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="7eea5-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="7eea5-114">与邮件流中的操作类似，这意味着即使服务确定所传递的邮件需要 ZAP，也不会由于安全发件人配置而导致邮件不起作用。</span><span class="sxs-lookup"><span data-stu-id="7eea5-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="7eea5-115">这是在将邮件配置为绕过筛选时要注意的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="7eea5-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="7eea5-116">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="7eea5-116">Malware ZAP</span></span>

<span data-ttu-id="7eea5-117">对于在传递后发现包含恶意软件的已 **读或未读邮件** ，ZAP 将隔离包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="7eea5-118">只有管理员可以查看和管理隔离中的恶意软件消息。</span><span class="sxs-lookup"><span data-stu-id="7eea5-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="7eea5-119">默认情况下，在反恶意软件策略中启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="7eea5-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="7eea5-120">有关详细信息，请参阅 [在 EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="7eea5-121">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="7eea5-121">Phish ZAP</span></span>

<span data-ttu-id="7eea5-122">对于在传递后被标识为 "仿冒" 的已 **读或未读邮件** ，ZAP 结果取决于为适用的反垃圾邮件策略中的 **网络钓鱼电子邮件** 筛选判定的操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-122">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="7eea5-123">以下列表介绍了针对网络钓鱼及其可能的 ZAP 结果的可用筛选判定操作：</span><span class="sxs-lookup"><span data-stu-id="7eea5-123">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="7eea5-124">**添加 X 标头，将\*\*\*\*带有文本的主题行预置**： ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="7eea5-125">**将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则 (默认情况下，将启用该规则) 。</span><span class="sxs-lookup"><span data-stu-id="7eea5-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="7eea5-126">有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="7eea5-127">**将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**： ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="7eea5-128">默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，而 **仿冒电子邮件** 筛选判定的默认操作是 **隔离邮件**，这意味着网络钓鱼 ZAP 默认隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="7eea5-129">有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="7eea5-130">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="7eea5-130">Spam ZAP</span></span>

<span data-ttu-id="7eea5-131">对于在传递后被标识为垃圾邮件的 **未读邮件** ，ZAP 结果取决于为适用的反垃圾邮件策略中的 **垃圾邮件** 筛选判定所配置的操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="7eea5-132">以下列表介绍了针对垃圾邮件的可用筛选判定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="7eea5-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="7eea5-133">**添加 X 标头，将\*\*\*\*带有文本的主题行预置**： ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="7eea5-134">**将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则 (默认情况下，将启用该规则) 。</span><span class="sxs-lookup"><span data-stu-id="7eea5-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="7eea5-135">有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="7eea5-136">**将邮件重定向到电子邮件地址**， **删除邮件**， **隔离邮件**： ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="7eea5-137">最终用户可以查看和管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="7eea5-138">默认情况下，在反垃圾邮件策略中启用垃圾邮件 ZAP， **垃圾** 邮件筛选判定的默认操作是 **将邮件移动到垃圾邮件文件夹**，这意味着垃圾邮件 ZAP 在默认情况下将 **未读** 邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7eea5-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="7eea5-139">有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="7eea5-140">Microsoft Defender for Office 365 的 ZAP 注意事项</span><span class="sxs-lookup"><span data-stu-id="7eea5-140">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="7eea5-141">ZAP 不会隔离在安全附件扫描中的 [动态传递](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 过程中的任何邮件，或者 EOP 恶意软件筛选已将附件替换为 **恶意软件警报 Text.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="7eea5-142">如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选判定项设置为对邮件执行某些操作 (移到 "垃圾邮件"、"重定向"、"删除" 或 "隔离) "，则 ZAP 将默认为 "移动到垃圾邮件" 操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-142">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="7eea5-143">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="7eea5-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="7eea5-144">若要确定 ZAP 是否移动了邮件，可以使用 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report) 或 [威胁浏览器 (和实时检测) ](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="7eea5-145">请注意，作为系统操作，不会在 Exchange 邮箱审核日志中记录 ZAP。</span><span class="sxs-lookup"><span data-stu-id="7eea5-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="7eea5-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="7eea5-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="7eea5-147">如果将合法邮件移动到 "垃圾邮件" 文件夹中，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="7eea5-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="7eea5-148">您应遵循正常的报告过程 [误报](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="7eea5-149">将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是，该服务已确定邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="7eea5-150">如果我使用隔离文件夹而不是垃圾邮件文件夹，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="7eea5-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="7eea5-151">根据本主题前面所述的配置反垃圾邮件策略，ZAP 将对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="7eea5-152">如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="7eea5-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="7eea5-153">安全发件人、邮件流规则或阻止和允许组织设置优先。</span><span class="sxs-lookup"><span data-stu-id="7eea5-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="7eea5-154">由于服务正在执行您配置的操作，这些邮件将从 ZAP 中排除。</span><span class="sxs-lookup"><span data-stu-id="7eea5-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="7eea5-155">这是在将邮件配置为绕过筛选时要注意的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="7eea5-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="7eea5-156">如果邮件移动到另一个文件夹 (例如收件箱规则) ，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="7eea5-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="7eea5-157">只要邮件尚未删除，或者只要相同或更强的操作尚未应用，ZAP 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="7eea5-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="7eea5-158">例如，如果将反网络钓鱼策略设置为隔离，邮件已在垃圾邮件中，则 ZAP 将执行操作以隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-158">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="7eea5-159">ZAP 对邮箱的保留有何影响？</span><span class="sxs-lookup"><span data-stu-id="7eea5-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="7eea5-160">ZAP 不会在保留邮箱时隔离邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="7eea5-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="7eea5-161">ZAP 可以根据为反垃圾邮件策略中的垃圾邮件或网络钓鱼判定所配置的操作将邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7eea5-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="7eea5-162">有关 Exchange Online 中的保留的详细信息，请参阅 [Exchange online 中的就地保留和诉讼保留](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。</span><span class="sxs-lookup"><span data-stu-id="7eea5-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
