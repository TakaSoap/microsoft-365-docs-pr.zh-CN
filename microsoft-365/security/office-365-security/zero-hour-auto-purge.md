---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
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
description: 零小时自动清除（ZAP）是一种电子邮件保护功能，可检测到已发送到用户收件箱的垃圾邮件或恶意软件的邮件，然后将恶意内容无害。 ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: 3a888e6a6b4de57efcb0a8b8284432a2b9f1095a
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971380"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="55db2-104">零时差自动清除 - 防范垃圾邮件和恶意软件</span><span class="sxs-lookup"><span data-stu-id="55db2-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="55db2-105">概述</span><span class="sxs-lookup"><span data-stu-id="55db2-105">Overview</span></span>

<span data-ttu-id="55db2-106">零小时自动清除（ZAP）是一种电子邮件保护功能，可检测到已传递给用户的收件箱的包含网络钓鱼、垃圾邮件或恶意软件的邮件，然后将恶意内容无害。</span><span class="sxs-lookup"><span data-stu-id="55db2-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="55db2-107">ZAP 的工作方式取决于检测到的恶意内容的类型。</span><span class="sxs-lookup"><span data-stu-id="55db2-107">How ZAP does this depends on the type of malicious content detected.</span></span> <span data-ttu-id="55db2-108">由于邮件内容、Url 或附件，邮件可能会 zapped。</span><span class="sxs-lookup"><span data-stu-id="55db2-108">Mail can be zapped due to mail content, URLs, or attachments.</span></span>

<span data-ttu-id="55db2-109">ZAP 可与包含 Exchange Online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online 保护一起使用。</span><span class="sxs-lookup"><span data-stu-id="55db2-109">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="55db2-110">ZAP 的工作方式</span><span class="sxs-lookup"><span data-stu-id="55db2-110">How ZAP works</span></span>

<span data-ttu-id="55db2-111">Office 365 每天实时更新反垃圾邮件引擎和恶意软件签名。</span><span class="sxs-lookup"><span data-stu-id="55db2-111">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="55db2-112">但是，用户仍可能会因各种原因而将恶意邮件传递到其收件箱，其中包括在将内容传递给用户后 weaponized 内容。</span><span class="sxs-lookup"><span data-stu-id="55db2-112">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="55db2-113">ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此情况。</span><span class="sxs-lookup"><span data-stu-id="55db2-113">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="55db2-114">ZAP 可查找并删除已在用户收件箱中的以前传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="55db2-114">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="55db2-115">对于邮箱用户，ZAP 操作是无缝的;如果移动电子邮件，则不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="55db2-115">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="55db2-116">消息不得早于2天。</span><span class="sxs-lookup"><span data-stu-id="55db2-116">Message must not be older than 2 days.</span></span>

<span data-ttu-id="55db2-117">允许列表、[邮件流规则](use-transport-rules-to-configure-bulk-email-filtering.md)（也称为传输规则）和最终用户规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-117">Allow lists, [mail flow rules](use-transport-rules-to-configure-bulk-email-filtering.md) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="55db2-118">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="55db2-118">Malware ZAP</span></span>

<span data-ttu-id="55db2-119">对于新检测到的恶意软件，ZAP 会将整个邮件（包括其附件）移动到恶意软件隔离中。</span><span class="sxs-lookup"><span data-stu-id="55db2-119">For newly detected malware, ZAP moves the entire message, including its attachment, to malware Quarantine.</span></span> <span data-ttu-id="55db2-120">无论邮件的阅读状态如何，都会移动邮件。</span><span class="sxs-lookup"><span data-stu-id="55db2-120">Messages are moved regardless of the read status of the mail.</span></span> <span data-ttu-id="55db2-121">如果我们在动态传递扫描过程中收到邮件的恶意软件信号，则 ZAP 将对邮件执行 "移动到垃圾邮件" 操作。</span><span class="sxs-lookup"><span data-stu-id="55db2-121">If we get a malware signal for a message in the process of Dynamic Delivery scanning, ZAP will take a Move to Junk action on the message.</span></span> <span data-ttu-id="55db2-122">然后，它将允许动态传递，以完成传递扫描的时间并采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="55db2-122">Then it will allow Dynamic Delivery to finish the Time of Delivery scanning and take the appropriate action.</span></span>

<span data-ttu-id="55db2-123">在恶意软件策略中，默认情况下会启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-123">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="55db2-124">您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet 上的*ZapEnabled*参数禁用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-124">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="55db2-125">还可以通过编辑安全与合规中心中的恶意软件策略来启用或禁用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-125">Malware ZAP can also be enabled or disabled by editing the Malware Policy in the Security and Compliance Center.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="55db2-126">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="55db2-126">Phish ZAP</span></span>

<span data-ttu-id="55db2-127">对于在传递后被标识为网络钓鱼的邮件，ZAP 将根据覆盖特定用户的垃圾邮件策略执行操作，而不考虑邮件的阅读状态。</span><span class="sxs-lookup"><span data-stu-id="55db2-127">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that covers a specific user, regardless of the read status of the mail.</span></span> <span data-ttu-id="55db2-128">如果将策略网络钓鱼操作设置为*不*执行操作（添加 X 标头、修改 Subject、无操作），则 ZAP 不会对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="55db2-128">If the policy Phish action is set to *not* take action (Add X-header, Modify subject, No action) then ZAP will not take any action on the mail.</span></span> <span data-ttu-id="55db2-129">如果将网络钓鱼操作设置为移动到垃圾邮件，则 ZAP 会将邮件移动到用户收件箱的 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55db2-129">If the Phish action is set to Move to Junk then ZAP will move the message to the Junk mail folder of the user's inbox.</span></span> <span data-ttu-id="55db2-130">**对于任何其他网络钓鱼操作（重定向、删除、隔离），ZAP 都会将邮件移动到网络钓鱼隔离**。</span><span class="sxs-lookup"><span data-stu-id="55db2-130">**For any other Phish action (Redirect, Delete, Quarantine) ZAP will move the message to phish Quarantine**.</span></span> <span data-ttu-id="55db2-131">请阅读下面的配置要求和排除项。</span><span class="sxs-lookup"><span data-stu-id="55db2-131">Read below for configuration requirements and exclusions.</span></span> <span data-ttu-id="55db2-132">了解有关如何在此处[配置垃圾邮件筛选器策略](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55db2-132">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="55db2-133">默认情况下，会在垃圾邮件策略中启用网络钓鱼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-133">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="55db2-134">可以使用[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)的*PHISHZAPENABLED*参数（EOP cmdlet）禁用网络钓鱼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-134">Phish ZAP can be disabled using the *PhishZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), an EOP cmdlet.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="55db2-135">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="55db2-135">Spam ZAP</span></span>

<span data-ttu-id="55db2-136">对于在传递后被标识为垃圾邮件的邮件，ZAP 将根据覆盖特定用户的垃圾邮件策略执行操作，只有在邮件未读时才会执行。</span><span class="sxs-lookup"><span data-stu-id="55db2-136">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that covers the specific user, only if the message is unread.</span></span>  <span data-ttu-id="55db2-137">如果 "策略垃圾邮件" 操作设置为 "不执行操作（添加 X 标头，修改主题，无操作）"，则 ZAP 不会对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="55db2-137">If the policy Spam action is set to not take action (Add X-header, Modify subject, No action) then ZAP won't take any action on the mail.</span></span> <span data-ttu-id="55db2-138">如果垃圾邮件操作设置为移至垃圾邮件，则 ZAP 会将邮件移动到用户收件箱的 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55db2-138">If the Spam action is set to Move to Junk then ZAP will move the message to the Junk mail folder of the user's inbox.</span></span> <span data-ttu-id="55db2-139">**对于任何其他垃圾邮件操作（重定向、删除、隔离） ZAP，都会将邮件移动到垃圾邮件隔离**。</span><span class="sxs-lookup"><span data-stu-id="55db2-139">**For any other Spam action (Redirect, Delete, Quarantine) ZAP will move the message to spam Quarantine**.</span></span> <span data-ttu-id="55db2-140">请阅读下面的配置要求和排除项。</span><span class="sxs-lookup"><span data-stu-id="55db2-140">Read below for configuration requirements and exclusions.</span></span> <span data-ttu-id="55db2-141">了解有关如何在此处[配置垃圾邮件筛选器策略](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55db2-141">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="55db2-142">垃圾邮件策略中默认启用垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-142">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="55db2-143">您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) Cmdlet 的*SpamZapEnabled*参数禁用垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-143">You can disable Spam ZAP by using the *SpamZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a><span data-ttu-id="55db2-144">网络钓鱼和垃圾邮件 ZAP 要求、排除和通知</span><span class="sxs-lookup"><span data-stu-id="55db2-144">Phish and Spam ZAP requirements, exclusions, and notices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55db2-145">以前的*ZapEnabled* cmdlet 参数控制了网络钓鱼和垃圾邮件 ZAP 将**弃用2020年2月1日**。</span><span class="sxs-lookup"><span data-stu-id="55db2-145">the previous *ZapEnabled* cmdlet parameter which controlled both Phish and Spam ZAP will be **deprecated February 1, 2020**.</span></span> <span data-ttu-id="55db2-146">如果你已编写使用 ZapEnabled 参数的任何脚本，我们建议将其更新为使用 SpamZapEnabled 和 PhishZapEnabled。</span><span class="sxs-lookup"><span data-stu-id="55db2-146">If you have written any scripts which use the ZapEnabled parameter, we recommend updating them to use SpamZapEnabled and PhishZapEnabled.</span></span> <span data-ttu-id="55db2-147">在过渡期内，所有3个参数（ZapEnabled、PhishZapEnabled 和 SpamZapEnabled）都将通过 cmdlet 提供。</span><span class="sxs-lookup"><span data-stu-id="55db2-147">In the transitional period all 3 parameters (ZapEnabled, PhishZapEnabled, and SpamZapEnabled) will be available through the cmdlet.</span></span> <span data-ttu-id="55db2-148">在通过 UI 或 PowerShell 显式设置之前，PhishZapEnabled 和 SpamZapEnabled 将显示 ZapEnabled 参数中的继承值。</span><span class="sxs-lookup"><span data-stu-id="55db2-148">Until explicitly set via UI or PowerShell, PhishZapEnabled and SpamZapEnabled will show an inherited value from the ZapEnabled parameter.</span></span> <span data-ttu-id="55db2-149">一旦设置了新参数，它们就不再从 ZapEnabled 参数继承。</span><span class="sxs-lookup"><span data-stu-id="55db2-149">Once the new parameters are set, they will no longer inherit from the ZapEnabled parameter.</span></span> <span data-ttu-id="55db2-150">弃用后设置 ZapEnabled 将对 PhishZapEnabled 或 SpamZapEnabled 属性没有任何影响，ZapEnabled 将从 cmdlet 中的参数列表中删除。</span><span class="sxs-lookup"><span data-stu-id="55db2-150">After it is deprecated setting ZapEnabled will have no affect on the PhishZapEnabled or SpamZapEnabled properties and ZapEnabled will be removed from the list of parameters in cmdlets.</span></span>

<span data-ttu-id="55db2-151">ZAP 不会将任何邮件移动到正在进行动态传递扫描的隔离中，或已使用替换的附件判定为恶意软件。</span><span class="sxs-lookup"><span data-stu-id="55db2-151">ZAP will not move any message to Quarantine which is in the process of Dynamic Delivery scanning, or which already has a Malware verdict with a replaced attachment.</span></span> <span data-ttu-id="55db2-152">如果收到这些类型的邮件的网络钓鱼或垃圾邮件信号，并且垃圾邮件策略/网络钓鱼操作设置为执行某些操作（移动到垃圾邮件、重定向、删除、隔离），则 ZAP 将默认为 "移动到垃圾邮件" 操作。</span><span class="sxs-lookup"><span data-stu-id="55db2-152">If a phish or spam signal is received for these types of messages and the Spam policy / Phish action is set to take some action (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span> <span data-ttu-id="55db2-153">对于对邮件执行 "移动到垃圾邮件" 操作的 ZAP，用户必须启用其垃圾邮件保护，并使用默认的 "垃圾邮件" 设置。</span><span class="sxs-lookup"><span data-stu-id="55db2-153">For ZAP to take a 'Move to Junk' action on a message, the user must have their junk email protection enabled, with the default junk mail settings.</span></span> <span data-ttu-id="55db2-154">（有关 Outlook 中用户选项的详细信息，请参阅[更改垃圾邮件筛选器中的保护级别](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。）</span><span class="sxs-lookup"><span data-stu-id="55db2-154">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="55db2-155">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="55db2-155">How to see if ZAP moved your message</span></span>

<span data-ttu-id="55db2-156">若要确定 ZAP 是否移动了邮件，可以使用[威胁防护状态报告](../../compliance/view-email-security-reports.md#threat-protection-status-report)或[威胁浏览器（和实时检测）](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="55db2-156">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="55db2-157">禁用 ZAP</span><span class="sxs-lookup"><span data-stu-id="55db2-157">Disable ZAP</span></span>

<span data-ttu-id="55db2-158">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55db2-158">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="55db2-159">若要连接到 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55db2-159">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="55db2-160">禁用恶意软件 ZAP \* \*</span><span class="sxs-lookup"><span data-stu-id="55db2-160">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="55db2-161">可以通过 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet 上的*ZapEnabled*参数禁用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-161">Malware ZAP can be disabled through the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="55db2-162">还可以通过编辑安全与合规中心中的恶意软件策略来启用或禁用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-162">Malware ZAP can also be enabled or disabled by editing the Malware Policy in the Security and Compliance Center.</span></span>

<span data-ttu-id="55db2-163">此示例在名为 "Test" 的恶意软件筛选器策略中禁用 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-163">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="55db2-164">有关语法和参数的详细信息，请参阅[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="55db2-164">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="55db2-165">禁用网络钓鱼 ZAP 和垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="55db2-165">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="55db2-166">若要禁用 O365 租户的网络钓鱼和垃圾邮件 ZAP 或一组用户，请使用[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)的 EOP Cmdlet 的*PhishZapEnabled*和*SpamZapEnabled*参数。</span><span class="sxs-lookup"><span data-stu-id="55db2-166">To disable Phish and Spam ZAP for your O365 tenant, or a set of users, use the *PhishZapEnabled* and *SpamZapEnabled* parameters of [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), an EOP cmdlet.</span></span>

<span data-ttu-id="55db2-167">在下面的示例中，对名为 "Test" 的内容筛选器策略禁用了网络钓鱼和垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="55db2-167">In the following example, phish and spam ZAP are disabled for a content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

<span data-ttu-id="55db2-168">有关语法和参数的详细信息，请参阅[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)。</span><span class="sxs-lookup"><span data-stu-id="55db2-168">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).</span></span>

## <a name="faq"></a><span data-ttu-id="55db2-169">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="55db2-169">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="55db2-170">如果将合法邮件移动到 "垃圾邮件" 文件夹中，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="55db2-170">What happens if a legitimate message is moved to the junk mail folder?</span></span>

<span data-ttu-id="55db2-171">您应遵循正常的报告过程[假阳性](../../compliance/prevent-email-from-being-marked-as-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="55db2-171">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="55db2-172">将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是，该服务已确定邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="55db2-172">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="55db2-173">如果我使用的是 Office 365 隔离，而不是垃圾邮件文件夹，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="55db2-173">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>

<span data-ttu-id="55db2-174">ZAP 将根据反垃圾邮件策略中的网络钓鱼和垃圾邮件操作设置的配置执行操作。</span><span class="sxs-lookup"><span data-stu-id="55db2-174">ZAP will take action according to the configuration of the Phish and Spam action settings in your Anti-spam policy.</span></span> <span data-ttu-id="55db2-175">有关恶意软件、网络钓鱼和垃圾邮件 ZAP 的更多详细信息，请参阅上文。</span><span class="sxs-lookup"><span data-stu-id="55db2-175">See above for more details on Malware, Phish, and Spam ZAP.</span></span>

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="55db2-176">如果我有自定义邮件流规则（阻止/允许规则），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="55db2-176">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>

<span data-ttu-id="55db2-177">由管理员（邮件流规则）或阻止和允许规则创建的规则优先。</span><span class="sxs-lookup"><span data-stu-id="55db2-177">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="55db2-178">将从功能条件中排除此类邮件，以便邮件流遵循规则操作（阻止/允许规则）。</span><span class="sxs-lookup"><span data-stu-id="55db2-178">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="55db2-179">如果邮件被移到另一个文件夹（例如收件箱规则），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="55db2-179">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="55db2-180">在这种情况下，ZAP 仍适用，除非邮件已被删除或在垃圾邮件中。</span><span class="sxs-lookup"><span data-stu-id="55db2-180">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="55db2-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="55db2-181">Related Topics</span></span>

[<span data-ttu-id="55db2-182">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="55db2-182">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="55db2-183">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="55db2-183">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
