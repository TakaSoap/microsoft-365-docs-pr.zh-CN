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
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602091"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b728e-104">演练-Microsoft Defender for Office 365 中的欺骗智能洞察力</span><span class="sxs-lookup"><span data-stu-id="b728e-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b728e-105">在使用 Defender for Office 365 的 Microsoft 365 组织中，您可以使用欺骗智能洞察力快速确定哪些外部发件人可以合法地向您发送未经身份验证的电子邮件 (来自不通过 SPF、DKIM 或 DMARC 检查的域的邮件) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="b728e-106">通过允许已知外部发件人从已知位置发送欺骗邮件，可以减少误报 (被标记为坏) 的良好电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b728e-106">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="b728e-107">通过监视允许的欺骗性发件人，您可以提供额外的安全层来防止不安全的邮件到达您的组织中。</span><span class="sxs-lookup"><span data-stu-id="b728e-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="b728e-108">有关报告和见解的详细信息，请参阅 [Security & 合规性中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="b728e-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="b728e-109">本演练是安全 & 合规中心的几个演练之一。</span><span class="sxs-lookup"><span data-stu-id="b728e-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="b728e-110">若要导航报告和见解，请参阅 [相关主题](#related-topics) 部分中的演练。</span><span class="sxs-lookup"><span data-stu-id="b728e-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b728e-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b728e-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b728e-112">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="b728e-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b728e-113">若要直接转到 **安全仪表板** 页面，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="b728e-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="b728e-114">您可以从安全 & 合规中心的多个仪表板中查看欺骗性智能洞察力。</span><span class="sxs-lookup"><span data-stu-id="b728e-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="b728e-115">无论您正在查看哪个仪表板，真知灼见都会提供相同的详细信息，并允许您快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="b728e-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="b728e-116">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="b728e-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b728e-117">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="b728e-117">**Organization Management**</span></span>
  - <span data-ttu-id="b728e-118">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="b728e-118">**Security Administrator**</span></span>
  - <span data-ttu-id="b728e-119">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="b728e-119">**Security Reader**</span></span>
  - <span data-ttu-id="b728e-120">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="b728e-120">**Global Reader**</span></span>

  <span data-ttu-id="b728e-121">**注意**：将用户添加到 microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心中的必需权限 _以及_ Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="b728e-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b728e-122">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b728e-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="b728e-123">在 Microsoft Defender for Office 365 中启用和禁用欺骗智能在反网络钓鱼策略中。</span><span class="sxs-lookup"><span data-stu-id="b728e-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b728e-124">默认情况下启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="b728e-124">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="b728e-125">有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b728e-125">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="b728e-126">若要使用欺骗智能来监视和管理向您发送未经身份验证的邮件的发件人，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b728e-126">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="b728e-127">在安全 & 合规中心中打开欺骗性智能洞察力</span><span class="sxs-lookup"><span data-stu-id="b728e-127">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b728e-128">在安全 & 合规性中心中，转到 " **威胁管理** \> **仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="b728e-128">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="b728e-129">在 " **见解** " 行中，查找以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="b728e-129">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="b728e-130">**可能在过去七天内的欺骗域**：此洞察力表明启用了欺骗智能， (默认情况下启用了该功能) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-130">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="b728e-131">**启用欺骗保护**：此洞察力表明已禁用欺骗性智能，单击真知灼见使你能够启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="b728e-131">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="b728e-132">仪表板上的洞察力显示如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="b728e-132">The insight on the dashboard shows you information like this:</span></span>

   ![欺骗性智能洞察力的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="b728e-134">此洞察力有两种模式：</span><span class="sxs-lookup"><span data-stu-id="b728e-134">This insight has two modes:</span></span>

   - <span data-ttu-id="b728e-135">**真知灼见模式**：如果启用欺骗智能，则真知灼见将显示在过去七天内受到欺骗智能功能影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="b728e-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="b728e-136">**如果模式** 为：如果禁用欺骗情报，则真知灼见将显示在过去七天中，我们的欺骗智能功能 *可能会* 影响多少封邮件。</span><span class="sxs-lookup"><span data-stu-id="b728e-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="b728e-137">无论哪种方式，真知灼见中显示的欺骗性域都分为两类： **可疑域** 和 **非可疑域**。</span><span class="sxs-lookup"><span data-stu-id="b728e-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="b728e-138">**可疑域** 包括：</span><span class="sxs-lookup"><span data-stu-id="b728e-138">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="b728e-139">高可信度欺骗：基于域的历史发送模式和信誉得分，我们非常确信域是哄骗的，并且来自这些域的邮件更有可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="b728e-139">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="b728e-140">中等可信度欺骗：根据历史发送模式和域的信誉得分，我们确保了域是欺骗的，并且从这些域发送的邮件是合法的。</span><span class="sxs-lookup"><span data-stu-id="b728e-140">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="b728e-141">在此类别中，误报的可能性更大，而不是高度信心欺骗。</span><span class="sxs-lookup"><span data-stu-id="b728e-141">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="b728e-142">**非可疑域**：域未通过显式电子邮件身份验证检查 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-142">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="b728e-143">但是，域通过隐式电子邮件身份验证检查 ([复合身份验证](email-validation-and-authentication.md#composite-authentication)) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-143">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="b728e-144">因此，不会对邮件执行任何反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="b728e-144">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="b728e-145">查看有关欺骗性智能洞察力的可疑域的详细信息</span><span class="sxs-lookup"><span data-stu-id="b728e-145">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="b728e-146">在 "哄骗智能洞察力" 中，单击 " **可疑域** " 或 " **非可疑域** " 以转到 " **哄骗智能洞察力** " 页面。</span><span class="sxs-lookup"><span data-stu-id="b728e-146">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="b728e-147">" **哄骗智能洞察力** " 页面包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b728e-147">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="b728e-148">**欺骗域**：在电子邮件客户端的 " **发件人** " 框中显示的欺骗用户的域。</span><span class="sxs-lookup"><span data-stu-id="b728e-148">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="b728e-149">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="b728e-149">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="b728e-150">**基础结构**：也称为 " _发送" 基础结构_。</span><span class="sxs-lookup"><span data-stu-id="b728e-150">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="b728e-151">在反向 DNS 查找中找到的域 (PTR 记录服务器的 IP 地址的 PTR 记录) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-151">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="b728e-152">如果源 IP 地址没有 PTR 记录，则发送的基础结构被标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-152">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="b728e-153">**邮件计数**：在最近7天内包含指定的欺骗性域的组织发送到组织的邮件数。</span><span class="sxs-lookup"><span data-stu-id="b728e-153">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="b728e-154">**上次查看** 时间：从包含欺骗域的发送基础结构收到邮件的最后日期。</span><span class="sxs-lookup"><span data-stu-id="b728e-154">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="b728e-155">**哄骗类型**：此值是 **外部** 的。</span><span class="sxs-lookup"><span data-stu-id="b728e-155">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="b728e-156">是否 **允许欺骗？**：您在此处看到的值是：</span><span class="sxs-lookup"><span data-stu-id="b728e-156">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="b728e-157">**是**：允许欺骗用户的域和发送基础结构组合的邮件不会被视为欺骗电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b728e-157">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="b728e-158">**否**：来自欺骗用户的域和发送基础结构的组合的邮件被标记为欺骗。</span><span class="sxs-lookup"><span data-stu-id="b728e-158">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="b728e-159">该操作由默认的反网络钓鱼策略或自定义反网络钓鱼策略控制 (默认值为 " **将邮件移动到垃圾邮件" 文件夹**) 。</span><span class="sxs-lookup"><span data-stu-id="b728e-159">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="b728e-160">有关详细信息，请参阅 [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b728e-160">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="b728e-161">选择列表中的某一项，以查看浮出控件中的域/发送基础结构对的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b728e-161">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="b728e-162">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="b728e-162">The information includes:</span></span>
   - <span data-ttu-id="b728e-163">为什么我们会发现这一点。</span><span class="sxs-lookup"><span data-stu-id="b728e-163">Why we caught this.</span></span>
   - <span data-ttu-id="b728e-164">您需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b728e-164">What you need to do.</span></span>
   - <span data-ttu-id="b728e-165">域摘要。</span><span class="sxs-lookup"><span data-stu-id="b728e-165">A domain summary.</span></span>
   - <span data-ttu-id="b728e-166">WhoIs 有关发件人的数据。</span><span class="sxs-lookup"><span data-stu-id="b728e-166">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="b728e-167">从同一个发件人在你的租户中看到的类似消息。</span><span class="sxs-lookup"><span data-stu-id="b728e-167">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="b728e-168">在这里，您还可以选择在 " **允许欺骗** 发件人允许" 列表中添加或删除域/发送基础结构对。</span><span class="sxs-lookup"><span data-stu-id="b728e-168">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="b728e-169">只需设置相应的开关即可。</span><span class="sxs-lookup"><span data-stu-id="b728e-169">Simply set the toggle accordingly.</span></span>

   ![欺骗智能洞察力详细信息窗格中的域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="b728e-171">将域添加到允许的欺骗列表中</span><span class="sxs-lookup"><span data-stu-id="b728e-171">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="b728e-172">通过哄骗智能洞察力将域添加到允许的欺骗列表中，仅允许将欺骗性域 *和* 发送基础结构结合在一起。</span><span class="sxs-lookup"><span data-stu-id="b728e-172">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="b728e-173">它不允许来自任何来源的来自欺骗域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b728e-173">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="b728e-174">例如，您允许以下域成为允许欺骗的列表：</span><span class="sxs-lookup"><span data-stu-id="b728e-174">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="b728e-175">**域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="b728e-175">**Domain**: gmail.com</span></span>
- <span data-ttu-id="b728e-176">**基础结构**： tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="b728e-176">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="b728e-177">仅允许来自该域/发送基础结构对的电子邮件进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="b728e-177">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="b728e-178">不允许其他试图欺骗 gmail.com 的发件人。</span><span class="sxs-lookup"><span data-stu-id="b728e-178">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="b728e-179">来自 tms.mx.com 的其他域中的邮件由欺骗情报检查。</span><span class="sxs-lookup"><span data-stu-id="b728e-179">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b728e-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="b728e-180">Related topics</span></span>

[<span data-ttu-id="b728e-181">Microsoft 365 中的反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="b728e-181">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
