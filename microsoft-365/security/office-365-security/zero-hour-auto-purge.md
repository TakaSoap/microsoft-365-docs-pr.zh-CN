---
title: '零时差自动清除 (ZAP) '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理员可以了解零时差自动清除 (ZAP) 如何以反向方式将 Exchange Online 邮箱中传递的邮件移动到垃圾邮件文件夹或被反向发现为垃圾邮件或网络钓鱼的隔离邮箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287301"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="0b45e-103">Exchange Online 中的 ZAP (零) 清除</span><span class="sxs-lookup"><span data-stu-id="0b45e-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="0b45e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0b45e-104">**Applies to**</span></span>
- [<span data-ttu-id="0b45e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b45e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b45e-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="0b45e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0b45e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b45e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="0b45e-108">ZAP 的基本功能</span><span class="sxs-lookup"><span data-stu-id="0b45e-108">Basic features of ZAP</span></span>

<span data-ttu-id="0b45e-109">在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，零时差自动清除 (ZAP) 是一种电子邮件保护功能，可反向检测和消除已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="0b45e-110">ZAP 在保护本地 Exchange 邮箱的独立 Exchange Online Protection (EOP) 环境中不起作用。</span><span class="sxs-lookup"><span data-stu-id="0b45e-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="0b45e-111">ZAP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="0b45e-111">How ZAP works</span></span>

<span data-ttu-id="0b45e-112">垃圾邮件和恶意软件签名每天在服务中实时更新。</span><span class="sxs-lookup"><span data-stu-id="0b45e-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="0b45e-113">但是，由于各种原因，用户仍可能会收到恶意消息，包括内容在传递给用户后是否遭到武器化。</span><span class="sxs-lookup"><span data-stu-id="0b45e-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="0b45e-114">ZAP 通过持续监视服务中垃圾邮件和恶意软件签名的更新来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="0b45e-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="0b45e-115">ZAP 可以查找和删除用户邮箱中已有的邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="0b45e-116">ZAP 操作对于用户是无缝的;如果检测到并移动了邮件，则系统不会通知他们。</span><span class="sxs-lookup"><span data-stu-id="0b45e-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="0b45e-117">[安全发件人列表](create-safe-sender-lists-in-office-365.md)、邮件流规则 (也称为传输规则) 、收件箱规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="0b45e-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="0b45e-118">与邮件流中发生的情况类似，这意味着即使服务确定已传递的邮件需要 ZAP，邮件不会因安全发件人配置而运行。</span><span class="sxs-lookup"><span data-stu-id="0b45e-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="0b45e-119">这是在配置邮件以绕过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="0b45e-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="0b45e-120">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="0b45e-120">Malware ZAP</span></span>

<span data-ttu-id="0b45e-121">对于 **在传递** 后发现包含恶意软件的已读邮件或未读邮件，ZAP 隔离包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="0b45e-122">只有管理员可以查看和管理隔离邮件中的恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="0b45e-123">反恶意软件策略中默认启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="0b45e-123">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="0b45e-124">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b45e-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="0b45e-125">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="0b45e-125">Phish ZAP</span></span>

<span data-ttu-id="0b45e-126">对于 **在** 传递后被标识为网络钓鱼的已读邮件或未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为网络钓鱼电子邮件筛选裁定配置的操作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="0b45e-127">以下列表介绍了适用于网络钓鱼的可用筛选裁定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="0b45e-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="0b45e-128">**添加 X-Header，** 使用文本附加主题 **行**：ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-128">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="0b45e-129">**将邮件** 移动到"垃圾邮件"：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认) 。</span><span class="sxs-lookup"><span data-stu-id="0b45e-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="0b45e-130">有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="0b45e-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="0b45e-131">**将邮件重定向到电子邮件地址**，**删除邮件\*\*\*\*，隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-131">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="0b45e-132">默认情况下，在反垃圾邮件策略中启用网络钓鱼 ZAP，网络钓鱼电子邮件筛选裁定的默认操作是隔离邮件，这意味着默认情况下，网络钓鱼 ZAP 会隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-132">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="0b45e-133">有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft [365](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="0b45e-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="0b45e-134">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="0b45e-134">Spam ZAP</span></span>

<span data-ttu-id="0b45e-135">对于 **在** 传递后被标识为垃圾邮件的未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为垃圾邮件筛选裁定配置的操作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-135">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="0b45e-136">以下列表介绍了垃圾邮件的可用筛选裁定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="0b45e-136">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="0b45e-137">**添加 X-Header，** 使用文本附加主题 **行**：ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-137">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="0b45e-138">**将邮件** 移动到"垃圾邮件"：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认) 。</span><span class="sxs-lookup"><span data-stu-id="0b45e-138">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="0b45e-139">有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="0b45e-139">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="0b45e-140">**将邮件重定向到电子邮件地址**，**删除邮件\*\*\*\*，隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-140">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="0b45e-141">最终用户可以查看和管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-141">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="0b45e-142">默认情况下，反垃圾邮件策略中启用垃圾邮件 ZAP，垃圾邮件筛选裁定的默认操作是"将邮件移动到垃圾邮件"文件夹，这意味着垃圾邮件 ZAP 默认情况下会将未读邮件移动到"垃圾邮件"文件夹。 </span><span class="sxs-lookup"><span data-stu-id="0b45e-142">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="0b45e-143">有关配置垃圾邮件筛选裁定的信息，请参阅在 Microsoft [365](configure-your-spam-filter-policies.md)中配置反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="0b45e-143">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="0b45e-144">适用于 Office 365 的 Microsoft Defender 的 ZAP 注意事项</span><span class="sxs-lookup"><span data-stu-id="0b45e-144">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0b45e-145">ZAP 不会隔离安全附件扫描中的动态传递过程中的任何邮件 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)，或者 EOP 恶意软件筛选已用恶意软件警报文件替换附件 **Text.txt邮件。**</span><span class="sxs-lookup"><span data-stu-id="0b45e-145">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="0b45e-146">如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定设置为对邮件 (移动到垃圾邮件、重定向、删除或隔离) 采取一些操作，则 ZAP 将默认为"移动到垃圾邮件"操作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-146">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="0b45e-147">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="0b45e-147">How to see if ZAP moved your message</span></span>

<span data-ttu-id="0b45e-148">若要确定 ZAP 是否移动了邮件，可以使用威胁防护[](view-email-security-reports.md#threat-protection-status-report)状态报告或威胁资源管理器 (实时检测[) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="0b45e-148">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="0b45e-149">请注意，作为系统操作，ZAP 不会记录在 Exchange 邮箱审核日志中。</span><span class="sxs-lookup"><span data-stu-id="0b45e-149">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="0b45e-150">ZAP 常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0b45e-150">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="0b45e-151">如果合法邮件移至"垃圾邮件"文件夹，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="0b45e-151">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="0b45e-152">你应该遵循误报的正常 [报告过程](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="0b45e-152">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="0b45e-153">邮件从收件箱移动到垃圾邮件文件夹的唯一原因是服务已确定邮件是垃圾邮件或恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-153">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="0b45e-154">如果我使用"隔离"文件夹而不是"垃圾邮件"文件夹，应该怎么做？</span><span class="sxs-lookup"><span data-stu-id="0b45e-154">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="0b45e-155">ZAP 将基于反垃圾邮件策略的配置对邮件采取措施，如本文前面所述。</span><span class="sxs-lookup"><span data-stu-id="0b45e-155">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="0b45e-156">如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该做什么？</span><span class="sxs-lookup"><span data-stu-id="0b45e-156">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="0b45e-157">安全发件人、邮件流规则或阻止和允许组织设置优先。</span><span class="sxs-lookup"><span data-stu-id="0b45e-157">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="0b45e-158">这些消息从 ZAP 中排除，因为服务正在执行你配置它要执行的工作。</span><span class="sxs-lookup"><span data-stu-id="0b45e-158">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="0b45e-159">这是在配置邮件以绕过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="0b45e-159">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="0b45e-160">如果邮件移动到其他文件夹，例如 (收件箱规则，) ？</span><span class="sxs-lookup"><span data-stu-id="0b45e-160">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="0b45e-161">只要邮件尚未删除，或者尚未应用相同或更强的操作，ZAP 仍有效。</span><span class="sxs-lookup"><span data-stu-id="0b45e-161">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="0b45e-162">例如，如果反网络钓鱼策略设置为隔离，并且邮件已位于垃圾邮件中，则 ZAP 将采取措施隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-162">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="0b45e-163">ZAP 如何影响保留的邮箱？</span><span class="sxs-lookup"><span data-stu-id="0b45e-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="0b45e-164">ZAP 不会隔离来自保留邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="0b45e-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="0b45e-165">ZAP 可以基于为反垃圾邮件策略中的垃圾邮件或网络钓鱼裁定配置的操作，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="0b45e-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="0b45e-166">有关 Exchange Online 中的保留内容，请参阅 Exchange Online 中的就 [地保留和诉讼保留](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。</span><span class="sxs-lookup"><span data-stu-id="0b45e-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
