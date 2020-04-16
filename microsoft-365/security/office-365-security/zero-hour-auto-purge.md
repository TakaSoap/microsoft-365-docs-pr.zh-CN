---
title: 零小时自动清除（ZAP）-针对垃圾邮件、恶意软件和网络钓鱼的 retroactive 保护。
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: 零小时自动清除（ZAP）是 Office 365 中的一种电子邮件保护功能，用于检测已传递到 Exchange Online 的垃圾邮件、恶意软件或网络钓鱼邮件。 ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: 44bdab5d37863bc543d953a89ac3129b3530437d
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516769"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-office-365"></a><span data-ttu-id="c6db2-104">0小时自动清除（ZAP）-针对 Office 365 中的垃圾邮件和恶意软件进行保护</span><span class="sxs-lookup"><span data-stu-id="c6db2-104">Zero-hour auto purge (ZAP) - protection against spam and malware in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="c6db2-105">概述</span><span class="sxs-lookup"><span data-stu-id="c6db2-105">Overview</span></span>

<span data-ttu-id="c6db2-106">零小时自动清除（ZAP）是 Office 365 中的一种电子邮件保护功能，追溯检测并 neutralizes 已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-106">Zero-hour auto purge (ZAP) is an email protection feature in Office 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="c6db2-107">ZAP 可与包含 Exchange Online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online Protection （EOP）一起使用。</span><span class="sxs-lookup"><span data-stu-id="c6db2-107">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="c6db2-108">ZAP 在独立 EOP 环境中无法正常工作，从而保护本地 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c6db2-108">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="c6db2-109">ZAP 的工作方式</span><span class="sxs-lookup"><span data-stu-id="c6db2-109">How ZAP works</span></span>

<span data-ttu-id="c6db2-110">Office 365 每天实时更新垃圾邮件和恶意软件签名。</span><span class="sxs-lookup"><span data-stu-id="c6db2-110">Office 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="c6db2-111">但是，用户仍可以出于各种原因（包括内容在传递给用户后 weaponized 的情况）接收恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-111">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="c6db2-112">ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="c6db2-112">ZAP addresses this issue by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="c6db2-113">ZAP 可以查找和删除用户邮箱中已有的邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-113">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="c6db2-114">对于用户而言，ZAP 操作是无缝的;如果检测到并移动了邮件，则不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="c6db2-114">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="c6db2-115">[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则（也称为传输规则）、收件箱规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="c6db2-115">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="c6db2-116">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="c6db2-116">Malware ZAP</span></span>

<span data-ttu-id="c6db2-117">对于在传递后发现包含恶意软件的已**读或未读邮件**，ZAP 将隔离包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="c6db2-118">只有管理员可以查看和管理隔离中的恶意软件消息。</span><span class="sxs-lookup"><span data-stu-id="c6db2-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="c6db2-119">默认情况下，在反恶意软件策略中启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="c6db2-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="c6db2-120">有关详细信息，请参阅[在 Office 365 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-120">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="c6db2-121">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="c6db2-121">Phish ZAP</span></span>

<span data-ttu-id="c6db2-122">对于在传递后被标识为网络钓鱼的已**读或未读邮件**，ZAP 结果取决于为适用的反垃圾邮件策略中的**网络钓鱼电子邮件**筛选判定的操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="c6db2-123">以下列表介绍了针对网络钓鱼的可用筛选判定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="c6db2-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="c6db2-124">**添加 X 标头，将\*\*\*\*带有文本的主题行预置**： ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="c6db2-125">**将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则（默认情况下启用）。</span><span class="sxs-lookup"><span data-stu-id="c6db2-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="c6db2-126">有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="c6db2-127">**将邮件重定向到电子邮件地址**，**删除邮件**，**隔离邮件**： ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="c6db2-128">只有管理员可以查看和管理网络钓鱼隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-128">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="c6db2-129">默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，而**仿冒电子邮件**筛选判定的默认操作是**隔离邮件**，这意味着网络钓鱼 ZAP 默认隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-129">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="c6db2-130">有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-130">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="c6db2-131">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="c6db2-131">Spam ZAP</span></span>

<span data-ttu-id="c6db2-132">对于在传递后被标识为垃圾邮件的**未读邮件**，ZAP 结果取决于为适用的反垃圾邮件策略中的**垃圾邮件**筛选判定所配置的操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-132">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="c6db2-133">以下列表介绍了针对垃圾邮件的可用筛选判定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="c6db2-133">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="c6db2-134">**添加 X 标头，将\*\*\*\*带有文本的主题行预置**： ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-134">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="c6db2-135">**将邮件移动到垃圾邮件**： ZAP 将邮件移动到 "垃圾邮件" 文件夹，只要邮箱中启用了垃圾邮件规则（默认情况下启用）。</span><span class="sxs-lookup"><span data-stu-id="c6db2-135">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="c6db2-136">有关详细信息，请参阅[在 Office 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-136">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="c6db2-137">**将邮件重定向到电子邮件地址**，**删除邮件**，**隔离邮件**： ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-137">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="c6db2-138">最终用户可以查看和管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-138">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="c6db2-139">默认情况下，在反垃圾邮件策略中启用垃圾邮件 ZAP，**垃圾**邮件筛选判定的默认操作是**将邮件移动到垃圾邮件文件夹**，这意味着垃圾邮件 ZAP 在默认情况下将**未读**邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c6db2-139">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="c6db2-140">有关配置垃圾邮件筛选 verdicts 的详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-140">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="c6db2-141">Office 365 高级威胁防护（ATP）的 ZAP 注意事项</span><span class="sxs-lookup"><span data-stu-id="c6db2-141">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="c6db2-142">ZAP 不会隔离[动态传递](dynamic-delivery-and-previewing.md)扫描过程中的任何邮件，或者恶意软件筛选已使用**恶意软件警报文本 .txt**文件替换了附件的情况。</span><span class="sxs-lookup"><span data-stu-id="c6db2-142">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="c6db2-143">如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并将反垃圾邮件策略中的筛选判定项设置为对邮件执行某些操作（移动到垃圾邮件、重定向、删除、隔离），则 ZAP 将默认为 "移动到垃圾邮件" 操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-143">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="c6db2-144">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="c6db2-144">How to see if ZAP moved your message</span></span>

<span data-ttu-id="c6db2-145">若要确定 ZAP 是否移动了邮件，可以使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)或[威胁浏览器（和实时检测）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-145">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="c6db2-146">请注意，作为系统操作，不会在 Exchange 邮箱审核日志中记录 ZAP。</span><span class="sxs-lookup"><span data-stu-id="c6db2-146">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="c6db2-147">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="c6db2-147">ZAP FAQ</span></span>

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="c6db2-148">问：如果将合法邮件移动到 "垃圾邮件" 文件夹中，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="c6db2-148">Q: What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="c6db2-149">A：您应遵循正常的报告过程[误报](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-149">A: You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="c6db2-150">将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是，该服务已确定邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-150">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="q-what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="c6db2-151">问：如果我使用 Office 365 隔离（而不是垃圾邮件文件夹），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="c6db2-151">Q: What if I use the Office 365 quarantine instead of the Junk Mail folder?</span></span>

<span data-ttu-id="c6db2-152">A： ZAP 将根据本主题前面所述的配置反垃圾邮件策略对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-152">A: ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="c6db2-153">问：如果我使用邮件流规则或允许/阻止的发件人列表，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="c6db2-153">Q: What if I'm using mail flow rules or allowed/blocked sender lists?</span></span>

<span data-ttu-id="c6db2-154">A：邮件流规则或阻止和允许组织设置优先。</span><span class="sxs-lookup"><span data-stu-id="c6db2-154">A: Mail flow rules or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="c6db2-155">将从 ZAP 中排除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-155">These messages are excluded from ZAP.</span></span>

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="c6db2-156">问：如果邮件被移到另一个文件夹（例如收件箱规则），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="c6db2-156">Q: What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="c6db2-157">A：如果尚未删除邮件，或只要尚未应用相同或更强的操作，则 ZAP 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="c6db2-157">A:  ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="c6db2-158">例如，如果网络钓鱼策略设置为 "隔离"，并且用户或管理员已经 junked 了该电子邮件，则隔离将执行操作以隔离该文件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="q-does-zap-change-the-message-header"></a><span data-ttu-id="c6db2-159">问： ZAP 是否会更改邮件头？</span><span class="sxs-lookup"><span data-stu-id="c6db2-159">Q: Does ZAP change the message header?</span></span>

<span data-ttu-id="c6db2-160">A： ZAP 操作不会对邮件头进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="c6db2-160">A: A ZAP action does not make any changes to the message header.</span></span>

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="c6db2-161">问： ZAP 如何影响邮箱处于保留状态？</span><span class="sxs-lookup"><span data-stu-id="c6db2-161">Q: How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="c6db2-162">A： ZAP 不会在保留邮箱时隔离邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="c6db2-162">A: ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="c6db2-163">ZAP 可以根据为反垃圾邮件策略中的垃圾邮件或网络钓鱼判定所配置的操作将邮件移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c6db2-163">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="c6db2-164">有关 Exchange Online 中的保留的详细信息，请参阅[Exchange online 中的就地保留和诉讼保留](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。</span><span class="sxs-lookup"><span data-stu-id="c6db2-164">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
