---
title: 演练-欺骗性的智能洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理员可以了解欺骗性智能洞察力的工作原理。 他们可以快速确定哪些发件人将电子邮件直接发送到其组织，而不是将电子邮件身份验证检查 (SPF、DKIM 或 DMARC) 的域。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920474"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="779ee-104">演练-Microsoft Defender for Office 365 中的欺骗智能洞察力</span><span class="sxs-lookup"><span data-stu-id="779ee-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="779ee-105">在使用拥有 Defender for Office 365 的 Microsoft 365 组织中，您可以使用欺骗智能洞察力快速确定哪些发件人合法向您发送未经身份验证的电子邮件 (来自不通过 SPF、DKIM 或 DMARC 检查的域的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="779ee-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="779ee-106">通过允许已知发件人从已知位置发送欺骗邮件，可以减少误报 (被标记为坏) 的良好电子邮件。</span><span class="sxs-lookup"><span data-stu-id="779ee-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="779ee-107">通过监视允许的欺骗性发件人，您可以提供额外的安全层来防止不安全的邮件到达您的组织中。</span><span class="sxs-lookup"><span data-stu-id="779ee-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="779ee-108">有关报告和见解的详细信息，请参阅 [Security & 合规性中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="779ee-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="779ee-109">本演练是安全 & 合规中心的几个演练之一。</span><span class="sxs-lookup"><span data-stu-id="779ee-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="779ee-110">若要导航报告和见解，请参阅 [相关主题](#related-topics) 部分中的演练。</span><span class="sxs-lookup"><span data-stu-id="779ee-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="779ee-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="779ee-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="779ee-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="779ee-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="779ee-113">若要直接转到 **安全仪表板** 页面，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="779ee-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="779ee-114">您可以从安全 & 合规中心的多个仪表板中查看欺骗性智能洞察力。</span><span class="sxs-lookup"><span data-stu-id="779ee-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="779ee-115">无论您正在查看哪个仪表板，真知灼见都会提供相同的详细信息，并允许您快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="779ee-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="779ee-116">您需要先分配权限，然后才能执行本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="779ee-116">You need to be assigned permissions before you can do the procedures in this topic.</span></span> <span data-ttu-id="779ee-117">若要使用欺骗性智能洞察力，您需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="779ee-117">To use the spoof intelligence insight, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="779ee-118">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。</span><span class="sxs-lookup"><span data-stu-id="779ee-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="779ee-119">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“ **组织管理** ”或“ **清洁管理** ”。</span><span class="sxs-lookup"><span data-stu-id="779ee-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>
  - <span data-ttu-id="779ee-120">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“ **安全读取者** ”。</span><span class="sxs-lookup"><span data-stu-id="779ee-120">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="779ee-121">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“ **仅查看组织管理** ”。</span><span class="sxs-lookup"><span data-stu-id="779ee-121">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="779ee-122">在 Microsoft Defender for Office 365 中启用和禁用欺骗智能在反网络钓鱼策略中。</span><span class="sxs-lookup"><span data-stu-id="779ee-122">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="779ee-123">有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="779ee-123">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="779ee-124">若要使用欺骗智能来监视和管理向您发送未经身份验证的邮件的发件人，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="779ee-124">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="779ee-125">在安全 & 合规中心中打开欺骗性智能洞察力</span><span class="sxs-lookup"><span data-stu-id="779ee-125">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="779ee-126">在安全 & 合规性中心中，转到 " **威胁管理** \> **仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="779ee-126">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="779ee-127">在 " **见解** " 行中，查找以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="779ee-127">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="779ee-128">**启用欺骗智能** ：该洞察力被命名为 **欺骗性域，在过去30天的身份验证失败** 。</span><span class="sxs-lookup"><span data-stu-id="779ee-128">**Spoof intelligence is enabled** : The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="779ee-129">这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="779ee-129">This is the default.</span></span>
   - <span data-ttu-id="779ee-130">**已禁用欺骗情报** ：已命名 **启用欺骗保护** 的洞察力，单击它可启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="779ee-130">**Spoof intelligence is disabled** : The insight in named **Enable Spoof Protection** , and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="779ee-131">仪表板上的洞察力显示如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="779ee-131">The insight on the dashboard shows you information like this:</span></span>

   ![欺骗性智能洞察力的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="779ee-133">此洞察力有两种模式：</span><span class="sxs-lookup"><span data-stu-id="779ee-133">This insight has two modes:</span></span>

   - <span data-ttu-id="779ee-134">**真知灼见模式** ：如果启用欺骗智能，则真知灼见将显示在过去30天内受到欺骗智能功能影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="779ee-134">**Insight mode** : If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="779ee-135">**如果模式** 为：如果禁用欺骗情报，则真知灼见将显示在过去30天中，我们的欺骗智能功能 *会* 影响多少封邮件。</span><span class="sxs-lookup"><span data-stu-id="779ee-135">**What if mode** : If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="779ee-136">无论哪种方式，真知灼见中显示的欺骗性域都分为两类： **可疑域对** 和 **非可疑域对** 。</span><span class="sxs-lookup"><span data-stu-id="779ee-136">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="779ee-137">这些类别进一步细分为三个不同的存储桶供您查看。</span><span class="sxs-lookup"><span data-stu-id="779ee-137">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="779ee-138">**域对** 是 "发件人" 地址和发送基础结构的组合：</span><span class="sxs-lookup"><span data-stu-id="779ee-138">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="779ee-139">发件人地址是在电子邮件客户端的发件人框中显示的发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="779ee-139">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="779ee-140">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="779ee-140">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="779ee-141">发送方结构或发件人是发送 IP 地址的反向 DNS 查找 (PTR 记录) 的组织域。</span><span class="sxs-lookup"><span data-stu-id="779ee-141">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="779ee-142">如果发送 IP 地址没有 PTR 记录，则发件人由使用 CIDR 表示法中的255.255.255.0 子网掩码的发送 IP 标识 (/24) 。</span><span class="sxs-lookup"><span data-stu-id="779ee-142">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="779ee-143">例如，如果 IP 地址为192.168.100.100，则发件人的完整 IP 地址为 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="779ee-143">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="779ee-144">**可疑域对** 包括：</span><span class="sxs-lookup"><span data-stu-id="779ee-144">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="779ee-145">**高可信度欺骗** ：基于域的历史发送模式和信誉得分，我们非常确信域是哄骗的，并且来自这些域的邮件更有可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="779ee-145">**High-confidence spoof** : Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="779ee-146">**中等可信度欺骗** ：根据历史发送模式和域的信誉得分，我们确保了域是欺骗的，并且从这些域发送的邮件是合法的。</span><span class="sxs-lookup"><span data-stu-id="779ee-146">**Moderate confidence spoof** : Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="779ee-147">在此类别中，误报的可能性更大，而不是高度信心欺骗。</span><span class="sxs-lookup"><span data-stu-id="779ee-147">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="779ee-148">**非可疑域对** (包括 **rescued 欺骗** ) ：域失败显式电子邮件身份验证检查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。</span><span class="sxs-lookup"><span data-stu-id="779ee-148">**Non-suspicious domain pairs** (includes **rescued spoof** ): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="779ee-149">但是，域通过隐式电子邮件身份验证检查 ([复合身份验证](email-validation-and-authentication.md#composite-authentication)) 。</span><span class="sxs-lookup"><span data-stu-id="779ee-149">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="779ee-150">因此，不会对邮件执行任何反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="779ee-150">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="779ee-151">查看有关欺骗性智能洞察力的可疑域对的详细信息</span><span class="sxs-lookup"><span data-stu-id="779ee-151">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="779ee-152">在 "欺骗智能洞察力" 中，单击 "高"、"中等" 或 "rescued") 中的任一域对 (。</span><span class="sxs-lookup"><span data-stu-id="779ee-152">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="779ee-153">将显示 " **欺骗性智能洞察力** " 页。</span><span class="sxs-lookup"><span data-stu-id="779ee-153">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="779ee-154">页面向您显示将未经身份验证的电子邮件发送到您的组织的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="779ee-154">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="779ee-155">此信息可帮助您确定是否授权欺骗邮件，或者是否需要执行进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="779ee-155">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="779ee-156">您可以按邮件数、欺骗的上次检测日期等对信息进行排序。</span><span class="sxs-lookup"><span data-stu-id="779ee-156">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="779ee-157">在表中选择一个项目，打开包含有关域对的丰富信息的详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="779ee-157">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="779ee-158">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="779ee-158">The information includes:</span></span>
   - <span data-ttu-id="779ee-159">为什么我们会发现这一点。</span><span class="sxs-lookup"><span data-stu-id="779ee-159">Why we caught this.</span></span>
   - <span data-ttu-id="779ee-160">您需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="779ee-160">What you need to do.</span></span>
   - <span data-ttu-id="779ee-161">域摘要。</span><span class="sxs-lookup"><span data-stu-id="779ee-161">A domain summary.</span></span>
   - <span data-ttu-id="779ee-162">WhoIs 有关发件人的数据。</span><span class="sxs-lookup"><span data-stu-id="779ee-162">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="779ee-163">从同一个发件人在你的租户中看到的类似消息。</span><span class="sxs-lookup"><span data-stu-id="779ee-163">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="779ee-164">在这里，您还可以选择在 **AllowedToSpoof** 安全发件人列表中添加或删除域对。</span><span class="sxs-lookup"><span data-stu-id="779ee-164">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![欺骗智能洞察力详细信息窗格中的域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="779ee-166">在 AllowedToSpoof 列表中添加或删除域</span><span class="sxs-lookup"><span data-stu-id="779ee-166">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="779ee-167">您可以在域对的欺骗性智能洞察力的详细信息窗格中的 "AllowedToSpoof (安全发件人) 列表中添加或删除域。</span><span class="sxs-lookup"><span data-stu-id="779ee-167">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="779ee-168">只需设置相应的开关即可。</span><span class="sxs-lookup"><span data-stu-id="779ee-168">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="779ee-169">仅允许域对允许欺骗域 *和* 发送基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="779ee-169">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="779ee-170">它不允许来自任何来源的来自欺骗域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="779ee-170">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="779ee-171">例如，您允许以下域对将欺骗邮件发送到您的组织：</span><span class="sxs-lookup"><span data-stu-id="779ee-171">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="779ee-172">*冒牌域* ： gmail.com "</span><span class="sxs-lookup"><span data-stu-id="779ee-172">*Spoofed Domain* : gmail.com"</span></span>
- <span data-ttu-id="779ee-173">*发送基础结构* `tms.mx.com` ：</span><span class="sxs-lookup"><span data-stu-id="779ee-173">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="779ee-174">仅允许来自此域对的电子邮件欺骗。</span><span class="sxs-lookup"><span data-stu-id="779ee-174">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="779ee-175">不允许其他试图欺骗 gmail.com 的发件人。</span><span class="sxs-lookup"><span data-stu-id="779ee-175">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="779ee-176">来自 tms.mx.com 的其他域中的邮件由欺骗情报检查。</span><span class="sxs-lookup"><span data-stu-id="779ee-176">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="779ee-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="779ee-177">Related topics</span></span>

[<span data-ttu-id="779ee-178">Microsoft 365 中的反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="779ee-178">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
