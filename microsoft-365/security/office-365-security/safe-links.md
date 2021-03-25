---
title: 安全链接
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 在本文中，管理员可以了解 Defender for Office 365 中的安全链接保护，以保护其组织免受网络钓鱼和使用恶意 URL 的其他攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ec3ab1a255e9eaa8c190ed5c248c9587273e03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203842"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9343d-103">Microsoft Defender for Office 365 中的安全链接</span><span class="sxs-lookup"><span data-stu-id="9343d-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9343d-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9343d-104">**Applies to**</span></span>
- [<span data-ttu-id="9343d-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9343d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9343d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9343d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="9343d-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="9343d-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="9343d-108">如果你使用的是 Outlook.com、Microsoft 365 家庭版或 Microsoft 365 个人版，并且正在查找有关 Outlook 中安全链接的信息，请参阅高级安全[Outlook.com。](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="9343d-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9343d-109">安全链接是 Defender [for Office 365](defender-for-office-365.md) 中的一项功能，它提供邮件流中入站电子邮件的 URL 扫描和重写，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="9343d-109">Safe Links is a feature in [Defender for Office 365](defender-for-office-365.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="9343d-110">除了 Exchange Online Protection ([](anti-spam-and-anti-malware-protection.md) EOP 策略中的入站电子邮件中的常规反垃圾邮件和反恶意软件保护外，安全链接扫描) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="9343d-111">安全链接扫描可帮助保护组织免受钓鱼和其他攻击中使用的恶意链接的攻击。</span><span class="sxs-lookup"><span data-stu-id="9343d-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="9343d-112">安全链接保护可在以下位置使用：</span><span class="sxs-lookup"><span data-stu-id="9343d-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="9343d-113">**电子邮件：** 电子邮件中链接的安全链接保护由安全链接策略控制。</span><span class="sxs-lookup"><span data-stu-id="9343d-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="9343d-114">没有默认的安全链接策略，因此若要保护电子邮件中的安全链接，需要创建一 **个或多个安全链接策略**。</span><span class="sxs-lookup"><span data-stu-id="9343d-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="9343d-115">有关说明，请参阅在 [Microsoft Defender for Office 365](set-up-safe-links-policies.md)中设置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="9343d-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

  <span data-ttu-id="9343d-116">有关电子邮件的安全链接保护详细信息，请参阅本文稍后介绍的电子邮件的安全[](#safe-links-settings-for-email-messages)链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="9343d-117">**Microsoft Teams** (TAP Preview) ：Teams 对话、群聊或频道中的链接的安全链接保护也由安全链接策略控制。</span><span class="sxs-lookup"><span data-stu-id="9343d-117">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="9343d-118">没有默认的安全链接策略，因此若要在 Teams 中保护安全链接，需要创建一个或多个安全 **链接策略**。</span><span class="sxs-lookup"><span data-stu-id="9343d-118">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="9343d-119">有关 Teams 中的安全链接保护详细信息，请参阅本文稍后介绍 [的 Microsoft Teams](#safe-links-settings-for-microsoft-teams) 安全链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-119">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="9343d-120">**Office 365 应用**：Office 365 应用的安全链接保护在受支持的桌面、移动和 Web aps 中可用。</span><span class="sxs-lookup"><span data-stu-id="9343d-120">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="9343d-121">在 **安全** 链接策略之外的全局设置中为 Office 365 应用配置安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-121">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="9343d-122">有关说明，请参阅 [为 Microsoft Defender for Office 365 中的安全链接设置配置全局设置](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="9343d-122">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="9343d-123">但是，Office 365 应用的安全链接保护仅适用于活动安全链接策略中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="9343d-123">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="9343d-124">如果用户未包含在活动安全链接策略中，则用户不会在受支持的 Office 365 应用中获得安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-124">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="9343d-125">有关 Office 365 应用中安全链接保护详细信息，请参阅本文稍后介绍 [的 Office 365](#safe-links-settings-for-office-365-apps) 应用的安全链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="9343d-126">本文包含以下安全链接设置的详细说明：</span><span class="sxs-lookup"><span data-stu-id="9343d-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="9343d-127">**安全链接策略中的** 设置：这些设置仅适用于特定策略中包含的用户，并且策略之间的设置可能不同。</span><span class="sxs-lookup"><span data-stu-id="9343d-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="9343d-128">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="9343d-128">These settings include:</span></span>

  - [<span data-ttu-id="9343d-129">电子邮件的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="9343d-130">Microsoft Teams 的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="9343d-131">安全链接策略中的"不重写以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="9343d-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="9343d-132">**全局安全链接设置**：这些设置是全局配置的，而不是在安全链接策略中配置的。</span><span class="sxs-lookup"><span data-stu-id="9343d-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="9343d-133">但是，这些设置仅适用于活动安全链接策略中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="9343d-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="9343d-134">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="9343d-134">These settings include:</span></span>

  - [<span data-ttu-id="9343d-135">Office 365 应用的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="9343d-136">安全链接的"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="9343d-136">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="9343d-137">下表介绍了 Microsoft 365 和 Office 365 组织中安全链接的方案，其中包括 Defender for Office 365 (换句话说，缺少许可在示例) 中永远不会是问题。</span><span class="sxs-lookup"><span data-stu-id="9343d-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="9343d-138">方案</span><span class="sxs-lookup"><span data-stu-id="9343d-138">Scenario</span></span>|<span data-ttu-id="9343d-139">结果</span><span class="sxs-lookup"><span data-stu-id="9343d-139">Result</span></span>|
|---|---|
|<span data-ttu-id="9343d-140">表示是市场营销部门的成员。</span><span class="sxs-lookup"><span data-stu-id="9343d-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="9343d-141">Office 365 应用的安全链接保护在安全链接的全局设置中打开，并且存在适用于市场营销部门成员的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="9343d-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="9343d-142">在电子邮件中打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="9343d-143">百分之百受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="9343d-144">Office 365 应用的安全链接保护包含在安全链接策略中，且 Office 365 应用的安全链接保护已打开。</span><span class="sxs-lookup"><span data-stu-id="9343d-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="9343d-145">有关 Office 365 应用中安全链接保护的要求详细信息，请参阅本文稍后介绍 [的 Office 365](#safe-links-settings-for-office-365-apps) 应用的安全链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="9343d-146">Chris 的 Microsoft 365 E5 组织未配置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="9343d-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="9343d-147">Chris 从外部发件人收到一封电子邮件，其中包含他最终单击的恶意网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="9343d-148">Chris 不受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="9343d-149">管理员必须至少为任何人创建一个安全链接策略，才能在入站电子邮件中获得安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="9343d-150">Chris 必须包含在策略条件中才能获得安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="9343d-151">在 Pat 的组织中，管理员未创建任何安全链接策略，但 Office 365 应用的安全链接保护已打开。</span><span class="sxs-lookup"><span data-stu-id="9343d-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="9343d-152">Pat 打开 Word 文档并单击该文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="9343d-153">Pat 不受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="9343d-154">尽管 Office 365 应用的安全链接保护已全局打开，但 Pat 未包含在任何活动的安全链接策略中，因此无法应用保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="9343d-155">在 Lee 的组织中，在安全链接的全局设置中的"阻止以下 `https://tailspintoys.com` **URL"** 列表中进行配置。</span><span class="sxs-lookup"><span data-stu-id="9343d-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="9343d-156">包含 Lee 的安全链接策略已存在。</span><span class="sxs-lookup"><span data-stu-id="9343d-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="9343d-157">Lee 收到一封包含 URL 的电子邮件 `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="9343d-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="9343d-158">Lee 单击 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-158">Lee clicks the URL.</span></span>|<span data-ttu-id="9343d-159">可能为 Lee 自动阻止 URL;这取决于列表中的 URL 条目和所使用的电子邮件客户端 Lee。</span><span class="sxs-lookup"><span data-stu-id="9343d-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="9343d-160">有关详细信息，请参阅本文稍后介绍[](#block-the-following-urls-list-for-safe-links)的安全链接的"阻止以下 URL"列表部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="9343d-161">Jamie 和 Julia 都负责 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9343d-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="9343d-162">在不久之前，管理员配置了适用于 Jamie 和 Julia 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="9343d-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="9343d-163">Jamie 向 Julia 发送了一封电子邮件，但不知道该电子邮件包含恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="9343d-164">如果适用于 Julia 的安全链接策略配置为应用于内部收件人之间的邮件，则 Julia 受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="9343d-165">有关详细信息，请参阅本文稍后 [介绍的电子邮件](#safe-links-settings-for-email-messages) 的安全链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="9343d-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="9343d-166">电子邮件的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="9343d-167">安全链接扫描传入电子邮件中是否包含已知的恶意超链接。</span><span class="sxs-lookup"><span data-stu-id="9343d-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="9343d-168">扫描的 URL 使用 Microsoft 标准 URL 前缀重写 `https://nam01.safelinks.protection.outlook.com` ：。</span><span class="sxs-lookup"><span data-stu-id="9343d-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="9343d-169">重写链接后，将分析潜在恶意内容。</span><span class="sxs-lookup"><span data-stu-id="9343d-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="9343d-170">在安全链接重写 URL 之后，即使手动将邮件转发或答复给外部收件人， (URL 仍) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-170">After Safe Links rewrites a URL, the URL remains rewritten even if the message is *manually* forwarded or replied to (both to internal and external recipients).</span></span> <span data-ttu-id="9343d-171">不会重写添加到转发或答复邮件的其他链接。</span><span class="sxs-lookup"><span data-stu-id="9343d-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span> <span data-ttu-id="9343d-172">但是，在收件箱规则或SMTP 转发自动转发的情况下，不会在发送给最终收件人的邮件中重写 URL，除非该收件人还受安全链接保护，或者URL 已在以前的通信中重写。</span><span class="sxs-lookup"><span data-stu-id="9343d-172">However, in the case of *automatic* forwarding by Inbox rules or SMTP forwarding, the URL will not be rewritten in the message that's intended for the final recipient *unless* that recipient is also protected by Safe Links or the URL had already been rewritten in a previous communication.</span></span> 

<span data-ttu-id="9343d-173">以下列表介绍了适用于电子邮件的安全链接策略中的设置：</span><span class="sxs-lookup"><span data-stu-id="9343d-173">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="9343d-174">**选择邮件中未知潜在恶意 URL 的操作**：启用或禁用电子邮件中的安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-174">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="9343d-175">建议的值是 **On**。</span><span class="sxs-lookup"><span data-stu-id="9343d-175">The recommended value is **On**.</span></span> <span data-ttu-id="9343d-176">打开此设置会导致以下操作。</span><span class="sxs-lookup"><span data-stu-id="9343d-176">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="9343d-177">Windows 上的 Outlook (C2R) 启用安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-177">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="9343d-178">当单击邮件中的 URL 时，URL 将被重写，用户通过安全链接保护进行路由。</span><span class="sxs-lookup"><span data-stu-id="9343d-178">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="9343d-179">单击后，将针对已知恶意 URL 列表和"阻止以下 URL"列表检查[URL。](#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="9343d-179">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="9343d-180">没有有效信誉的 URL 将在后台异步触发。</span><span class="sxs-lookup"><span data-stu-id="9343d-180">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="9343d-181">**对指向文件的** 可疑链接应用实时 URL 扫描：启用链接（包括指向可下载内容的电子邮件中的链接）实时扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-181">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="9343d-182">建议的值已启用。</span><span class="sxs-lookup"><span data-stu-id="9343d-182">The recommended value is enabled.</span></span>

  - <span data-ttu-id="9343d-183">**等待 URL 扫描完成，然后再传递邮件**：</span><span class="sxs-lookup"><span data-stu-id="9343d-183">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="9343d-184">已启用：包含 URL 的邮件将一直进行，直到扫描完成。</span><span class="sxs-lookup"><span data-stu-id="9343d-184">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="9343d-185">仅在确认 URL 是安全的之后，才传递邮件。</span><span class="sxs-lookup"><span data-stu-id="9343d-185">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="9343d-186">这是建议的值。</span><span class="sxs-lookup"><span data-stu-id="9343d-186">This is the recommended value.</span></span>
    - <span data-ttu-id="9343d-187">已禁用：如果 URL 扫描无法完成，无论如何都传递邮件。</span><span class="sxs-lookup"><span data-stu-id="9343d-187">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="9343d-188">**将安全链接应用于组织** 内部发送的电子邮件：启用或禁用对同一 Exchange Online 组织中内部发件人和内部收件人之间发送的邮件的安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-188">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="9343d-189">建议的值已启用。</span><span class="sxs-lookup"><span data-stu-id="9343d-189">The recommended value is enabled.</span></span>

- <span data-ttu-id="9343d-190">**Do not track user clicks**： Enables or disables storing Safe Links click data for URLs clicked in email messages.</span><span class="sxs-lookup"><span data-stu-id="9343d-190">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="9343d-191">建议的值是保持此设置未选择 (跟踪用户单击) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-191">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="9343d-192">目前不支持在内部发件人和内部收件人之间发送的电子邮件中的链接的 URL 单击跟踪。</span><span class="sxs-lookup"><span data-stu-id="9343d-192">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="9343d-193">**不允许用户单击到原始 URL：** 允许或阻止用户通过警告 [页面](#warning-pages-from-safe-links) 单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-193">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="9343d-194">推荐值已启用。</span><span class="sxs-lookup"><span data-stu-id="9343d-194">The recommend value is enabled.</span></span>

- <span data-ttu-id="9343d-195">**在通知和警告页面上** 显示组织品牌：此选项在警告页面上显示组织的品牌。</span><span class="sxs-lookup"><span data-stu-id="9343d-195">**Display the organization branding on notification and warning pages**: This option shows your organization's branding on warning pages.</span></span> <span data-ttu-id="9343d-196">品牌打造可帮助用户识别合法警告，因为默认 Microsoft 警告页面经常被攻击者使用。</span><span class="sxs-lookup"><span data-stu-id="9343d-196">Branding helps users identify legitimate warnings, because default Microsoft warning pages are often used by attackers.</span></span> <span data-ttu-id="9343d-197">有关自定义品牌打造详细信息，请参阅将品牌添加到组织的 [Azure Active Directory 登录页面](/azure/active-directory/fundamentals/customize-branding)。</span><span class="sxs-lookup"><span data-stu-id="9343d-197">For more information about customized branding, see [Add branding to your organization's Azure Active Directory sign-in page](/azure/active-directory/fundamentals/customize-branding).</span></span>

- <span data-ttu-id="9343d-198">**不要重写以下 URL：** 保留 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-198">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="9343d-199">保留不需要扫描的安全 URL 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="9343d-199">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="9343d-200">该列表对于每个安全链接策略都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9343d-200">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="9343d-201">有关不重写以下 **URL** 列表的信息，请参阅本文稍后的安全链接策略 [](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)中的"不重写以下 URL"列表一节。</span><span class="sxs-lookup"><span data-stu-id="9343d-201">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="9343d-202">有关安全链接策略的"标准"和"严格"策略设置的建议值详细信息，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="9343d-202">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="9343d-203">**收件人** 筛选器：需要指定确定策略适用的收件人条件和例外。</span><span class="sxs-lookup"><span data-stu-id="9343d-203">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="9343d-204">可以将这些属性用于条件和例外：</span><span class="sxs-lookup"><span data-stu-id="9343d-204">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="9343d-205">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="9343d-205">**The recipient is**</span></span>
  - <span data-ttu-id="9343d-206">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="9343d-206">**The recipient domain is**</span></span>
  - <span data-ttu-id="9343d-207">**收件人为以下组的成员**</span><span class="sxs-lookup"><span data-stu-id="9343d-207">**The recipient is a member of**</span></span>

  <span data-ttu-id="9343d-208">一次只能使用一个条件或例外，但条件或例外可以包含多个值。</span><span class="sxs-lookup"><span data-stu-id="9343d-208">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="9343d-209">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="9343d-209">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9343d-210">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="9343d-210">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="9343d-211">**优先级**：如果创建多个策略，可以指定策略的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="9343d-211">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="9343d-212">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="9343d-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="9343d-213">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="9343d-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="9343d-214">安全链接在电子邮件中的工作方式</span><span class="sxs-lookup"><span data-stu-id="9343d-214">How Safe Links works in email messages</span></span>

<span data-ttu-id="9343d-215">在高级别上，下面将说明安全链接保护在电子邮件中的 URL 上的工作原理：</span><span class="sxs-lookup"><span data-stu-id="9343d-215">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="9343d-216">所有电子邮件均通过 EOP，其中 Internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器在邮件传递到收件人邮箱之前。</span><span class="sxs-lookup"><span data-stu-id="9343d-216">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="9343d-217">用户在邮箱中打开邮件，并单击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-217">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="9343d-218">安全链接在打开网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="9343d-218">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="9343d-219">如果 URL 包含在"阻止以下 **URL"** 列表中，将打开 [阻止的 URL](#blocked-url-warning) 警告。</span><span class="sxs-lookup"><span data-stu-id="9343d-219">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="9343d-220">如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。</span><span class="sxs-lookup"><span data-stu-id="9343d-220">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="9343d-221">如果 URL 指向可下载的文件，并且适用于用户的策略中启用了"对指向文件的可疑链接和链接应用实时 **URL** 扫描"设置，则选中可下载的文件。</span><span class="sxs-lookup"><span data-stu-id="9343d-221">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="9343d-222">如果确定 URL 是安全的，将打开网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-222">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="9343d-223">Microsoft Teams 的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-223">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9343d-224">自 2020 年 3 月起，此功能为预览版，仅适用于 Microsoft Teams 技术采用计划 (TAP) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-224">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="9343d-225">有关发布计划的信息，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="9343d-225">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="9343d-226">在安全链接策略中为 Microsoft Teams 启用或禁用安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-226">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="9343d-227">具体来说，使用" **为 Microsoft Teams 中的未知或潜在恶意 URL 选择操作"** 设置。</span><span class="sxs-lookup"><span data-stu-id="9343d-227">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="9343d-228">建议的值是 **On**。</span><span class="sxs-lookup"><span data-stu-id="9343d-228">The recommended value is **On**.</span></span>

<span data-ttu-id="9343d-229">适用于电子邮件中链接的安全链接策略中的以下设置也适用于 Teams 中的链接：</span><span class="sxs-lookup"><span data-stu-id="9343d-229">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="9343d-230">**对指向文件的可疑链接应用实时 URL 扫描**</span><span class="sxs-lookup"><span data-stu-id="9343d-230">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="9343d-231">**不跟踪用户单击**</span><span class="sxs-lookup"><span data-stu-id="9343d-231">**Do not track user clicks**</span></span>
- <span data-ttu-id="9343d-232">**不允许用户单击至初始 URL**</span><span class="sxs-lookup"><span data-stu-id="9343d-232">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="9343d-233">这些设置在以前的电子邮件 [安全链接设置部分中进行了说明](#safe-links-settings-for-email-messages) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-233">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="9343d-234">为 Microsoft Teams 启用安全链接保护后，当受保护的用户单击链接时，将针对已知恶意链接列表检查 Teams 中的 URL (单击时保护) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-234">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="9343d-235">不重写 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-235">URLs are not rewritten.</span></span> <span data-ttu-id="9343d-236">如果发现链接是恶意链接，用户将具有以下体验：</span><span class="sxs-lookup"><span data-stu-id="9343d-236">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="9343d-237">如果在 Teams 对话、群聊或频道中单击了链接，则以下屏幕截图中显示的警告页面将显示在默认 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="9343d-237">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="9343d-238">如果从固定选项卡单击了链接，则警告页面将显示在该选项卡内的 Teams 界面中。出于安全考虑，禁用在 Web 浏览器中打开链接的选项。</span><span class="sxs-lookup"><span data-stu-id="9343d-238">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="9343d-239">根据策略中"不允许用户单击到原始 **URL"** 设置的配置方式，用户将允许或不允许单击到原始 URL (是否继续 (屏幕截图) 中不建议) 。 </span><span class="sxs-lookup"><span data-stu-id="9343d-239">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="9343d-240">我们建议您启用"不允许用户单击访问原始 **URL"** 设置，以便用户无法单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-240">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="9343d-241">如果发送链接的用户未包含在启用了 Teams 保护的安全链接策略中，则用户可以自由单击访问其计算机或设备上的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-241">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

!["Teams 安全链接"页面报告恶意链接。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="9343d-243">单击 **警告页面上的** "返回"按钮将用户返回到其原始上下文或 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="9343d-243">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="9343d-244">但是，再次单击原始链接将导致安全链接重新扫描 URL，因此警告页面将重新出现。</span><span class="sxs-lookup"><span data-stu-id="9343d-244">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="9343d-245">安全链接在 Teams 中的工作方式</span><span class="sxs-lookup"><span data-stu-id="9343d-245">How Safe Links works in Teams</span></span>

<span data-ttu-id="9343d-246">在高级别上，下面将说明安全链接保护在 Microsoft Teams 中对 URL 的工作原理：</span><span class="sxs-lookup"><span data-stu-id="9343d-246">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="9343d-247">用户启动 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="9343d-247">A user starts the Teams app.</span></span>

2. <span data-ttu-id="9343d-248">Microsoft 365 验证用户组织是否包括适用于 Office 365 的 Microsoft Defender，并且用户是否包含在启用了 Microsoft Teams 保护的活动安全链接策略中。</span><span class="sxs-lookup"><span data-stu-id="9343d-248">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="9343d-249">在用户单击聊天、群聊、频道和选项卡时验证 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-249">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="9343d-250">Office 365 应用的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="9343d-250">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="9343d-251">Office 365 应用的安全链接保护检查 Office 文档中的链接，而不是电子邮件 (但它可以在打开 Office 文档后检查电子邮件中附加的 Office) 中的链接。</span><span class="sxs-lookup"><span data-stu-id="9343d-251">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="9343d-252">Office 365 应用的安全链接保护具有以下客户端要求：</span><span class="sxs-lookup"><span data-stu-id="9343d-252">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="9343d-253">Microsoft 365 应用版或 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="9343d-253">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="9343d-254">Windows、Mac 或 Web 浏览器中 Word、Excel 和 PowerPoint 的当前版本。</span><span class="sxs-lookup"><span data-stu-id="9343d-254">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="9343d-255">iOS 或 Android 设备上的 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="9343d-255">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="9343d-256">Windows 上的 Visio。</span><span class="sxs-lookup"><span data-stu-id="9343d-256">Visio on Windows.</span></span>
  - <span data-ttu-id="9343d-257">Web 浏览器中的 OneNote。</span><span class="sxs-lookup"><span data-stu-id="9343d-257">OneNote in a web browser.</span></span>

- <span data-ttu-id="9343d-258">Office 365 应用配置为使用新式验证。</span><span class="sxs-lookup"><span data-stu-id="9343d-258">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="9343d-259">有关详细信息，请参阅新式验证如何适用于 [Office 2013、Office 2016 和 Office 2019 客户端应用](../../enterprise/modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="9343d-259">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span>

- <span data-ttu-id="9343d-260">用户使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9343d-260">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="9343d-261">有关详细信息，请参阅登录到[Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="9343d-261">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="9343d-262">在安全链接的全局设置中（而不是在安全链接策略中）为 Office 365 应用配置安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-262">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="9343d-263">但是，若要应用 Office 365 应用的安全链接保护，打开 Office 文档并单击链接的用户必须包含在活动的安全链接策略中。</span><span class="sxs-lookup"><span data-stu-id="9343d-263">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="9343d-264">以下安全链接设置适用于 Office 365 应用：</span><span class="sxs-lookup"><span data-stu-id="9343d-264">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="9343d-265">**Office 365 应用程序**：启用或禁用受支持的 Office 365 应用中的安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-265">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="9343d-266">默认值和推荐值为 **On。**</span><span class="sxs-lookup"><span data-stu-id="9343d-266">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="9343d-267">**Do not track when users click Safe Links**： Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word， Excel， PowerPoint， and Visio.</span><span class="sxs-lookup"><span data-stu-id="9343d-267">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="9343d-268">建议值为 **Off**，这意味着将跟踪用户点击量。</span><span class="sxs-lookup"><span data-stu-id="9343d-268">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="9343d-269">**不允许用户** 单击指向原始 URL 的安全链接：允许或阻止用户在桌面版 Word、Excel、PowerPoint 和 Visio 中单击通过警告页面指向原始 URL。 [](#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="9343d-269">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="9343d-270">默认值和推荐值为 **On。**</span><span class="sxs-lookup"><span data-stu-id="9343d-270">The default and recommended value is **On**.</span></span>

<span data-ttu-id="9343d-271">若要为 Office 365 应用配置安全链接设置，请参阅为 [Office 365](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)应用配置安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-271">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="9343d-272">有关"标准"和"严格"策略设置的建议值详细信息，请参阅安全链接 [的全局设置](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="9343d-272">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="9343d-273">安全链接在 Office 365 应用中的工作方式</span><span class="sxs-lookup"><span data-stu-id="9343d-273">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="9343d-274">在高级别上，下面将说明安全链接保护在 Office 365 应用中对 URL 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="9343d-274">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="9343d-275">支持的 Office 365 应用在上一部分中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9343d-275">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="9343d-276">用户在包含 Microsoft 365 应用版或 Microsoft 365 商业高级版的组织使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="9343d-276">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="9343d-277">用户打开并单击受支持的 Office 应用中的 Office 文档链接。</span><span class="sxs-lookup"><span data-stu-id="9343d-277">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="9343d-278">安全链接在打开目标网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="9343d-278">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="9343d-279">如果 URL 包含在跳过安全链接扫描的列表中 (将打开阻止的 URL ) 阻止[的 URL 警告](#blocked-url-warning)页。</span><span class="sxs-lookup"><span data-stu-id="9343d-279">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="9343d-280">如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。</span><span class="sxs-lookup"><span data-stu-id="9343d-280">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="9343d-281">如果 URL 指向可下载的文件，并且将适用于用户的安全链接策略配置为扫描指向可下载内容的链接 (应用实时 **URL** 扫描，以检查指向文件) 的可疑链接和链接，将检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="9343d-281">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="9343d-282">如果 URL 被视为安全 URL，则用户将访问网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-282">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="9343d-283">如果安全链接扫描无法完成，不会触发安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="9343d-283">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="9343d-284">在 Office 桌面客户端中，在用户继续访问目标网站之前，将警告用户。</span><span class="sxs-lookup"><span data-stu-id="9343d-284">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="9343d-285">在每个会话开始时，可能需要几秒钟来验证用户是否启用了 Office 安全链接。</span><span class="sxs-lookup"><span data-stu-id="9343d-285">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="9343d-286">安全链接的"阻止以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="9343d-286">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="9343d-287">" **阻止以下 URL"** 列表定义安全链接扫描始终阻止的链接，这些链接位于以下位置：</span><span class="sxs-lookup"><span data-stu-id="9343d-287">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="9343d-288">电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9343d-288">Email messages.</span></span>
- <span data-ttu-id="9343d-289">Windows 和 Mac 中的 Office 365 应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="9343d-289">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="9343d-290">Office for iOS 和 Android 中的文档。</span><span class="sxs-lookup"><span data-stu-id="9343d-290">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="9343d-291">当活动安全链接策略中的用户单击受支持的应用中的阻止链接时，他们会访问阻止 [的 URL 警告](#blocked-url-warning) 页面。</span><span class="sxs-lookup"><span data-stu-id="9343d-291">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="9343d-292">在安全链接的全局设置中配置 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="9343d-292">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="9343d-293">有关说明，请参阅 [配置"阻止以下 URL"列表](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="9343d-293">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="9343d-294">**注意**：</span><span class="sxs-lookup"><span data-stu-id="9343d-294">**Notes**:</span></span>

- <span data-ttu-id="9343d-295">有关被阻止的 URL 的真正通用列表，请参阅管理 [租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="9343d-295">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="9343d-296">限制：</span><span class="sxs-lookup"><span data-stu-id="9343d-296">Limits:</span></span>
  - <span data-ttu-id="9343d-297">最大条目数为 500。</span><span class="sxs-lookup"><span data-stu-id="9343d-297">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="9343d-298">条目的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="9343d-298">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="9343d-299">所有条目不能超过 10，000 个字符。</span><span class="sxs-lookup"><span data-stu-id="9343d-299">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="9343d-300">不要在 URL 末尾添加 `/` () 斜杠。</span><span class="sxs-lookup"><span data-stu-id="9343d-300">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="9343d-301">例如，使用 `https://www.contoso.com` ，而不是 `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="9343d-301">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="9343d-302">例如或 (仅域 URL) `contoso.com` `tailspintoys.com` 将阻止包含该域的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-302">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="9343d-303">可以阻止子域，但不阻止整个域。</span><span class="sxs-lookup"><span data-stu-id="9343d-303">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="9343d-304">例如，阻止包含子域的任何 URL，但不阻止包含完整域 `toys.contoso.com*` 的 `contoso.com` URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-304">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="9343d-305">每个 URL 条目可以包含最多三 () `*` 通配符。</span><span class="sxs-lookup"><span data-stu-id="9343d-305">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="9343d-306">"阻止以下 URL"列表的条目语法</span><span class="sxs-lookup"><span data-stu-id="9343d-306">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="9343d-307">下表介绍了您可以输入的值及其结果的示例：</span><span class="sxs-lookup"><span data-stu-id="9343d-307">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="9343d-308">值</span><span class="sxs-lookup"><span data-stu-id="9343d-308">Value</span></span>|<span data-ttu-id="9343d-309">结果</span><span class="sxs-lookup"><span data-stu-id="9343d-309">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="9343d-310">或者</span><span class="sxs-lookup"><span data-stu-id="9343d-310">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="9343d-311">阻止域、子域和路径。</span><span class="sxs-lookup"><span data-stu-id="9343d-311">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="9343d-312">例如， `https://www.contoso.com` `https://sub.contoso.com` 、 和 `https://contoso.com/abc` 被阻止。</span><span class="sxs-lookup"><span data-stu-id="9343d-312">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="9343d-313">阻止 `https://contoso.com/a` 但不阻止其他子路径（如 `https://contoso.com/a/b` ）。</span><span class="sxs-lookup"><span data-stu-id="9343d-313">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="9343d-314">块 `https://contoso.com/a` 和其他子路径（如 `https://contoso.com/a/b` ）。</span><span class="sxs-lookup"><span data-stu-id="9343d-314">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="9343d-315">阻止此示例中 (`toys` 子域) 但允许单击其他域 URL (或 `https://contoso.com` `https://home.contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-315">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="9343d-316">安全链接策略中的"不重写以下 URL"列表</span><span class="sxs-lookup"><span data-stu-id="9343d-316">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="9343d-317">如果组织使用安全链接策略，则不重写以下 **URL** 列表是第三方网络钓鱼测试唯一受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="9343d-317">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="9343d-318">每个安全链接策略都包含一个"不重写以下 **URL"** 列表，您可以使用该列表指定安全链接扫描未重写的 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-318">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="9343d-319">换句话说，该列表允许策略中包含的用户访问指定的 URL，否则安全链接会阻止这些 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-319">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="9343d-320">可以在不同的安全链接策略中配置不同的列表。</span><span class="sxs-lookup"><span data-stu-id="9343d-320">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="9343d-321">策略处理在用户应用第一 (策略后) 可能停止。</span><span class="sxs-lookup"><span data-stu-id="9343d-321">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="9343d-322">因此，只有一个"不 **重写以下 URL"** 列表应用于包含在多个活动安全链接策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="9343d-322">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="9343d-323">若要将条目添加到新的或现有的安全链接策略中的列表，请参阅 [创建安全链接策略](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或修改 [安全链接策略](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="9343d-323">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="9343d-324">**注意**：</span><span class="sxs-lookup"><span data-stu-id="9343d-324">**Notes**:</span></span>

- <span data-ttu-id="9343d-325">以下客户端无法识别安全链接策略中的 **不** 重写以下 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="9343d-325">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="9343d-326">根据这些客户端中安全链接扫描的结果，可阻止包含在这些安全管理中的用户访问 URL：</span><span class="sxs-lookup"><span data-stu-id="9343d-326">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="9343d-327">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9343d-327">Microsoft Teams</span></span>
  - <span data-ttu-id="9343d-328">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="9343d-328">Office web apps</span></span>

  <span data-ttu-id="9343d-329">有关任何地方允许的 URL 的真正通用列表，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="9343d-329">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="9343d-330">请考虑将常用的内部 URL 添加到列表中，以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="9343d-330">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="9343d-331">例如，如果你有本地服务（如 Skype for Business 或 SharePoint），你可以添加这些 URL 以将其从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="9343d-331">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="9343d-332">如果安全链接策略中已有"不重写以下 **URL"** 条目，请务必查看列表并根据需要添加通配符。</span><span class="sxs-lookup"><span data-stu-id="9343d-332">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="9343d-333">例如，你的列表有一个类似 的条目 `https://contoso.com/a` ，你稍后决定包括子路径，如 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="9343d-333">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="9343d-334">不要添加新条目，而是向现有条目添加通配符，以便它成为 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="9343d-334">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="9343d-335">每个 URL 条目可以包含最多三 () `*` 通配符。</span><span class="sxs-lookup"><span data-stu-id="9343d-335">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="9343d-336">通配符明确包括前缀或子域。</span><span class="sxs-lookup"><span data-stu-id="9343d-336">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="9343d-337">例如，条目与 不同，因为允许用户访问指定域中的子域 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 和路径。</span><span class="sxs-lookup"><span data-stu-id="9343d-337">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="9343d-338">"不重写以下 URL"列表的条目语法</span><span class="sxs-lookup"><span data-stu-id="9343d-338">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="9343d-339">下表介绍了您可以输入的值及其结果的示例：</span><span class="sxs-lookup"><span data-stu-id="9343d-339">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="9343d-340">值</span><span class="sxs-lookup"><span data-stu-id="9343d-340">Value</span></span>|<span data-ttu-id="9343d-341">结果</span><span class="sxs-lookup"><span data-stu-id="9343d-341">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="9343d-342">允许访问 `https://contoso.com` 子域或路径，但不能访问子域或路径。</span><span class="sxs-lookup"><span data-stu-id="9343d-342">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="9343d-343">允许访问域、子域和路径 (例如、 `https://www.contoso.com` `https://www.contoso.com` 或 `https://maps.contoso.com` `https://www.contoso.com/a`) 。</span><span class="sxs-lookup"><span data-stu-id="9343d-343">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="9343d-344">此条目本质上优于 ，因为它不允许潜在的欺诈性网站 `*contoso.com*` ，如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="9343d-344">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="9343d-345">允许访问 `https://contoso.com/a` ，但不允许访问子路径（如 ） `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9343d-345">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="9343d-346">允许访问 `https://contoso.com/a` 和子路径，如 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="9343d-346">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="9343d-347">安全链接中的警告页面</span><span class="sxs-lookup"><span data-stu-id="9343d-347">Warning pages from Safe Links</span></span>

<span data-ttu-id="9343d-348">本节包含单击 URL 时安全链接保护触发的各种警告页面的示例。</span><span class="sxs-lookup"><span data-stu-id="9343d-348">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="9343d-349">请注意，已更新多个警告页面。</span><span class="sxs-lookup"><span data-stu-id="9343d-349">Note that several warning pages have been updated.</span></span> <span data-ttu-id="9343d-350">如果还没有看到更新的页面，你很快就会看到。</span><span class="sxs-lookup"><span data-stu-id="9343d-350">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="9343d-351">更新的页面包括新的配色方案、更多详细信息，以及即使给定警告和建议，仍可以继续访问网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-351">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="9343d-352">扫描正在进行通知</span><span class="sxs-lookup"><span data-stu-id="9343d-352">Scan in progress notification</span></span>

<span data-ttu-id="9343d-353">单击的 URL 正由安全链接进行扫描。</span><span class="sxs-lookup"><span data-stu-id="9343d-353">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="9343d-354">在再次尝试链接之前，可能需要等待片刻。</span><span class="sxs-lookup"><span data-stu-id="9343d-354">You might need to wait a few moments before trying the link again.</span></span>

!["正在扫描链接"通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="9343d-356">原始通知页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="9343d-356">The original notification page looked like this:</span></span>

![原始"正在扫描链接"通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="9343d-358">可疑邮件警告</span><span class="sxs-lookup"><span data-stu-id="9343d-358">Suspicious message warning</span></span>

<span data-ttu-id="9343d-359">单击的 URL 位于类似于其他可疑邮件的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="9343d-359">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="9343d-360">我们建议您在继续网站之前仔细检查电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9343d-360">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["从可疑邮件单击链接"警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="9343d-362">网络钓鱼尝试警告</span><span class="sxs-lookup"><span data-stu-id="9343d-362">Phishing attempt warning</span></span>

<span data-ttu-id="9343d-363">单击的 URL 位于已标识为网络钓鱼攻击的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="9343d-363">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="9343d-364">因此，电子邮件中所有 URL 都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="9343d-364">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="9343d-365">建议您不要继续访问该网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-365">We recommend that you do not proceed to the site.</span></span>

!["从网络钓鱼邮件中单击链接"警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="9343d-367">恶意网站警告</span><span class="sxs-lookup"><span data-stu-id="9343d-367">Malicious website warning</span></span>

<span data-ttu-id="9343d-368">单击的 URL 指向已标识为恶意的网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-368">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="9343d-369">建议您不要继续访问该网站。</span><span class="sxs-lookup"><span data-stu-id="9343d-369">We recommend that you do not proceed to the site.</span></span>

!["此网站被分类为恶意"警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="9343d-371">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="9343d-371">The original warning page looked like this:</span></span>

![原始"此网站已分类为恶意"警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="9343d-373">阻止的 URL 警告</span><span class="sxs-lookup"><span data-stu-id="9343d-373">Blocked URL warning</span></span>

<span data-ttu-id="9343d-374">单击的 URL 已被您组织的管理员手动阻止 (安全链接列表的全局设置中的"阻止以下 URL") 。</span><span class="sxs-lookup"><span data-stu-id="9343d-374">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="9343d-375">安全链接未扫描该链接，因为它已被手动阻止。</span><span class="sxs-lookup"><span data-stu-id="9343d-375">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="9343d-376">管理员手动阻止特定 URL 的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="9343d-376">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="9343d-377">如果认为不应阻止网站，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="9343d-377">If you think the site should not be blocked, contact your admin.</span></span>

!["此网站被管理员阻止"警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="9343d-379">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="9343d-379">The original warning page looked like this:</span></span>

![原始"根据组织的 URL 策略阻止此网站"警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="9343d-381">错误警告</span><span class="sxs-lookup"><span data-stu-id="9343d-381">Error warning</span></span>

<span data-ttu-id="9343d-382">发生了某种错误，无法打开 URL。</span><span class="sxs-lookup"><span data-stu-id="9343d-382">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["无法加载您尝试访问的页面"警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="9343d-384">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="9343d-384">The original warning page looked like this:</span></span>

![原始"无法加载此网页"警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
