---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
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
description: 零时差自动清除 (ZAP) 反作用地将 Exchange Online 邮箱中的已送达邮件移动到垃圾邮件文件夹或隔离邮箱中，在传递后被识别为垃圾邮件或网络钓鱼邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083496"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="bfbb9-103">零时差自动清除 (ZAP) 中Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bfbb9-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="bfbb9-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="bfbb9-104">**Applies to**</span></span>
- [<span data-ttu-id="bfbb9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bfbb9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bfbb9-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="bfbb9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bfbb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bfbb9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a><span data-ttu-id="bfbb9-108">零时差自动清除 (ZAP) 基础知识</span><span class="sxs-lookup"><span data-stu-id="bfbb9-108">Zero-hour auto purge (ZAP) basics</span></span>

<span data-ttu-id="bfbb9-109">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，零时差自动清除 (ZAP) 是一种电子邮件保护功能，可主动检测并消除已传递到 Exchange Online 邮箱的恶意网络钓鱼、垃圾邮件或恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="bfbb9-110">ZAP 在保护内部部署Exchange Online Protection (邮箱) 独立 EOP Exchange工作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="bfbb9-111">ZAP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="bfbb9-111">How ZAP works</span></span>

<span data-ttu-id="bfbb9-112">垃圾邮件和恶意软件签名每天在服务中实时更新。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="bfbb9-113">但是，用户仍可能会因各种原因收到恶意消息，包括内容在传送给用户后是否遭到武器化。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="bfbb9-114">ZAP 通过持续监视服务中的垃圾邮件和恶意软件签名更新来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="bfbb9-115">ZAP 可以查找和删除用户邮箱中已有的邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="bfbb9-116">ZAP 操作对于用户是无缝的;如果检测到并移动了邮件，系统不会通知他们。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="bfbb9-117">[保险箱列表、](create-safe-sender-lists-in-office-365.md)邮件流规则 (传输规则) 收件箱规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="bfbb9-118">与邮件流中发生的情况类似，这意味着即使服务确定已传递的邮件需要 ZAP，由于安全发件人配置，邮件不会处理。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="bfbb9-119">这是在配置邮件以绕过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="zero-hour-auto-purge-zap-for-malware"></a><span data-ttu-id="bfbb9-120">恶意软件的零时差 (ZAP) 清除</span><span class="sxs-lookup"><span data-stu-id="bfbb9-120">Zero-hour auto purge (ZAP) for malware</span></span>

<span data-ttu-id="bfbb9-121">对于 **在传递后** 发现包含恶意软件的已读邮件或未读邮件，ZAP 隔离包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="bfbb9-122">只有管理员可以查看和管理隔离邮件中的恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="bfbb9-123">恶意软件的 ZAP 在反恶意软件策略中默认启用。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-123">ZAP for malware is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="bfbb9-124">有关详细信息，请参阅在 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-phishing"></a><span data-ttu-id="bfbb9-125">针对网络钓鱼的零时差 (ZAP) 清除</span><span class="sxs-lookup"><span data-stu-id="bfbb9-125">Zero-hour auto purge (ZAP) for phishing</span></span>

<span data-ttu-id="bfbb9-126">对于 **在** 传递后标识为网络钓鱼的已读邮件或未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为网络钓鱼电子邮件筛选裁定配置的操作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="bfbb9-127">以下列表介绍了针对网络钓鱼的可用筛选裁定操作及其可能的 ZAP 结果：</span><span class="sxs-lookup"><span data-stu-id="bfbb9-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="bfbb9-128">**添加 X-Header** **、Prepend subject line with text** **、Redirect message to email address、Delete** **message**：ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-128">**Add X-Header**, **Prepend subject line with text**, **Redirect message to email address**, **Delete message**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="bfbb9-129">**将邮件移动到** 垃圾邮件 ：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认启用) 。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="bfbb9-130">有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="bfbb9-131">**隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-131">**Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="bfbb9-132">默认情况下，在反垃圾邮件策略中启用网络钓鱼的 ZAP，而网络钓鱼电子邮件筛选裁定的默认操作是隔离邮件，这意味着默认情况下，网络钓鱼的 ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-132">By default, ZAP for phishing is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means ZAP for phishing quarantines the message by default.</span></span>

<span data-ttu-id="bfbb9-133">有关配置垃圾邮件筛选裁定的信息，请参阅在邮件中配置[反垃圾邮件Microsoft 365。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a><span data-ttu-id="bfbb9-134">零时差自动清除 (ZAP) 高可信度网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="bfbb9-134">Zero-hour auto purge (ZAP) for high confidence phishing</span></span>

<span data-ttu-id="bfbb9-135">对于 **在传递后** 被标识为高可信度网络钓鱼的已读邮件或未读邮件，ZAP 将隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-135">For **read or unread messages** that are identified as high confidence phishing after delivery, ZAP quarantines the message.</span></span> <span data-ttu-id="bfbb9-136">只有管理员可以查看和管理隔离的高可信度钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-136">Only admins can view and manage high confidence phish messages from quarantine.</span></span>

<span data-ttu-id="bfbb9-137">默认情况下启用高可信度钓鱼邮件的 ZAP。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-137">ZAP for high confidence phish is enabled by default.</span></span> <span data-ttu-id="bfbb9-138">有关详细信息，请参阅安全[默认值Office 365。](secure-by-default.md)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-138">For more information, see [Secure by Default in Office 365](secure-by-default.md).</span></span>

### <a name="zero-hour-auto-purge-zap-for-spam"></a><span data-ttu-id="bfbb9-139">垃圾邮件的零时差 (ZAP) 清除</span><span class="sxs-lookup"><span data-stu-id="bfbb9-139">Zero-hour auto purge (ZAP) for spam</span></span>

<span data-ttu-id="bfbb9-140">对于 **在** 传递后被标识为垃圾邮件的未读邮件，ZAP 结果取决于在适用的反垃圾邮件策略中为垃圾邮件筛选裁定配置的操作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-140">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="bfbb9-141">垃圾邮件的可用筛选裁定操作及其可能的 ZAP 结果如下列表所述：</span><span class="sxs-lookup"><span data-stu-id="bfbb9-141">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="bfbb9-142">**添加 X-Header** **、Prepend subject line with text** **、Redirect message to email address、Delete** **message**：ZAP 对邮件不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-142">**Add X-Header**, **Prepend subject line with text**, **Redirect message to email address**, **Delete message**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="bfbb9-143">**将邮件移动到** 垃圾邮件 ：ZAP 将邮件移动到"垃圾邮件"文件夹，只要在邮箱上启用了垃圾邮件规则 (该规则默认启用) 。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-143">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="bfbb9-144">有关详细信息，请参阅 Configure [junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-144">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="bfbb9-145">**隔离邮件**：ZAP 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-145">**Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="bfbb9-146">最终用户可以查看和管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-146">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="bfbb9-147">默认情况下，反垃圾邮件策略中已启用垃圾邮件 ZAP，垃圾邮件筛选裁定的默认操作是"将邮件移动到垃圾邮件文件夹"，这意味着默认情况下，垃圾邮件 ZAP 会将未读邮件移动到"垃圾邮件"文件夹。 </span><span class="sxs-lookup"><span data-stu-id="bfbb9-147">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="bfbb9-148">有关配置垃圾邮件筛选裁定的信息，请参阅在邮件中配置[反垃圾邮件Microsoft 365。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-148">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="bfbb9-149">零时差自动清除 (ZAP) Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="bfbb9-149">Zero-hour auto purge (ZAP) considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="bfbb9-150">ZAP 不会隔离正在 保险箱 附件扫描中动态传递 [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)的任何邮件，或者 EOP 恶意软件筛选已使用恶意软件警报文件替换附件 **Text.txt邮件。**</span><span class="sxs-lookup"><span data-stu-id="bfbb9-150">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="bfbb9-151">如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且反垃圾邮件策略中的筛选裁定设置为对邮件 (Move to Junk， Redirect， Delete， or Quarantine) 则 ZAP 将默认为"移动到垃圾邮件"操作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-151">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="bfbb9-152">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="bfbb9-152">How to see if ZAP moved your message</span></span>

<span data-ttu-id="bfbb9-153">若要确定 ZAP 是否移动了邮件，可以使用威胁防护[](view-email-security-reports.md#threat-protection-status-report)状态报告或威胁资源管理器 (和实时检测[) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-153">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="bfbb9-154">请注意，作为系统操作，ZAP 不会记录在Exchange审核日志中。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-154">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zero-hour-auto-purge-zap-faq"></a><span data-ttu-id="bfbb9-155">零时差自动清除 (ZAP) FAQ</span><span class="sxs-lookup"><span data-stu-id="bfbb9-155">Zero-hour auto purge (ZAP) FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="bfbb9-156">如果将合法邮件移动到"垃圾邮件"文件夹，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-156">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="bfbb9-157">你应该遵循误报的正常 [报告过程](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-157">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="bfbb9-158">邮件从"收件箱"移动到"垃圾邮件"文件夹的唯一原因是服务已确定该邮件是垃圾邮件或恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-158">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="bfbb9-159">如果我使用隔离文件夹而不是垃圾邮件文件夹，应该怎么做？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-159">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="bfbb9-160">ZAP 将基于反垃圾邮件策略的配置对邮件采取措施，如本文前面所述。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-160">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="bfbb9-161">如果我使用安全发件人、邮件流规则或允许/阻止的发件人列表，该做什么？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-161">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="bfbb9-162">保险箱发件人、邮件流规则或阻止和允许组织设置优先。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-162">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="bfbb9-163">这些消息从 ZAP 中排除，因为服务正在执行你配置它所执行的工作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-163">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="bfbb9-164">这是在配置邮件以绕过筛选时要谨慎的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-164">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a><span data-ttu-id="bfbb9-165">ZAP (零时差自动清除) 要求是什么？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-165">What are the licensing Requirements for Zero-hour auto purge (ZAP) to work?</span></span>

<span data-ttu-id="bfbb9-166">对许可证没有限制。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-166">There are no limitations on licenses.</span></span> <span data-ttu-id="bfbb9-167">ZAP 适用于联机邮箱上托管Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-167">ZAP works on all mailboxes hosted on Exchange online.</span></span> <span data-ttu-id="bfbb9-168">ZAP 在保护内部部署Exchange Online Protection (邮箱) 独立 EOP Exchange工作。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-168">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="bfbb9-169">如果将邮件移动到其他文件夹（例如收件箱规则 (，) ？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-169">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="bfbb9-170">只要邮件尚未删除，或者只要尚未应用相同或更强的操作，零时差自动清除仍有效。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-170">Zero-hour auto purge still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="bfbb9-171">例如，如果反网络钓鱼策略设置为隔离，并且邮件已位于垃圾邮件中，则 ZAP 将采取措施隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-171">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="bfbb9-172">ZAP 对保留的邮箱有何影响？</span><span class="sxs-lookup"><span data-stu-id="bfbb9-172">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="bfbb9-173">零时差自动清除将隔离来自保留邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-173">Zero-hour auto purge will quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="bfbb9-174">ZAP 可以基于为反垃圾邮件策略中的垃圾邮件或网络钓鱼裁定配置的操作，将邮件移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="bfbb9-174">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="bfbb9-175">有关用户中的保留Exchange Online，请参阅 Exchange Online[中的就地保留和诉讼Exchange Online。](/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="bfbb9-175">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
