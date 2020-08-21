---
title: 零时差自动清除 O) AP (
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
description: 管理员可以了解零时差差自动清除 (ZAP) 如何通过试图将 Exchange Online 邮箱中的传递邮件移至垃圾邮件文件夹或被动被动发现为垃圾邮件或网络钓鱼的隔离邮箱。
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826693"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="6a44e-103">在 Exchange Online 中为 ZAP (零时) 清除</span><span class="sxs-lookup"><span data-stu-id="6a44e-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

## <a name="basic-features-of-zap"></a><span data-ttu-id="6a44e-104">ZAP 的基本功能</span><span class="sxs-lookup"><span data-stu-id="6a44e-104">Basic features of ZAP</span></span>

<span data-ttu-id="6a44e-105">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，零时差差自动清除 (ZAP) 是一种电子邮件保护功能，它会被撤销地检测并忽略已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="6a44e-106">ZAP 不适用于保护本地 Exchange (的 EOP) EOP 保护的独立 Exchange Online Protection。</span><span class="sxs-lookup"><span data-stu-id="6a44e-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="6a44e-107">ZAP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="6a44e-107">How ZAP works</span></span>

<span data-ttu-id="6a44e-108">每天更新服务中的垃圾邮件和恶意软件签名。</span><span class="sxs-lookup"><span data-stu-id="6a44e-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="6a44e-109">但是，用户仍会因各种原因收到恶意邮件，包括向用户交付之后内容被简化的情况。</span><span class="sxs-lookup"><span data-stu-id="6a44e-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="6a44e-110">ZAP 通过不等监控服务中垃圾邮件和恶意软件签名的更新来解决这一问题。</span><span class="sxs-lookup"><span data-stu-id="6a44e-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="6a44e-111">ZAP 可以查找并删除用户邮箱中已有的邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="6a44e-112">ZAP 操作对于用户是无缝的;如果检测到并移动了消息，则不会通知这些消息。</span><span class="sxs-lookup"><span data-stu-id="6a44e-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="6a44e-113">[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则通常 (称为传输规则、) 件箱规则或其他筛选器的优先级高于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="6a44e-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="6a44e-114">与邮件流中发生的情况类似，这意味着，即使服务确定已传递的邮件需要 ZAP，由于安全发件人配置如何操作邮件也不会对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="6a44e-115">这是为配置邮件而跳过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="6a44e-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="6a44e-116">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="6a44e-116">Malware ZAP</span></span>

<span data-ttu-id="6a44e-117">为了 **查看或未读** 邮件，在传递后发现包含恶意软件的邮件，ZAP 会隔离包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="6a44e-118">只有管理员可以从隔离查看和管理恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="6a44e-119">在反恶意软件策略中默认启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="6a44e-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="6a44e-120">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="6a44e-121">网络钓鱼邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="6a44e-121">Phish ZAP</span></span>

<span data-ttu-id="6a44e-122">对于**在传递后识别**为钓鱼的邮件，ZAP 结果取决于针对在适用的反垃圾邮件策略中为钓鱼电子邮件筛选结定而配置的操作。 **Phishing email**</span><span class="sxs-lookup"><span data-stu-id="6a44e-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="6a44e-123">以下列表描述了适用于网络钓鱼的可用筛选谓词操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="6a44e-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="6a44e-124">**添加 X-Header** **、在主题行（带文本的前挂起**主题行）： ZAP 不对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="6a44e-125">**将邮件移动到垃圾邮件**：ZAP 将邮件移动到垃圾邮件文件夹，只要在邮箱上启用了默认启用 (就会) 。</span><span class="sxs-lookup"><span data-stu-id="6a44e-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="6a44e-126">有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="6a44e-127">**重定向邮件到电子邮件地址\*\*\*\*、删除\*\*\*\*邮件、隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="6a44e-128">默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，"网络钓鱼电子邮件筛选裁 **定** "的默认操作为" **隔离**邮件"，这意味着默认情况下，ZAP 将隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="6a44e-129">有关配置垃圾邮件筛选分析检查的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="6a44e-130">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="6a44e-130">Spam ZAP</span></span>

<span data-ttu-id="6a44e-131">对于 **在传递后** 被标识为垃圾邮件的未读邮件，ZAP 结果取决于针对适用的反 **垃圾邮件** 策略中为垃圾邮件筛选结点配置的操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="6a44e-132">以下列表介绍了垃圾邮件的可用筛选谓词操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="6a44e-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="6a44e-133">**添加 X-Header**、 **预挂起带文本的主题行**： ZAP 不对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="6a44e-134">**将邮件移动到垃圾邮件**：ZAP 将邮件移动到垃圾邮件文件夹，只要在邮箱上启用了默认启用 (就会) 。</span><span class="sxs-lookup"><span data-stu-id="6a44e-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="6a44e-135">有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="6a44e-136">**重定向邮件到电子邮件地址\*\*\*\*、删除\*\*\*\*邮件、隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="6a44e-137">最终用户可以查看和管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="6a44e-138">默认情况下，在反垃圾邮件策略中启用垃圾邮件 ZAP，垃圾邮件筛选结点的默认操作为**Spam**"将邮件移至**垃圾邮件文件夹"，** 这意味着默认情况下，垃圾邮件 ZAP 会将未读**邮件移动到"** 垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a44e-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="6a44e-139">有关配置垃圾邮件筛选分析检查的详细信息，请参阅 [在 Microsoft 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a><span data-ttu-id="6a44e-140">Office 365 ATP 中的 Office 365 高级威胁 (的 ZAP 注意事) </span><span class="sxs-lookup"><span data-stu-id="6a44e-140">ZAP considerations for Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>

<span data-ttu-id="6a44e-141">ZAP 不会隔离所有正在 [进行动态](dynamic-delivery-and-previewing.md) 传递扫描的邮件，或恶意软件筛选已将附件替换为 **恶意软件警报扫描文件Text.txt** 附件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="6a44e-142">如果收到这些邮件类型的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定被设置为对邮件 (移动至垃圾邮件、重定向、删除、隔离) 执行某些操作 (则 ZAP 将默认执行"移动到垃圾邮件"操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="6a44e-143">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="6a44e-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="6a44e-144">为确定 ZAP 是否移动了您的邮件，可使用威胁防[护状态](view-email-security-reports.md#threat-protection-status-report)报告或[威胁资源管理器 (以及实时) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="6a44e-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="6a44e-145">请注意，作为系统操作，ZAP 不会记录在 Exchange 邮箱审核日志中。</span><span class="sxs-lookup"><span data-stu-id="6a44e-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="6a44e-146">ZAP 常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6a44e-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="6a44e-147">如果将合法邮件移动到"垃圾邮件"文件夹，会怎什么？</span><span class="sxs-lookup"><span data-stu-id="6a44e-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="6a44e-148">应按照正常报告过程 [实现误报](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="6a44e-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="6a44e-149">邮件将移至垃圾邮件文件夹的唯一原因是服务已确定该邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="6a44e-150">如果我使用"隔离"文件夹而不是"垃圾邮件"文件夹，该怎办？</span><span class="sxs-lookup"><span data-stu-id="6a44e-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="6a44e-151">ZAP 将基于您在本主题前面描述的配置对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="6a44e-152">如果使用安全发件人、邮件流规则或允许/阻止的发件人名列表，该怎怎办？</span><span class="sxs-lookup"><span data-stu-id="6a44e-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="6a44e-153">安全发件人、邮件流规则或阻止和允许组织设置优先。</span><span class="sxs-lookup"><span data-stu-id="6a44e-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="6a44e-154">这些消息将从 ZAP 中排除，因为服务按你配置的任务进行操作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="6a44e-155">这是为配置邮件而跳过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="6a44e-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="6a44e-156">如果将邮件移到其他文件夹（例如收 (规则规则，该怎) ？</span><span class="sxs-lookup"><span data-stu-id="6a44e-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="6a44e-157">只要未删除消息，或者操作尚未应用，ZAP 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="6a44e-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="6a44e-158">例如，如果网络钓鱼策略设置为隔离，且用户或管理员已对电子邮件隔离垃圾邮件，那么隔离邮箱将执行隔离操作来隔离该文件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="6a44e-159">ZAP 对邮箱的保留影响是什么？</span><span class="sxs-lookup"><span data-stu-id="6a44e-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="6a44e-160">ZAP 不会从置于保留状态的邮箱中隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="6a44e-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="6a44e-161">ZAP 可以根据为反垃圾邮件策略中的垃圾邮件或网络钓鱼欺解配置的操作，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a44e-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="6a44e-162">有关 Exchange Online 中的保留的详细信息，请参阅 Exchange [Online 中的"就地保留"和"诉讼保留"。](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="6a44e-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
