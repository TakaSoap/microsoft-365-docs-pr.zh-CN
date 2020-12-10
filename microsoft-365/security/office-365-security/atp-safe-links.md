---
title: 安全链接
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
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
description: 在本文中，管理员可以了解 Office 365 的 Defender 中的安全链接保护，以保护其组织免受使用恶意 Url 的网络钓鱼和其他攻击的攻击。
ms.openlocfilehash: f2a747b0776a16ac981158ab866f28699583a06b
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616316"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a8ec5-103">Microsoft Defender for Office 365 中的安全链接</span><span class="sxs-lookup"><span data-stu-id="a8ec5-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="a8ec5-104">本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="a8ec5-105">如果使用的是 Outlook.com、Microsoft 365 系列或 Microsoft 365 个人，并且要在 Outlook 中查找有关 Safelinks 的信息，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-105">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="a8ec5-106">安全链接是在 [Office 365 的 Defender](office-365-atp.md) 中的一项功能，可提供邮件流中的入站电子邮件的 URL 扫描和重写，以及电子邮件和其他位置中的 url 和链接的单击时验证时间。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-106">Safe Links is a feature in [Defender for Office 365](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="a8ec5-107">除了 Exchange Online Protection (EOP) 中的入站电子邮件 [和反恶意软件保护](anti-spam-and-anti-malware-protection.md) 之外，还会对安全链接进行扫描。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-107">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a8ec5-108">安全链接扫描可帮助保护您的组织免受网络钓鱼和其他攻击中使用的恶意链接的攻击。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-108">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="a8ec5-109">安全链接保护在以下位置可用：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-109">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="a8ec5-110">**电子邮件**：对电子邮件中的链接的安全链接保护由安全链接策略控制。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-110">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="a8ec5-111">没有默认安全链接策略，因此， **若要获取电子邮件中安全链接的保护，您需要创建一个或多个安全链接策略**。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-111">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="a8ec5-112">有关说明，请参阅 [在 Microsoft Defender For Office 365 中设置安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="a8ec5-113">有关电子邮件的安全链接保护的详细信息，请参阅本文后面的 "电子邮件的 [安全链接设置](#safe-links-settings-for-email-messages) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-113">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="a8ec5-114">**Microsoft 团队** (当前位于点击预览) ：对团队对话、组聊天或频道中的链接的安全链接保护也受安全链接策略控制。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-114">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="a8ec5-115">没有默认安全链接策略，因此， **若要在团队中获取安全链接的保护，您需要创建一个或多个安全链接策略**。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-115">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="a8ec5-116">有关团队中的安全链接保护的详细信息，请参阅本主题后面的 " [Microsoft 团队的安全链接设置](#safe-links-settings-for-microsoft-teams) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-116">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this topic.</span></span>

- <span data-ttu-id="a8ec5-117">**Office 365 应用程序**： office 365 应用程序的安全链接保护在受支持的桌面、移动设备和 web 接入点中可用。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-117">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="a8ec5-118">在不安全链接策略 **之外** 的全局设置中为 Office 365 应用程序 **配置** 安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-118">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="a8ec5-119">有关说明，请参阅 [在 Microsoft Defender For Office 365 中配置安全链接设置的全局设置](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-119">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="a8ec5-120">但是，对 Office 365 应用程序的安全链接保护仅 **适用** 于包含在活动安全链接策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-120">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="a8ec5-121">如果用户不包含在活动的安全链接策略中，则用户不会在受支持的 Office 365 应用程序中获取安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-121">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="a8ec5-122">有关 Office 365 应用程序中的安全链接保护的详细信息，请参阅本文后面的 " [office 365 应用程序的安全链接设置](#safe-links-settings-for-office-365-apps) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-122">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="a8ec5-123">本文包括以下类型的安全链接设置的详细说明：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-123">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="a8ec5-124">**安全链接策略中的设置**：这些设置仅适用于特定策略中包含的用户，并且这些设置在策略之间可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-124">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="a8ec5-125">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-125">These settings include:</span></span>

  - [<span data-ttu-id="a8ec5-126">电子邮件的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-126">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="a8ec5-127">Microsoft 团队的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-127">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="a8ec5-128">"安全链接策略" 中的 "不重写以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="a8ec5-128">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="a8ec5-129">**全局安全链接设置**：这些设置在全局范围内配置，而不是在安全链接策略中进行配置。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-129">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="a8ec5-130">但是，这些设置仅适用于包含在活动安全链接策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-130">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="a8ec5-131">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-131">These settings include:</span></span>

  - [<span data-ttu-id="a8ec5-132">Office 365 应用程序的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-132">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="a8ec5-133">安全链接的 "阻止以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="a8ec5-133">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="a8ec5-134">下表介绍了 Microsoft 365 和 Office 365 组织中的安全链接的应用场景，其中包括适用于 Office 的 Defender 365 (换句话说，缺少许可不是示例) 中的一个问题。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-134">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="a8ec5-135">方案</span><span class="sxs-lookup"><span data-stu-id="a8ec5-135">Scenario</span></span>|<span data-ttu-id="a8ec5-136">结果</span><span class="sxs-lookup"><span data-stu-id="a8ec5-136">Result</span></span>|
|---|---|
|<span data-ttu-id="a8ec5-137">Jean 是市场营销部门的成员。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-137">Jean is a member of the marketing department.</span></span> <span data-ttu-id="a8ec5-138">针对 Office 365 应用程序的安全链接保护在安全链接的全局设置中处于打开状态，并且存在适用于市场营销部门成员的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-138">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="a8ec5-139">Jean 在电子邮件中打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-139">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="a8ec5-140">Jean 受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-140">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="a8ec5-141">Jean 包含在安全链接策略中，并且启用了对 Office 365 应用的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-141">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="a8ec5-142">有关 Office 365 应用程序中的安全链接保护要求的详细信息，请参阅本文后面的 " [office 365 应用程序的安全链接设置](#safe-links-settings-for-office-365-apps) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-142">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="a8ec5-143">丽丽的 Microsoft 365 E5 组织没有配置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-143">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="a8ec5-144">Chris 收到来自外部发件人的电子邮件，其中包含最终单击的恶意网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-144">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="a8ec5-145">丽丽不受安全链接的保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-145">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="a8ec5-146">管理员必须至少为任何人创建一个安全链接策略，以在入站电子邮件中获取安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-146">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="a8ec5-147">若要获取安全链接保护，必须在策略条件中包含 Chris。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-147">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="a8ec5-148">在 Pat 的组织中，没有管理员创建任何安全链接策略，但启用了针对 Office 365 应用的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-148">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="a8ec5-149">Pat 打开 Word 文档并单击文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-149">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="a8ec5-150">Pat 不受安全链接的保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-150">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="a8ec5-151">尽管 Office 365 应用程序的安全链接保护是全局打开的，但 Pat 不包含在任何活动的安全链接策略中，因此无法应用保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-151">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="a8ec5-152">在工作先生的组织中，在 `https://tailspintoys.com` 安全链接的全局设置中的 " **阻止以下 url** " 列表中配置。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-152">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="a8ec5-153">包含 "已加入" 的安全链接策略已存在。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-153">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="a8ec5-154">先生接收包含 URL 的电子邮件 `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-154">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="a8ec5-155">先生单击 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-155">Lee clicks the URL.</span></span>|<span data-ttu-id="a8ec5-156">可能会自动阻止该 URL。这取决于列表中的 URL 条目和已使用的电子邮件客户端。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-156">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="a8ec5-157">有关详细信息，请参阅本主题后面的 ["阻止以下 url" 安全链接的列表](#block-the-following-urls-list-for-safe-links) "一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-157">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this topic.</span></span>|
|<span data-ttu-id="a8ec5-158">晓明和 Julia 都适用于 contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-158">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="a8ec5-159">很长时间之前，管理员配置了适用于晓明和 Julia 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-159">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="a8ec5-160">晓明将向 Julia 发送一封电子邮件，而不知道该电子邮件包含恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-160">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="a8ec5-161">**如果** 应用于她的安全链接策略被配置为应用于内部收件人之间的邮件，则 Julia 受安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-161">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="a8ec5-162">有关详细信息，请参阅本主题后面的 "电子邮件的 [安全链接设置](#safe-links-settings-for-email-messages) " 一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-162">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this topic.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="a8ec5-163">电子邮件的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-163">Safe Links settings for email messages</span></span>

<span data-ttu-id="a8ec5-164">安全链接扫描传入电子邮件中的已知恶意超链接。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-164">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="a8ec5-165">使用 Microsoft 标准 URL 前缀重写扫描的 Url： `https://nam01.safelinks.protection.outlook.com` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-165">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="a8ec5-166">重写链接后，将对其进行分析以查找潜在的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-166">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="a8ec5-167">安全链接重写 URL 后，即使邮件转发或答复，URL 仍将被重写。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-167">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="a8ec5-168">不会重写在转发或答复的邮件中添加的其他链接。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-168">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="a8ec5-169">以下列表介绍了适用于电子邮件的安全链接策略中的设置：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-169">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="a8ec5-170">**选择邮件中未知的潜在恶意 url 的操作**：启用或禁用电子邮件中的安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-170">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="a8ec5-171">建议的值为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-171">The recommended value is **On**.</span></span> <span data-ttu-id="a8ec5-172">启用此设置将导致以下操作。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-172">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="a8ec5-173">Outlook (C2R) 在 Windows 上启用安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-173">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="a8ec5-174">重写 Url，并在用户单击邮件中的 Url 时通过安全链接保护来路由用户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-174">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="a8ec5-175">单击时，将对照已知恶意 Url 的列表和 ["阻止以下 url" 列表](#block-the-following-urls-list-for-safe-links)检查 url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-175">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="a8ec5-176">没有有效信誉的 Url 将在后台以异步方式触发。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-176">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="a8ec5-177">**对指向文件的可疑链接和链接应用实时 URL 扫描**：启用对链接的实时扫描，包括指向可下载内容的电子邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-177">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="a8ec5-178">已启用建议的值。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-178">The recommended value is enabled.</span></span>

  - <span data-ttu-id="a8ec5-179">**等待 URL 扫描完成后再传递邮件**：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-179">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="a8ec5-180">已启用：包含 Url 的邮件将一直保留到扫描完成为止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-180">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="a8ec5-181">仅在将 Url 确认为安全之后，才会传递邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-181">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="a8ec5-182">这是建议的值。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-182">This is the recommended value.</span></span>
    - <span data-ttu-id="a8ec5-183">已禁用：如果无法完成 URL 扫描，则发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-183">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="a8ec5-184">**将安全链接应用于在组织内发送的电子邮件**：启用或禁用安全链接扫描在同一 Exchange Online 组织中的内部发件人和内部收件人之间发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-184">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="a8ec5-185">已启用建议的值。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-185">The recommended value is enabled.</span></span>

- <span data-ttu-id="a8ec5-186">**不跟踪用户单击**：启用或禁用存储安全链接单击电子邮件中单击的 url 的数据。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-186">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="a8ec5-187">建议的值是将此设置保留为未选中状态 (跟踪用户单击) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-187">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="a8ec5-188">URL 单击 "跟踪" 以查找内部发件人和内部收件人之间发送的电子邮件中的链接当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-188">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="a8ec5-189">**不允许用户单击到原始 url**：允许或阻止用户通过单击 [警告页](#warning-pages-from-safe-links) 到原始 url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-189">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="a8ec5-190">建议值为已启用。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-190">The recommend value is enabled.</span></span>

- <span data-ttu-id="a8ec5-191">**请勿重写以下 url**：保留 url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-191">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="a8ec5-192">保留一个不需要扫描的安全 Url 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-192">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="a8ec5-193">此列表对于每个安全链接策略都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-193">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="a8ec5-194">有关 "不 **重写以下 url** " 列表的详细信息，请参阅本文后面的 ["不重写以下 Url" 安全链接策略中的列表](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) "一节。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-194">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="a8ec5-195">有关安全链接策略的标准策略设置和严格策略设置的建议值的详细信息，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-195">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="a8ec5-196">**收件人筛选器**：需要指定用于确定策略适用于的收件人条件和例外。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-196">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="a8ec5-197">您可以将这些属性用于条件和例外：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-197">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="a8ec5-198">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-198">**The recipient is**</span></span>
  - <span data-ttu-id="a8ec5-199">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-199">**The recipient domain is**</span></span>
  - <span data-ttu-id="a8ec5-200">**收件人为以下组的成员**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-200">**The recipient is a member of**</span></span>

  <span data-ttu-id="a8ec5-201">只能使用条件或例外一次，但条件或例外可以包含多个值。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-201">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="a8ec5-202">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-202">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a8ec5-203">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-203">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="a8ec5-204">**优先级**：如果创建多个策略，则可以指定它们的应用顺序。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-204">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="a8ec5-205">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-205">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="a8ec5-206">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-206">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="a8ec5-207">安全链接在电子邮件中的工作方式</span><span class="sxs-lookup"><span data-stu-id="a8ec5-207">How Safe Links works in email messages</span></span>

<span data-ttu-id="a8ec5-208">在较高的层次上，以下是安全链接保护对电子邮件中的 Url 的处理方式：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-208">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="a8ec5-209">所有电子邮件都通过 EOP，其中 internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器，然后将邮件传递到收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-209">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="a8ec5-210">用户在其邮箱中打开邮件，然后单击邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-210">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="a8ec5-211">安全链接在打开网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-211">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="a8ec5-212">如果 URL 包含在 " **阻止以下 url** " 列表中，则会打开一个 [阻止的 URL 警告](#blocked-url-warning) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-212">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="a8ec5-213">如果 URL 指向已确定为 "恶意" 的网站，则会出现 " [恶意网站警告](#malicious-website-warning) " 页 (或) 打开 "其他警告" 页面。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-213">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="a8ec5-214">如果该 URL 指向一个可下载文件，并且应用于该用户的策略中启用了指向 "文件" 设置的 " **应用实时 URL 扫描" 和 "指向文件** 设置的链接"，则会检查下载的文件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-214">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="a8ec5-215">如果确定该 URL 是安全的，则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-215">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="a8ec5-216">Microsoft 团队的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-216">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8ec5-217">从2020年3月起，此功能处于预览阶段，仅适用于 Microsoft 团队技术采用计划的成员 (点击) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-217">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="a8ec5-218">有关发布计划的信息，请参阅 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-218">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="a8ec5-219">在安全链接策略中启用或禁用对 Microsoft 团队的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-219">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="a8ec5-220">具体来说，您可以使用 " **选择对 Microsoft 团队中的未知或可能有害的 url 执行操作** " 设置。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-220">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="a8ec5-221">建议的值为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-221">The recommended value is **On**.</span></span>

<span data-ttu-id="a8ec5-222">适用于电子邮件中的链接的安全链接策略中的以下设置也适用于团队中的链接：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-222">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="a8ec5-223">**对指向文件的可疑链接和链接应用实时 URL 扫描**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-223">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="a8ec5-224">**不跟踪用户点击**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-224">**Do not track user clicks**</span></span>
- <span data-ttu-id="a8ec5-225">**不允许用户单击到原始 URL**</span><span class="sxs-lookup"><span data-stu-id="a8ec5-225">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="a8ec5-226">前面的 " [电子邮件安全链接设置](#safe-links-settings-for-email-messages) " 部分对这些设置进行了说明。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-226">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="a8ec5-227">打开 Microsoft 团队的安全链接保护后，在受保护的用户单击链接时，将根据已知恶意链接列表检查团队中的 Url (单击) 的保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-227">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="a8ec5-228">不重写 Url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-228">URLs are not rewritten.</span></span> <span data-ttu-id="a8ec5-229">如果发现链接是恶意的，用户将有以下体验：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-229">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="a8ec5-230">如果在团队对话、分组聊天或频道中单击了链接，下面的屏幕截图中所示的警告页将显示在默认 web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-230">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="a8ec5-231">如果从固定的选项卡单击了链接，则警告页将出现在该选项卡中的 "团队" 界面中。由于安全原因，在 web 浏览器中打开链接的选项被禁用。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-231">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="a8ec5-232">根据配置策略中的 " **不允许用户单击到原始 url** " 设置的方式，将不允许用户在原始 url 中单击，否则将不允许 (**继续 (不建议** 在屏幕截图) 中) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-232">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="a8ec5-233">建议您启用 " **不允许用户单击到原始 url** 设置"，以便用户无法单击原始 url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-233">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="a8ec5-234">如果发送链接的用户未包含在启用团队保护的安全链接策略中，则用户可以在其计算机或设备上的原始 URL 中随意单击。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-234">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![报告恶意链接的工作组页面的安全链接。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="a8ec5-236">单击 "警告" 页上的 "返回" 按钮 **将把用户** 返回到其原始的上下文或 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-236">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="a8ec5-237">但是，再次单击原始链接将导致重新扫描 URL 的安全链接，因此警告页将重新出现。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-237">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="a8ec5-238">安全链接在团队中的工作方式</span><span class="sxs-lookup"><span data-stu-id="a8ec5-238">How Safe Links works in Teams</span></span>

<span data-ttu-id="a8ec5-239">在较高的层次上，以下是 Microsoft 团队中的 Url 的安全链接保护的工作方式：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-239">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="a8ec5-240">用户启动 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-240">A user starts the Teams app.</span></span>

2. <span data-ttu-id="a8ec5-241">Microsoft 365 验证用户的组织是否包含 Microsoft Defender for Office 365，以及该用户是否包含在启用 Microsoft 团队保护的活动安全链接策略中。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-241">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="a8ec5-242">在聊天、群研讨、频道和选项卡中单击用户时，将对 Url 进行验证。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-242">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="a8ec5-243">Office 365 应用程序的安全链接设置</span><span class="sxs-lookup"><span data-stu-id="a8ec5-243">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="a8ec5-244">针对 Office 365 应用程序的安全链接保护将检查 Office 文档中的链接，而不是电子邮件中的链接 (，但它可以检查电子邮件中附加的 Office 文档中的链接，) 中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-244">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="a8ec5-245">适用于 Office 365 应用程序的安全链接保护具有以下客户端要求：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-245">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="a8ec5-246">Microsoft 365 应用或 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-246">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="a8ec5-247">Windows、Mac 或 web 浏览器上的当前版本的 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-247">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="a8ec5-248">IOS 或 Android 设备上的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-248">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="a8ec5-249">Windows 上的 Visio。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-249">Visio on Windows.</span></span>
  - <span data-ttu-id="a8ec5-250">在 web 浏览器中的 OneNote。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-250">OneNote in a web browser.</span></span>

- <span data-ttu-id="a8ec5-251">Office 365 应用程序配置为使用新式验证。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-251">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="a8ec5-252">有关详细信息，请参阅 [如何在 office 2013、office 2016 和 office 2019 客户端应用程序中运行新式验证](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-252">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="a8ec5-253">用户使用其工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-253">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="a8ec5-254">有关详细信息，请参阅 [登录 Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-254">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="a8ec5-255">为安全链接的全局设置（而不是安全链接策略）中的 Office 365 应用程序配置安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-255">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="a8ec5-256">但是，为了能够应用 Office 365 应用程序的安全链接保护，打开 Office 文档并单击链接的用户必须包含在活动的安全链接策略中。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-256">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="a8ec5-257">以下安全链接设置适用于 Office 365 应用：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-257">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="a8ec5-258">**Office 365 应用程序**：启用或禁用在受支持的 Office 365 应用程序中进行安全链接扫描。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-258">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="a8ec5-259">默认值和建议值为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-259">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="a8ec5-260">**在用户单击安全链接时不进行跟踪**：启用或禁用存储安全链接单击在桌面版本 Word、Excel、PowerPoint 和 Visio 中单击的 url 的数据。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-260">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="a8ec5-261">建议的值为 **Off**，这表示跟踪用户单击。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-261">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="a8ec5-262">**不允许用户单击 "通过指向原始 url 的安全链接"**：允许或阻止用户在桌面版本 Word、Excel、PowerPoint 和 Visio 中的原始 url 中单击，以在 [网页](#warning-pages-from-safe-links) 中单击。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-262">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="a8ec5-263">默认值和建议值为 **"开**"。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-263">The default and recommended value is **On**.</span></span>

<span data-ttu-id="a8ec5-264">若要为 Office 365 应用程序配置安全链接设置，请参阅 [Configure Safe links protection For office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-264">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="a8ec5-265">有关标准策略设置和严格策略设置的推荐值的详细信息，请参阅 [安全链接的全局设置](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-265">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="a8ec5-266">安全链接在 Office 365 应用程序中的工作方式</span><span class="sxs-lookup"><span data-stu-id="a8ec5-266">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="a8ec5-267">在较高的层次上，以下是安全链接保护对 Office 365 应用中的 Url 的工作方式。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-267">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="a8ec5-268">上一节中介绍了受支持的 Office 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-268">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="a8ec5-269">用户在包含 Microsoft 365 应用或 Microsoft 365 商业高级版的组织中使用其工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-269">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="a8ec5-270">用户打开并单击链接到受支持的 Office 应用程序中的 Office 文档。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-270">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="a8ec5-271">安全链接在打开目标网站之前立即检查 URL：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-271">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="a8ec5-272">如果 URL 包含在跳过安全链接扫描的列表中 (**阻止以下 url** 列表) 将打开 " [阻止的 url 警告](#blocked-url-warning) " 页。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-272">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="a8ec5-273">如果 URL 指向已确定为 "恶意" 的网站，则会出现 " [恶意网站警告](#malicious-website-warning) " 页 (或) 打开 "其他警告" 页面。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-273">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="a8ec5-274">如果该 URL 指向一个可下载文件，并且应用于该用户的安全链接策略已配置为扫描到可下载内容的链接， (会对 **指向文件) 的可疑链接和链接应用实时 URL 扫描，同时** 会检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-274">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="a8ec5-275">如果该 URL 被认为是安全的，则会将用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-275">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="a8ec5-276">如果安全链接扫描无法完成，则安全链接保护不会触发。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-276">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="a8ec5-277">在 Office 桌面客户端中，用户将收到警告，然后再继续转到目标网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-277">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ec5-278">在每个会话开始时可能需要几秒钟的时间来验证用户是否已启用 Office 的安全链接。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-278">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="a8ec5-279">安全链接的 "阻止以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="a8ec5-279">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="a8ec5-280">**Block 以下 url** 列表定义了以下位置中的安全链接扫描始终阻止的链接：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-280">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="a8ec5-281">电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-281">Email messages.</span></span>
- <span data-ttu-id="a8ec5-282">Windows 和 Mac 中的 Office 365 应用中的文档。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-282">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="a8ec5-283">Office for iOS 和 Android 中的文档。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-283">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="a8ec5-284">当活动安全链接策略中的用户在受支持的应用程序中单击被阻止的链接时，将转到 " [阻止的 URL 警告](#blocked-url-warning) " 页。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-284">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="a8ec5-285">可以在安全链接的全局设置中配置 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-285">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="a8ec5-286">有关说明，请参阅 [Configure the "Block 以下 url" 列表](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-286">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="a8ec5-287">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-287">**Notes**:</span></span>

- <span data-ttu-id="a8ec5-288">有关在任何位置阻止的真正通用的 Url 列表，请参阅 [在租户允许/阻止列表中管理 url](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-288">For a truly universal list of URLs that are blocked everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="a8ec5-289">限额</span><span class="sxs-lookup"><span data-stu-id="a8ec5-289">Limits:</span></span>
  - <span data-ttu-id="a8ec5-290">最大条目数为500。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-290">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="a8ec5-291">条目的最大长度为128个字符。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-291">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="a8ec5-292">所有条目都不能超过10000个字符。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-292">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="a8ec5-293">不要在 URL 的末尾包含正斜杠 (`/`) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-293">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="a8ec5-294">例如，使用 `https://www.contoso.com` ，not `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-294">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="a8ec5-295">例如 "仅域"-"URL (" `contoso.com` 或 " `tailspintoys.com`) " 将阻止包含域的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-295">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="a8ec5-296">您可以阻止子域，而不阻止整个域。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-296">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="a8ec5-297">例如， `toys.contoso.com*` 阻止包含子域的任何 url，但它不会阻止包含完整域的 url `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-297">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="a8ec5-298">每个 URL 条目最长可包含三个通配符 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-298">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="a8ec5-299">"阻止以下 Url" 列表的输入语法</span><span class="sxs-lookup"><span data-stu-id="a8ec5-299">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="a8ec5-300">下表介绍了您可以输入的值的示例及其结果：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-300">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="a8ec5-301">值</span><span class="sxs-lookup"><span data-stu-id="a8ec5-301">Value</span></span>|<span data-ttu-id="a8ec5-302">结果</span><span class="sxs-lookup"><span data-stu-id="a8ec5-302">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="a8ec5-303">或</span><span class="sxs-lookup"><span data-stu-id="a8ec5-303">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="a8ec5-304">阻止域、子域和路径。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-304">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="a8ec5-305">例如、、 `https://www.contoso.com` `https://sub.contoso.com` 和 `https://contoso.com/abc` 将被阻止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-305">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="a8ec5-306">块 `https://contoso.com/a` ，但不是其他子路径（如） `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-306">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="a8ec5-307">块 `https://contoso.com/a` 和其他子路径（如） `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-307">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="a8ec5-308">`toys`在此示例中阻止子域 () 但允许单击其他域 url (如 `https://contoso.com` 或 `https://home.contoso.com`) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-308">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="a8ec5-309">"安全链接策略" 中的 "不重写以下 Url" 列表</span><span class="sxs-lookup"><span data-stu-id="a8ec5-309">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="a8ec5-310">如果您的组织使用安全链接策略，则不会 **重写以下 url** 列表，这是第三方仿冒测试的唯一受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-310">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="a8ec5-311">每个安全链接策略包含 **"不重写以下 url"** 列表，可用于指定不是由安全链接扫描重写的 url。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-311">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="a8ec5-312">换句话说，此列表允许包含在该策略中的用户访问指定的 Url，该 Url 将被安全链接阻止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-312">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="a8ec5-313">您可以在不同的安全链接策略中配置不同的列表。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-313">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="a8ec5-314">策略处理在第一 (之后停止，最高优先级的) 策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-314">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="a8ec5-315">因此，只有一个 **不重写以下 url** 列表应用于包含在多个活动安全链接策略中的用户。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-315">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="a8ec5-316">若要将条目添加到新的或现有安全链接策略的列表中，请参阅 [创建安全链接策略](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 或 [修改安全链接策略](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-316">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="a8ec5-317">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-317">**Notes**:</span></span>

- <span data-ttu-id="a8ec5-318">以下客户端无法识别 "在安全链接策略中不 **重写以下 url"** 列表。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-318">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="a8ec5-319">可以阻止策略中包含的用户基于在这些客户端中的安全链接扫描结果来访问 Url：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-319">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="a8ec5-320">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8ec5-320">Microsoft Teams</span></span>
  - <span data-ttu-id="a8ec5-321">Office web apps</span><span class="sxs-lookup"><span data-stu-id="a8ec5-321">Office web apps</span></span>

  <span data-ttu-id="a8ec5-322">有关允许随处使用的 Url 的真正通用列表，请参阅 [在租户允许/阻止列表中管理 url](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-322">For a truly universal list of URLs that are allowed everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="a8ec5-323">考虑将常用的内部 Url 添加到列表中，以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-323">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="a8ec5-324">例如，如果您有本地服务（如 Skype for Business 或 SharePoint），则可以添加这些 Url 以将其排除在扫描之外。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-324">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="a8ec5-325">如果您已不重写安全链接策略中 **的以下 url** 条目，请务必查看列表并根据需要添加通配符。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-325">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="a8ec5-326">例如，您的列表有类似的条目， `https://contoso.com/a` 后来决定包含类似的子路径 `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-326">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="a8ec5-327">不添加新条目，而是将通配符添加到现有条目中，使其变得如此 `https://contoso.com/a/*` 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-327">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="a8ec5-328">每个 URL 条目最长可包含三个通配符 (`*`) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-328">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="a8ec5-329">通配符显式包含前缀或子域。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-329">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="a8ec5-330">例如，输入项与 `contoso.com` 不同 `*.contoso.com/*` ，因为 `*.contoso.com/*` 允许用户访问指定域中的子域和路径。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-330">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="a8ec5-331">"不重写以下 Url" 列表的输入语法</span><span class="sxs-lookup"><span data-stu-id="a8ec5-331">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="a8ec5-332">下表介绍了您可以输入的值的示例及其结果：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-332">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="a8ec5-333">值</span><span class="sxs-lookup"><span data-stu-id="a8ec5-333">Value</span></span>|<span data-ttu-id="a8ec5-334">结果</span><span class="sxs-lookup"><span data-stu-id="a8ec5-334">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="a8ec5-335">允许访问（ `https://contoso.com` 而非子域或路径）。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-335">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="a8ec5-336">允许访问域、子域和路径 (例如，、、 `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` 或 `https://www.contoso.com/a`) 。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-336">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="a8ec5-337">此条目的本质上优于 `*contoso.com*` ，因为它不允许潜在的欺诈网站，如 `https://www.falsecontoso.com` 或 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="a8ec5-337">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="a8ec5-338">允许访问 `https://contoso.com/a` ，但不允许像这样的子路径 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="a8ec5-338">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="a8ec5-339">允许访问 `https://contoso.com/a` 和子路径，如 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="a8ec5-339">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="a8ec5-340">来自安全链接的警告页面</span><span class="sxs-lookup"><span data-stu-id="a8ec5-340">Warning pages from Safe Links</span></span>

<span data-ttu-id="a8ec5-341">此部分包含在单击 URL 时安全链接保护触发的各种警告页面的示例。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-341">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="a8ec5-342">请注意，已更新几个警告页面。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-342">Note that several warning pages have been updated.</span></span> <span data-ttu-id="a8ec5-343">如果您还没有看到更新的页面，很快就会了。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-343">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="a8ec5-344">更新的页面包括新的配色方案、更多的详细信息，以及在给定警告和建议的情况下能够继续使用网站的功能。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-344">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="a8ec5-345">扫描正在进行的通知</span><span class="sxs-lookup"><span data-stu-id="a8ec5-345">Scan in progress notification</span></span>

<span data-ttu-id="a8ec5-346">安全链接正在扫描单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-346">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="a8ec5-347">您可能需要等待几分钟，然后再次尝试链接。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-347">You might need to wait a few moments before trying the link again.</span></span>

!["正在扫描链接" 通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="a8ec5-349">原始通知页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-349">The original notification page looked like this:</span></span>

![原始 "正在扫描链接" 通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="a8ec5-351">可疑邮件警告</span><span class="sxs-lookup"><span data-stu-id="a8ec5-351">Suspicious message warning</span></span>

<span data-ttu-id="a8ec5-352">单击的 URL 位于类似于其他可疑邮件的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-352">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="a8ec5-353">建议您先仔细检查电子邮件，然后再继续转到网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-353">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["从可疑邮件单击链接" 警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="a8ec5-355">网络钓鱼尝试警告</span><span class="sxs-lookup"><span data-stu-id="a8ec5-355">Phishing attempt warning</span></span>

<span data-ttu-id="a8ec5-356">单击的 URL 位于已标识为 "网络钓鱼" 攻击的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-356">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="a8ec5-357">因此，电子邮件中的所有 Url 都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-357">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="a8ec5-358">我们建议您不要继续转到网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-358">We recommend that you do not proceed to the site.</span></span>

!["从仿冒邮件单击链接" 警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="a8ec5-360">恶意网站警告</span><span class="sxs-lookup"><span data-stu-id="a8ec5-360">Malicious website warning</span></span>

<span data-ttu-id="a8ec5-361">单击的 URL 指向已被标识为恶意的网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-361">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="a8ec5-362">我们建议您不要继续转到网站。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-362">We recommend that you do not proceed to the site.</span></span>

!["此网站被分类为恶意" 警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="a8ec5-364">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-364">The original warning page looked like this:</span></span>

![原始 "此网站已被分类为恶意" 警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="a8ec5-366">阻止的 URL 警告</span><span class="sxs-lookup"><span data-stu-id="a8ec5-366">Blocked URL warning</span></span>

<span data-ttu-id="a8ec5-367">您的组织中的管理员已手动阻止单击的 URL (在 "安全链接) 的全局设置" 中 **阻止以下 url** 列表。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-367">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="a8ec5-368">安全链接未扫描链接，因为它已被手动阻止。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-368">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="a8ec5-369">管理员手动阻止特定 Url 的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-369">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="a8ec5-370">如果您认为不应阻止该网站，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-370">If you think the site should not be blocked, contact your admin.</span></span>

!["此网站被管理员阻止" 警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="a8ec5-372">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-372">The original warning page looked like this:</span></span>

![原始 "此网站已根据组织的 URL 策略被阻止" 警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="a8ec5-374">错误警告</span><span class="sxs-lookup"><span data-stu-id="a8ec5-374">Error warning</span></span>

<span data-ttu-id="a8ec5-375">出现了某种类型的错误，无法打开该 URL。</span><span class="sxs-lookup"><span data-stu-id="a8ec5-375">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["无法加载您尝试访问的页面" 警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="a8ec5-377">原始警告页面如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8ec5-377">The original warning page looked like this:</span></span>

![原始 "无法加载此网页" 警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
