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
description: 本文中，管理员可了解 defender 保险箱链接保护，Office 365保护组织免受使用恶意 URL 的网络钓鱼和其他攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 675de13410ac98e18a8b72125c2226d2c9c62821
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698984"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3fc5c-103">保险箱Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3fc5c-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3fc5c-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-104">**Applies to**</span></span>
- [<span data-ttu-id="3fc5c-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="3fc5c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3fc5c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fc5c-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="3fc5c-107">本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="3fc5c-108">如果你使用的是 Outlook.com、Microsoft 365 家庭版 或 Microsoft 365 个人版，并且正在查找有关 Outlook 中的安全链接的信息，请参阅高级[Outlook.com 安全](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="3fc5c-109">保险箱链接是 Defender [for Office 365](defender-for-office-365.md)中的一项功能，它提供邮件流中入站电子邮件的 URL 扫描和重写，以及电子邮件和其他位置中 URL 和链接的单击验证时间。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-109">Safe Links is a feature in [Defender for Office 365](defender-for-office-365.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="3fc5c-110">保险箱除了 EOP 邮箱中的入站电子邮件[](anti-spam-and-anti-malware-protection.md)中的常规反垃圾邮件和反恶意软件保护外，Exchange Online Protection (扫描) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="3fc5c-111">保险箱链接扫描可帮助保护组织免受钓鱼和其他攻击中使用的恶意链接的攻击。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="3fc5c-112">保险箱链接保护可在以下位置使用：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="3fc5c-113">**电子邮件：保险箱** 链接策略控制电子邮件中链接保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="3fc5c-114">没有默认链接保险箱，因此若要保护电子邮件中的保险箱链接，需要创建一个或多个链接保险箱 **策略**。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="3fc5c-115">有关说明，请参阅在[Microsoft Defender 保险箱设置链接策略Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

  <span data-ttu-id="3fc5c-116">有关电子邮件的链接保险箱保护功能，请参阅本文保险箱电子邮件的链接设置"部分。 [](#safe-links-settings-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="3fc5c-117">保险箱链接对启用邮件的公用文件夹不起作用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-117">Safe Links does not work on mail-enabled public folders.</span></span>

- <span data-ttu-id="3fc5c-118">**Microsoft Teams (** TAP Preview) ： 保险箱 Links protection for links in Teams conversations， group chats， or from channels is also controlled by 保险箱 Links policies.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-118">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="3fc5c-119">没有默认链接保险箱，因此若要在 Teams 中保护 保险箱 链接，需要创建一个或多个保险箱 **链接策略**。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-119">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="3fc5c-120">有关在 Teams 中保险箱链接保护保险箱，请参阅本文保险箱的 Microsoft Teams[](#safe-links-settings-for-microsoft-teams)链接设置一节。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-120">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="3fc5c-121">**Office 365应用**：保险箱支持Office 365、移动和 Web 应用中提供适用于应用的链接保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-121">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web apps.</span></span> <span data-ttu-id="3fc5c-122">在 **全局** 保险箱"链接"策略Office 365为应用配置链接保险箱保护。 </span><span class="sxs-lookup"><span data-stu-id="3fc5c-122">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="3fc5c-123">有关说明，请参阅[在 Microsoft Defender 中为 保险箱 链接设置配置全局Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-123">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="3fc5c-124">保险箱Office 365应用的链接保护适用于组织中获得 Defender for Office 365 许可的所有用户，无论用户是否包含在活动的 保险箱 链接策略中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-124">Safe Links protection for Office 365 apps is applied to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span>

  <span data-ttu-id="3fc5c-125">有关在应用中保险箱链接保护Office 365，请参阅本文保险箱应用的 Office 365[链接](#safe-links-settings-for-office-365-apps)设置部分。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="3fc5c-126">本文包含以下类型链接保险箱详细说明：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="3fc5c-127">**设置链接** 保险箱：这些设置仅适用于特定策略中包含的用户，并且策略之间的设置可能不同。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="3fc5c-128">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-128">These settings include:</span></span>

  - [<span data-ttu-id="3fc5c-129">保险箱电子邮件的链接设置</span><span class="sxs-lookup"><span data-stu-id="3fc5c-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="3fc5c-130">保险箱链接设置Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fc5c-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="3fc5c-131">链接策略中的"不重写保险箱 URL"</span><span class="sxs-lookup"><span data-stu-id="3fc5c-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="3fc5c-132">**全局保险箱链接设置**：这些设置是全局配置的，而不是在保险箱策略中配置的。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="3fc5c-133">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-133">These settings include:</span></span>

  - [<span data-ttu-id="3fc5c-134">保险箱应用的链接Office 365设置</span><span class="sxs-lookup"><span data-stu-id="3fc5c-134">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="3fc5c-135">链接的"阻止以下 URL"保险箱列表</span><span class="sxs-lookup"><span data-stu-id="3fc5c-135">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="3fc5c-136">下表介绍了 Microsoft 365 Microsoft 365 和 Office 365 组织中包含 Defender for Office 365 (的 保险箱 链接的方案，换句话说，在) 示例中，缺少许可永远不会是问题。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-136">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

<br>

****

|<span data-ttu-id="3fc5c-137">应用场景</span><span class="sxs-lookup"><span data-stu-id="3fc5c-137">Scenario</span></span>|<span data-ttu-id="3fc5c-138">结果</span><span class="sxs-lookup"><span data-stu-id="3fc5c-138">Result</span></span>|
|---|---|
|<span data-ttu-id="3fc5c-139">表示是市场营销部门的成员。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-139">Jean is a member of the marketing department.</span></span> <span data-ttu-id="3fc5c-140">保险箱Office 365应用的链接保护在 保险箱 链接的全局设置中打开，并且存在适用于市场营销部门成员的 保险箱 链接策略。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-140">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="3fc5c-141">在电子邮件PowerPoint打开一个演示文稿，然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-141">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="3fc5c-142">百分之百受链接保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-142">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="3fc5c-143">该链接策略中包含 保险箱，保险箱应用的链接Office 365保护功能已打开。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-143">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="3fc5c-144">有关在 Office 365 应用中使用 保险箱 链接保护保险箱相关要求，请参阅本文稍后介绍的 保险箱[Links Office 365 部分](#safe-links-settings-for-office-365-apps)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-144">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="3fc5c-145">Chris 的Microsoft 365 E5未配置保险箱链接策略。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-145">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="3fc5c-146">Chris 从外部发件人收到一封电子邮件，其中包含他最终单击的恶意网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-146">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="3fc5c-147">Chris 不受链接保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-147">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="3fc5c-148">管理员必须至少为任何人创建一保险箱链接策略，才能在入站电子邮件保险箱链接保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-148">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="3fc5c-149">Chris 必须包含在策略条件中，才能保险箱链接保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-149">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="3fc5c-150">在 Pat 的组织中，管理员尚未创建任何保险箱链接策略，保险箱应用的链接Office 365保护功能已打开。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-150">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="3fc5c-151">Pat 打开 Word 文档并单击该文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-151">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="3fc5c-152">Pat 不受链接保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-152">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="3fc5c-153">尽管保险箱应用的链接保护Office 365全局打开，但 Pat 未包含在任何活动的 保险箱 链接策略中，因此无法应用保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-153">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="3fc5c-154">In Lee's organization， `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for 保险箱 Links.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-154">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="3fc5c-155">A 保险箱 Links policy that includes Lee already exists.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-155">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="3fc5c-156">Lee 收到一封包含 URL 的电子邮件 `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-156">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="3fc5c-157">Lee 单击 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-157">Lee clicks the URL.</span></span>|<span data-ttu-id="3fc5c-158">可能为 Lee 自动阻止 URL;这取决于列表中的 URL 条目和所使用的电子邮件客户端 Lee。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-158">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="3fc5c-159">有关详细信息，请参阅本文稍后介绍的"阻止以下[URL"保险箱链接](#block-the-following-urls-list-for-safe-links)"部分。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-159">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="3fc5c-160">Jamie 和 Julia 都负责 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-160">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="3fc5c-161">在很长一段时间之前，管理员保险箱适用于 Jamie 和 Julia 的链接策略。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-161">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="3fc5c-162">Jamie 向 Julia 发送了一封电子邮件，但不知道该电子邮件包含恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-162">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="3fc5c-163">如果适用于 julia 的 保险箱 链接策略保险箱配置为应用于内部收件人之间的邮件，则 Julia 受"链接"保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-163">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="3fc5c-164">有关详细信息，请参阅本文保险箱电子邮件[](#safe-links-settings-for-email-messages)的链接设置部分。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-164">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|
|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="3fc5c-165">保险箱电子邮件的链接设置</span><span class="sxs-lookup"><span data-stu-id="3fc5c-165">Safe Links settings for email messages</span></span>

<span data-ttu-id="3fc5c-166">保险箱链接扫描传入电子邮件中的已知恶意超链接。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-166">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="3fc5c-167">扫描的 URL 使用 Microsoft 标准 URL 前缀重写 `https://nam01.safelinks.protection.outlook.com` ：。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-167">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="3fc5c-168">重写链接后，将分析潜在恶意内容。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-168">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="3fc5c-169">在保险箱链接重写 URL 之后，即使手动将邮件转发或答复给内部和外部收件人， ( URL 仍然重写) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-169">After Safe Links rewrites a URL, the URL remains rewritten even if the message is *manually* forwarded or replied to (both to internal and external recipients).</span></span> <span data-ttu-id="3fc5c-170">不会重写添加到转发或答复邮件的其他链接。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-170">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span> <span data-ttu-id="3fc5c-171">但是，在收件箱规则或SMTP 转发自动转发的情况下，不会在发送给最终收件人的邮件中重写 URL，除非该收件人还受 保险箱 链接或URL 已在以前的通信中重写。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-171">However, in the case of *automatic* forwarding by Inbox rules or SMTP forwarding, the URL will not be rewritten in the message that's intended for the final recipient *unless* that recipient is also protected by Safe Links or the URL had already been rewritten in a previous communication.</span></span> 

<span data-ttu-id="3fc5c-172">以下列表保险箱电子邮件的链接策略中的设置：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-172">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="3fc5c-173">**选择邮件中未知潜在** 恶意 URL 的操作：启用或保险箱电子邮件中的链接扫描。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-173">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="3fc5c-174">建议的值是 **On**。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-174">The recommended value is **On**.</span></span> <span data-ttu-id="3fc5c-175">打开此设置会导致以下操作。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-175">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="3fc5c-176">保险箱链接扫描在 Outlook (C2R) 中Windows。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-176">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="3fc5c-177">重写 URL，当用户单击邮件中的 URL 时保险箱链接保护进行路由。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-177">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="3fc5c-178">单击后，将针对已知恶意 URL 列表和"阻止以下 URL"列表检查[URL。](#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-178">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="3fc5c-179">没有有效信誉的 URL 将在后台异步触发。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-179">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="3fc5c-180">**对指向文件的** 可疑链接应用实时 URL 扫描：启用链接（包括指向可下载内容的电子邮件中的链接）实时扫描。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-180">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="3fc5c-181">建议的值已启用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-181">The recommended value is enabled.</span></span>
  - <span data-ttu-id="3fc5c-182">**等待 URL 扫描完成，然后再传递邮件**：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-182">**Wait for URL scanning to complete before delivering the message**:</span></span>
    - <span data-ttu-id="3fc5c-183">已启用：包含 URL 的邮件将一直进行，直到扫描完成。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-183">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="3fc5c-184">仅在确认 URL 是安全的之后，才传递邮件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-184">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="3fc5c-185">这是建议的值。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-185">This is the recommended value.</span></span>
    - <span data-ttu-id="3fc5c-186">已禁用：如果 URL 扫描无法完成，无论如何都传递邮件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-186">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="3fc5c-187">**Apply 保险箱 Links to email messages sent within the organization**： Enables or disables 保险箱 Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-187">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="3fc5c-188">建议的值已启用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-188">The recommended value is enabled.</span></span>

- <span data-ttu-id="3fc5c-189">**Do not track user clicks**： Enables or disables storing 保险箱 Links click data for URLs clicked in email messages.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-189">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="3fc5c-190">建议的值是保持此设置未选择 (跟踪用户单击) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-190">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="3fc5c-191">目前不支持在内部发件人和内部收件人之间发送的电子邮件中的链接的 URL 单击跟踪。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-191">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="3fc5c-192">**不允许用户单击到原始 URL：** 允许或阻止用户通过警告 [页面](#warning-pages-from-safe-links) 单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-192">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="3fc5c-193">推荐值已启用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-193">The recommend value is enabled.</span></span>

- <span data-ttu-id="3fc5c-194">**在通知和警告页面上** 显示组织品牌：此选项在警告页面上显示组织的品牌。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-194">**Display the organization branding on notification and warning pages**: This option shows your organization's branding on warning pages.</span></span> <span data-ttu-id="3fc5c-195">品牌打造可帮助用户识别合法警告，因为默认 Microsoft 警告页面经常被攻击者使用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-195">Branding helps users identify legitimate warnings, because default Microsoft warning pages are often used by attackers.</span></span> <span data-ttu-id="3fc5c-196">有关自定义品牌打造详细信息，请参阅[自定义Microsoft 365自定义自定义主题](../../admin/setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-196">For more information about customized branding, see [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md).</span></span>

- <span data-ttu-id="3fc5c-197">**不要重写以下 URL：** 保留 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-197">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="3fc5c-198">保留不需要扫描的安全 URL 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-198">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="3fc5c-199">该列表对于每个链接策略保险箱唯一。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-199">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="3fc5c-200">有关"不重写以下 **URL"** 列表的信息，请参阅本文稍后的"保险箱 [链接策略"](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)一节中的"不重写以下 URL"列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-200">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

  <span data-ttu-id="3fc5c-201">有关链接策略的标准策略和严格策略设置的建议值保险箱，请参阅保险箱[链接策略设置。](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-201">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="3fc5c-202">**收件人** 筛选器：需要指定确定策略适用的收件人条件和例外。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-202">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="3fc5c-203">可以将这些属性用于条件和例外：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-203">You can use these properties for conditions and exceptions:</span></span>
  - <span data-ttu-id="3fc5c-204">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-204">**The recipient is**</span></span>
  - <span data-ttu-id="3fc5c-205">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-205">**The recipient domain is**</span></span>
  - <span data-ttu-id="3fc5c-206">**收件人为以下组的成员**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-206">**The recipient is a member of**</span></span>

  <span data-ttu-id="3fc5c-207">一次只能使用一个条件或例外，但条件或例外可以包含多个值。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-207">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="3fc5c-208">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-208">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3fc5c-209">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-209">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="3fc5c-210">**优先级**：如果创建多个策略，可以指定策略的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-210">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="3fc5c-211">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="3fc5c-212">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>
  
### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="3fc5c-213">链接保险箱在电子邮件中的工作方式</span><span class="sxs-lookup"><span data-stu-id="3fc5c-213">How Safe Links works in email messages</span></span>

<span data-ttu-id="3fc5c-214">在高级别上，下面将保险箱链接保护如何作用于电子邮件中的 URL：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-214">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="3fc5c-215">所有电子邮件均通过 EOP，其中 Internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器在邮件传递到收件人邮箱之前。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-215">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="3fc5c-216">用户在邮箱中打开邮件，并单击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-216">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="3fc5c-217">保险箱链接在打开网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-217">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="3fc5c-218">如果 URL 包含在"阻止以下 **URL"** 列表中，将打开 [阻止的 URL](#blocked-url-warning) 警告。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-218">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="3fc5c-219">如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-219">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="3fc5c-220">如果 URL 指向可下载的文件，并且适用于用户的策略中启用了"对指向文件的可疑链接和链接应用实时 **URL** 扫描"设置，则选中可下载的文件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-220">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="3fc5c-221">如果确定 URL 是安全的，将打开网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-221">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="3fc5c-222">保险箱链接设置Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fc5c-222">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3fc5c-223">自 2020 年 3 月起，此功能为预览版，仅提供给 Microsoft Teams Technology Adoption Program (TAP) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-223">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="3fc5c-224">有关发布计划的信息，请查看Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-224">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="3fc5c-225">在链接策略中保险箱或禁用Microsoft Teams链接保险箱保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-225">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="3fc5c-226">具体来说，使用"**选择用于未知或潜在** 恶意 URL 的操作"设置Microsoft Teams URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-226">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="3fc5c-227">建议的值是 **On**。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-227">The recommended value is **On**.</span></span>

<span data-ttu-id="3fc5c-228">电子邮件中保险箱的链接策略中的以下设置也适用于电子邮件中Teams：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-228">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="3fc5c-229">**对指向文件的可疑链接应用实时 URL 扫描**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-229">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="3fc5c-230">**不跟踪用户单击**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-230">**Do not track user clicks**</span></span>
- <span data-ttu-id="3fc5c-231">**不允许用户单击至初始 URL**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-231">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="3fc5c-232">这些设置在之前的电子邮件保险箱[链接设置中进行了介绍](#safe-links-settings-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-232">These settings are explained previously in [Safe Links settings for email messages](#safe-links-settings-for-email-messages).</span></span>

<span data-ttu-id="3fc5c-233">为 Microsoft Teams 启用 保险箱 链接保护后，当受保护的用户单击 (单击链接时，将针对已知恶意链接列表检查 Teams 中的 URL) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-233">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="3fc5c-234">不重写 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-234">URLs are not rewritten.</span></span> <span data-ttu-id="3fc5c-235">如果发现链接是恶意链接，用户将具有以下体验：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-235">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="3fc5c-236">如果在对话、群组Teams或频道中单击了链接，则以下屏幕截图中显示的警告页面将显示在默认 Web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-236">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="3fc5c-237">如果从固定选项卡单击了链接，则警告页面将显示在该选项卡Teams的"页面"界面中。出于安全考虑，禁用在 Web 浏览器中打开链接的选项。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-237">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="3fc5c-238">根据策略中"不允许用户单击到原始 **URL"** 设置的配置方式，用户将允许或不允许单击到原始 URL (是否继续 (屏幕截图) 中不建议) 。 </span><span class="sxs-lookup"><span data-stu-id="3fc5c-238">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="3fc5c-239">我们建议您启用"不允许用户单击访问原始 **URL"** 设置，以便用户无法单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-239">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="3fc5c-240">如果发送链接的用户未包含在启用了 Teams 保护的 保险箱 链接策略中，则用户可以随意单击找到其计算机或设备上的原始 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-240">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![报告保险箱恶意Teams网页的"安全链接"。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="3fc5c-242">单击 **警告页面上的** "返回"按钮将用户返回到其原始上下文或 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-242">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="3fc5c-243">但是，再次单击原始链接将导致保险箱链接重新扫描 URL，因此警告页面将重新出现。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-243">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="3fc5c-244">链接保险箱中的工作原理Teams</span><span class="sxs-lookup"><span data-stu-id="3fc5c-244">How Safe Links works in Teams</span></span>

<span data-ttu-id="3fc5c-245">在高级别上，下面保险箱链接保护如何对网站中的 URL Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-245">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="3fc5c-246">用户启动Teams应用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-246">A user starts the Teams app.</span></span>

2. <span data-ttu-id="3fc5c-247">Microsoft 365验证用户组织是否包括适用于 Office 365 的 Microsoft Defender，以及该用户是否包含在启用了 Microsoft Teams 保护的活动 保险箱 链接策略中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-247">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="3fc5c-248">在用户单击聊天、群聊、频道和选项卡时验证 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-248">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="3fc5c-249">保险箱应用的链接Office 365设置</span><span class="sxs-lookup"><span data-stu-id="3fc5c-249">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="3fc5c-250">保险箱Office 365 应用程序的链接保护会检查 Office 文档中的链接，而不是电子邮件 (但它可以在打开) 后检查电子邮件中附加 Office 文档中的链接。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-250">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="3fc5c-251">保险箱适用于应用Office 365保护具有以下客户端要求：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-251">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="3fc5c-252">Microsoft 365 应用版或Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-252">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="3fc5c-253">Word、Excel 和 PowerPoint、Mac Windows或 Web 浏览器中的当前版本。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-253">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="3fc5c-254">Office iOS 或 Android 设备上的应用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-254">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="3fc5c-255">Visio上Windows。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-255">Visio on Windows.</span></span>
  - <span data-ttu-id="3fc5c-256">OneNote Web 浏览器中显示。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-256">OneNote in a web browser.</span></span>

- <span data-ttu-id="3fc5c-257">Office 365应用配置为使用新式验证。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-257">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="3fc5c-258">有关详细信息，请参阅新式验证如何适用于[Office 2013、Office 2016 和 Office 2019 客户端应用](../../enterprise/modern-auth-for-office-2013-and-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-258">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span>

- <span data-ttu-id="3fc5c-259">用户使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-259">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="3fc5c-260">有关详细信息，请参阅登录[Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-260">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="3fc5c-261">在 保险箱 链接的全局Office 365（而不是在"链接"策略中保险箱为 保险箱 应用配置链接保护。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-261">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="3fc5c-262">保护适用于组织中获得 Defender for Office 365 许可的所有用户，无论这些用户是否包含在活动的 保险箱 链接策略中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-262">The protection is applied to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span>

<span data-ttu-id="3fc5c-263">以下保险箱链接设置可用于Office 365应用：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-263">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="3fc5c-264">**Office 365应用程序**：启用或禁用保险箱支持的链接Office 365扫描。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-264">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="3fc5c-265">默认值和推荐值为 **On。**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-265">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="3fc5c-266">Do **not track when users click 保险箱 Links**： Enables or disables storing 保险箱 Links click data for URLs clicked in the desktop versions Word， Excel， PowerPoint， and Visio.</span><span class="sxs-lookup"><span data-stu-id="3fc5c-266">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="3fc5c-267">建议值为 **Off**，这意味着将跟踪用户点击量。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-267">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="3fc5c-268">不允许用户单击指向原始 URL 的安全链接：允许或阻止用户单击桌面版 Word、Excel、PowerPoint 和 Visio 中的警告页面指向原始 **URL。** [](#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-268">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="3fc5c-269">默认值和推荐值为 **On。**</span><span class="sxs-lookup"><span data-stu-id="3fc5c-269">The default and recommended value is **On**.</span></span>

<span data-ttu-id="3fc5c-270">若要为 保险箱应用配置Office 365链接设置，请参阅为保险箱应用配置Office 365[保护](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-270">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="3fc5c-271">有关"标准"和"严格"策略设置的建议值详细信息，请参阅全局设置["保险箱链接"。](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="3fc5c-271">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="3fc5c-272">保险箱链接在应用中Office 365的工作方式</span><span class="sxs-lookup"><span data-stu-id="3fc5c-272">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="3fc5c-273">在高级别上，下面将保险箱链接保护如何作用于应用中Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-273">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="3fc5c-274">上Office 365介绍了受支持的应用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-274">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="3fc5c-275">用户使用其工作或学校帐户登录包括Microsoft 365 应用版或Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-275">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="3fc5c-276">用户打开并单击支持文档中Office文档的链接Office 应用。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-276">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="3fc5c-277">保险箱链接在打开目标网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-277">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="3fc5c-278">如果 URL 包含在跳过链接扫描列表保险箱阻止 (阻止的 URL) 将打开阻止[的 URL 警告](#blocked-url-warning)页。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-278">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="3fc5c-279">如果 URL 指向已确定为恶意的网站，将打开恶意 (或其他警告[](#malicious-website-warning)) 页面。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-279">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="3fc5c-280">如果 URL 指向可下载的文件，并且适用于用户的 保险箱 链接策略配置为扫描指向可下载内容的链接 (应用实时 **URL** 扫描，以找到指向文件) 的可疑链接和链接，则检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-280">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="3fc5c-281">如果 URL 被视为安全 URL，则用户将访问网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-281">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="3fc5c-282">如果保险箱链接扫描无法完成，保险箱链接保护不会触发。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-282">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="3fc5c-283">在Office客户端中，在用户继续访问目标网站之前，将警告用户。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-283">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="3fc5c-284">在每个会话开始时，可能需要几秒钟来验证用户是否已启用保险箱链接Office。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-284">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="3fc5c-285">链接的"阻止以下 URL"保险箱列表</span><span class="sxs-lookup"><span data-stu-id="3fc5c-285">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="3fc5c-286">"**阻止以下 URL"** 列表定义始终被以下位置保险箱链接扫描阻止的链接：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-286">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="3fc5c-287">电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-287">Email messages.</span></span>
- <span data-ttu-id="3fc5c-288">Office 365和 Mac Windows应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-288">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="3fc5c-289">适用于 iOS Office Android 的 Office 中的文档。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-289">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="3fc5c-290">当活动链接策略中的保险箱单击受支持应用中的阻止链接时，他们会访问阻止[的 URL 警告](#blocked-url-warning)页面。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-290">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="3fc5c-291">您可以在全局设置中为"链接"配置保险箱列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-291">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="3fc5c-292">有关说明，请参阅 [配置"阻止以下 URL"列表](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-292">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="3fc5c-293">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-293">**Notes**:</span></span>

- <span data-ttu-id="3fc5c-294">有关被阻止的 URL 的真正通用列表，请参阅管理 [租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-294">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>
- <span data-ttu-id="3fc5c-295">阻止以下 **URL 列表** 的限制：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-295">Limits for the **Block the following URLs** list:</span></span>
  - <span data-ttu-id="3fc5c-296">最大条目数为 500。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-296">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="3fc5c-297">条目的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-297">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="3fc5c-298">所有条目不能超过 10，000 个字符。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-298">All of the entries can't exceed 10,000 characters.</span></span>
- <span data-ttu-id="3fc5c-299">不要在 URL 末尾添加 `/` () 斜杠。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-299">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="3fc5c-300">例如，使用 `https://www.contoso.com` ，而不是 `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-300">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>
- <span data-ttu-id="3fc5c-301">例如或 (仅域 URL) `contoso.com` `tailspintoys.com` 将阻止包含该域的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-301">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>
- <span data-ttu-id="3fc5c-302">可以阻止子域，但不阻止整个域。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-302">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="3fc5c-303">例如，阻止包含子域的任何 URL，但不阻止包含完整域 `toys.contoso.com*` 的 `contoso.com` URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-303">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>
- <span data-ttu-id="3fc5c-304">每个 URL 条目可以包含最多三 () `*` 通配符。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-304">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="3fc5c-305">"阻止以下 URL"列表的条目语法</span><span class="sxs-lookup"><span data-stu-id="3fc5c-305">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="3fc5c-306">下表介绍了您可以输入的值及其结果的示例：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-306">Examples of the values that you can enter and their results are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="3fc5c-307">值</span><span class="sxs-lookup"><span data-stu-id="3fc5c-307">Value</span></span>|<span data-ttu-id="3fc5c-308">结果</span><span class="sxs-lookup"><span data-stu-id="3fc5c-308">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="3fc5c-309">或</span><span class="sxs-lookup"><span data-stu-id="3fc5c-309">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="3fc5c-310">阻止域、子域和路径。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-310">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="3fc5c-311">例如， `https://www.contoso.com` `https://sub.contoso.com` 、 和 `https://contoso.com/abc` 被阻止。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-311">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="3fc5c-312">阻止 `https://contoso.com/a` 但不阻止其他子路径（如 `https://contoso.com/a/b` ）。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-312">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="3fc5c-313">块 `https://contoso.com/a` 和其他子路径（如 `https://contoso.com/a/b` ）。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-313">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="3fc5c-314">阻止此示例中 (`toys` 子域) 但允许单击其他域 URL (或 `https://contoso.com` `https://home.contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-314">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="3fc5c-315">链接策略中的"不重写保险箱 URL"</span><span class="sxs-lookup"><span data-stu-id="3fc5c-315">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="3fc5c-316">如果组织使用保险箱链接策略，则不重写以下 **URL** 列表是支持的第三方网络钓鱼测试的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-316">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="3fc5c-317">每个保险箱链接策略都包含一个"不重写以下 **URL"** 列表，您可以使用该列表指定未由"链接"扫描保险箱 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-317">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="3fc5c-318">换句话说，该列表允许策略中包含的用户访问指定的 URL，否则，"链接"会保险箱 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-318">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="3fc5c-319">可以在不同的链接策略中配置保险箱列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-319">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="3fc5c-320">策略处理在用户应用第一 (策略后) 可能停止。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-320">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="3fc5c-321">因此，只有一个"不重写以下 **URL"** 列表应用于包含多个活动"链接"策略保险箱用户。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-321">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="3fc5c-322">若要将条目添加到新列表或现有链接保险箱，请参阅 Create 保险箱 Links [policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies)或 Modify 保险箱[Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-322">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="3fc5c-323">**注意**：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-323">**Notes**:</span></span>

- <span data-ttu-id="3fc5c-324">以下客户端无法识别"不重写链接"**策略** 中的保险箱 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-324">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="3fc5c-325">根据以下客户端中链接扫描的结果，可阻止包含在保险箱中的用户访问 URL：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-325">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>
  - <span data-ttu-id="3fc5c-326">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fc5c-326">Microsoft Teams</span></span>
  - <span data-ttu-id="3fc5c-327">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="3fc5c-327">Office web apps</span></span>

  <span data-ttu-id="3fc5c-328">有关任何地方允许的 URL 的真正通用列表，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-328">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="3fc5c-329">请考虑将常用的内部 URL 添加到列表中，以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-329">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="3fc5c-330">例如，如果你有本地服务（如 Skype for Business 或 SharePoint，可以添加这些 URL 以将其从扫描中排除。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-330">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>
- <span data-ttu-id="3fc5c-331">如果"链接"**策略** 中已有"不重写保险箱 URL 条目，请务必查看列表并根据需要添加通配符。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-331">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="3fc5c-332">例如，你的列表有一个类似 的条目 `https://contoso.com/a` ，你稍后决定包括子路径，如 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-332">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="3fc5c-333">不要添加新条目，而是向现有条目添加通配符，以便它成为 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-333">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>
- <span data-ttu-id="3fc5c-334">每个 URL 条目可以包含最多三 () `*` 通配符。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-334">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="3fc5c-335">通配符明确包括前缀或子域。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-335">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="3fc5c-336">例如，条目与 不同，因为允许用户访问指定域中的子域 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` 和路径。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-336">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>
- <span data-ttu-id="3fc5c-337">如果 URL 使用 HTTP 到 HTTPS (（例如，302 重定向到) ）的自动重定向，并且您尝试为列表中的同一 URL 输入 HTTP 和 HTTPS 条目，您可能会注意到第二个 URL 条目将替换第一 `http://www.contoso.com` 个 URL 条目。 `https://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3fc5c-337">If a URL uses automatic redirection for HTTP to HTTPS (for example, 302 redirection for `http://www.contoso.com` to `https://www.contoso.com`), and you try to enter both HTTP and HTTPS entries for the same URL to the list, you might notice that the second URL entry replaces the first URL entry.</span></span> <span data-ttu-id="3fc5c-338">如果 URL 的 HTTP 和 HTTPS 版本是完全独立的，则不会发生此行为。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-338">This behavior does not occur if the HTTP and HTTPS versions of the URL are completely separate.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="3fc5c-339">"不重写以下 URL"列表的条目语法</span><span class="sxs-lookup"><span data-stu-id="3fc5c-339">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="3fc5c-340">下表介绍了您可以输入的值及其结果的示例：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-340">Examples of the values that you can enter and their results are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="3fc5c-341">值</span><span class="sxs-lookup"><span data-stu-id="3fc5c-341">Value</span></span>|<span data-ttu-id="3fc5c-342">结果</span><span class="sxs-lookup"><span data-stu-id="3fc5c-342">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="3fc5c-343">允许访问 `https://contoso.com` 子域或路径，但不能访问子域或路径。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-343">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="3fc5c-344">允许访问域、子域和路径 (例如、 `https://www.contoso.com` `https://www.contoso.com` 或 `https://maps.contoso.com` `https://www.contoso.com/a`) 。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-344">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="3fc5c-345">此条目本质上优于 ，因为它不允许潜在的欺诈性网站 `*contoso.com*` ，如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="3fc5c-345">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="3fc5c-346">允许访问 `https://contoso.com/a` ，但不允许访问子路径（如 ） `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="3fc5c-346">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="3fc5c-347">允许访问 `https://contoso.com/a` 和子路径，如 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="3fc5c-347">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="3fc5c-348">链接中的保险箱页</span><span class="sxs-lookup"><span data-stu-id="3fc5c-348">Warning pages from Safe Links</span></span>

<span data-ttu-id="3fc5c-349">本节包含单击 URL 时由链接保险箱触发的各种警告页面的示例。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-349">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="3fc5c-350">请注意，已更新多个警告页面。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-350">Note that several warning pages have been updated.</span></span> <span data-ttu-id="3fc5c-351">如果还没有看到更新的页面，你很快就会看到。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-351">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="3fc5c-352">更新的页面包括新的配色方案、更多详细信息，以及即使给定警告和建议，仍可以继续访问网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-352">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="3fc5c-353">扫描正在进行通知</span><span class="sxs-lookup"><span data-stu-id="3fc5c-353">Scan in progress notification</span></span>

<span data-ttu-id="3fc5c-354">单击的 URL 正由"链接"保险箱扫描。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-354">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="3fc5c-355">在再次尝试链接之前，可能需要等待片刻。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-355">You might need to wait a few moments before trying the link again.</span></span>

!["正在扫描链接"通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="3fc5c-357">原始通知页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-357">The original notification page looked like this:</span></span>

![原始"正在扫描链接"通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="3fc5c-359">可疑邮件警告</span><span class="sxs-lookup"><span data-stu-id="3fc5c-359">Suspicious message warning</span></span>

<span data-ttu-id="3fc5c-360">单击的 URL 位于类似于其他可疑邮件的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-360">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="3fc5c-361">我们建议您在继续网站之前仔细检查电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-361">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["从可疑邮件单击链接"警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="3fc5c-363">网络钓鱼尝试警告</span><span class="sxs-lookup"><span data-stu-id="3fc5c-363">Phishing attempt warning</span></span>

<span data-ttu-id="3fc5c-364">单击的 URL 位于已标识为网络钓鱼攻击的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-364">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="3fc5c-365">因此，电子邮件中所有 URL 都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-365">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="3fc5c-366">建议您不要继续访问该网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-366">We recommend that you do not proceed to the site.</span></span>

!["从网络钓鱼邮件中单击链接"警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="3fc5c-368">恶意网站警告</span><span class="sxs-lookup"><span data-stu-id="3fc5c-368">Malicious website warning</span></span>

<span data-ttu-id="3fc5c-369">单击的 URL 指向已标识为恶意的网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-369">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="3fc5c-370">建议您不要继续访问该网站。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-370">We recommend that you do not proceed to the site.</span></span>

!["此网站被分类为恶意"警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="3fc5c-372">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-372">The original warning page looked like this:</span></span>

![原始"此网站已分类为恶意"警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning&quot;></a><span data-ttu-id=&quot;3fc5c-374&quot;>阻止的 URL 警告</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3fc5c-374&quot;>Blocked URL warning</span></span>

<span data-ttu-id=&quot;3fc5c-375&quot;>单击的 URL 已被您组织的管理员手动阻止 (&quot;链接") 全局设置中的"阻止 保险箱以下 URL"列表。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-375">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="3fc5c-376">链接未由链接保险箱，因为它已被手动阻止。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-376">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="3fc5c-377">管理员手动阻止特定 URL 的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-377">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="3fc5c-378">如果认为不应阻止网站，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-378">If you think the site should not be blocked, contact your admin.</span></span>

!["此网站被管理员阻止"警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="3fc5c-380">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-380">The original warning page looked like this:</span></span>

![原始"根据组织的 URL 策略阻止此网站"警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="3fc5c-382">错误警告</span><span class="sxs-lookup"><span data-stu-id="3fc5c-382">Error warning</span></span>

<span data-ttu-id="3fc5c-383">发生了某种错误，无法打开 URL。</span><span class="sxs-lookup"><span data-stu-id="3fc5c-383">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["无法加载您尝试访问的页面"警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="3fc5c-385">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fc5c-385">The original warning page looked like this:</span></span>

![原始"无法加载此网页"警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
