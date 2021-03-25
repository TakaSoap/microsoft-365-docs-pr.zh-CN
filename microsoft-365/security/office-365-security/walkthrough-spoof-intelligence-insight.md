---
title: 演练 - 欺骗智能见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理员可以了解欺骗智能见解的工作原理。 他们可以快速确定哪些发件人从没有通过 SPF、DKIM 或 DMARC 身份验证检查 (向组织合法发送电子邮件) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203885"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="80257-104">演练 - Microsoft Defender for Office 365 中的欺骗智能见解</span><span class="sxs-lookup"><span data-stu-id="80257-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80257-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="80257-105">**Applies to**</span></span>
- [<span data-ttu-id="80257-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="80257-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="80257-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80257-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="80257-108">在具有适用于 Office 365 的 Defender 的 Microsoft 365 组织中，您可以使用欺骗智能见解快速确定哪些外部发件人合法地从未通过 SPF、DKIM 或 DMARC 检查) 的域中向您发送未经身份验证的电子邮件 (邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-108">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="80257-109">通过允许已知外部发件人从已知位置发送欺骗邮件，你可以减少误报 (标记为错误) 。</span><span class="sxs-lookup"><span data-stu-id="80257-109">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="80257-110">通过监视允许的欺骗发件人，你可以提供额外的安全层，以防止不安全的邮件到达你的组织。</span><span class="sxs-lookup"><span data-stu-id="80257-110">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="80257-111">有关报告和见解详细信息，请参阅安全与合规中心中的& [和见解](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="80257-111">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="80257-112">本演练是安全与合规中心&之一。</span><span class="sxs-lookup"><span data-stu-id="80257-112">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="80257-113">有关导航报告和见解的信息，请参阅相关主题 [部分中的演练](#related-topics) 。</span><span class="sxs-lookup"><span data-stu-id="80257-113">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

> [!NOTE]
> <span data-ttu-id="80257-114">欺骗智能见解显示过去 7 天的数据。</span><span class="sxs-lookup"><span data-stu-id="80257-114">The spoof intelligence insight shows data from the last 7 days.</span></span> <span data-ttu-id="80257-115">Exchange Online PowerShell [中的](learn-about-spoof-intelligence.md) 欺骗智能策略和相应的 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) cmdlet 显示过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="80257-115">The [spoof intelligence policy](learn-about-spoof-intelligence.md) and the corresponding [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) cmdlet in Exchange Online PowerShell shows data from the last 30 days.</span></span> <span data-ttu-id="80257-116">[Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport)最多显示 90 天的数据。</span><span class="sxs-lookup"><span data-stu-id="80257-116">The [Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport) shows data for up to 90 days.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80257-117">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="80257-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80257-118">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="80257-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="80257-119">若要直接转到安全 **仪表板页面，** 请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="80257-119">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="80257-120">可以从安全与合规中心中的多个仪表板查看&见解。</span><span class="sxs-lookup"><span data-stu-id="80257-120">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="80257-121">无论你正在查看哪个仪表板，该见解都提供相同的详细信息，并允许你快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="80257-121">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly do the same tasks.</span></span>

- <span data-ttu-id="80257-122">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="80257-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="80257-123">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="80257-123">**Organization Management**</span></span>
  - <span data-ttu-id="80257-124">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="80257-124">**Security Administrator**</span></span>
  - <span data-ttu-id="80257-125">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="80257-125">**Security Reader**</span></span>
  - <span data-ttu-id="80257-126">**全局读者**</span><span class="sxs-lookup"><span data-stu-id="80257-126">**Global Reader**</span></span>

  <span data-ttu-id="80257-127">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="80257-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="80257-128">注意：将用户添加到 Microsoft 365 管理中心的相应 Azure Active Directory 角色会为用户提供安全 & 合规中心所需的权限以及Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="80257-128">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80257-129">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="80257-129">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="80257-130">在 Microsoft Defender for Office 365 中的反网络钓鱼策略中启用和禁用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="80257-130">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="80257-131">默认情况下启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="80257-131">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="80257-132">有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="80257-132">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="80257-133">若要使用欺骗智能监视和管理发送未经身份验证的邮件的发件人，请参阅 [在 Microsoft 365](learn-about-spoof-intelligence.md)中配置欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="80257-133">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="80257-134">在安全与合规中心内打开&见解</span><span class="sxs-lookup"><span data-stu-id="80257-134">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="80257-135">在安全与&中心，转到" **威胁管理** \> **仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="80257-135">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="80257-136">在 **"Insights"** 行中，查找以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="80257-136">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="80257-137">**过去七天内** 可能欺骗的域：此见解表明在默认情况下 (已启用欺骗智能) 。</span><span class="sxs-lookup"><span data-stu-id="80257-137">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="80257-138">**启用欺骗** 保护：此见解表明已禁用欺骗智能，单击该见解将允许你启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="80257-138">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="80257-139">仪表板上的见解显示如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="80257-139">The insight on the dashboard shows you information like this:</span></span>

   ![欺骗智能见解的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="80257-141">此见解有两种模式：</span><span class="sxs-lookup"><span data-stu-id="80257-141">This insight has two modes:</span></span>

   - <span data-ttu-id="80257-142">**见解模式**：如果启用了欺骗智能，该见解将展示在过去七天内我们的欺骗智能功能所影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="80257-142">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="80257-143">**如果模式**：如果禁用了欺骗智能，那么该见解将展示在过去七天内有多少邮件会受我们的欺骗智能功能的影响。</span><span class="sxs-lookup"><span data-stu-id="80257-143">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="80257-144">无论使用哪种方式，见解中显示的欺骗性域都分为两类： **可疑** 域 **和非可疑域**。</span><span class="sxs-lookup"><span data-stu-id="80257-144">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="80257-145">**可疑域** 包括：</span><span class="sxs-lookup"><span data-stu-id="80257-145">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="80257-146">高可信度欺骗：根据历史发送模式和域的信誉分数，我们高度确信这些域是欺骗，并且来自这些域的邮件更有可能是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-146">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="80257-147">中等可信度欺骗：根据历史发送模式和域的信誉分数，我们确信这些域是欺骗的，并且从这些域发送的邮件是合法的。</span><span class="sxs-lookup"><span data-stu-id="80257-147">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="80257-148">在此类别中，误报的可能性大于高可信度欺骗。</span><span class="sxs-lookup"><span data-stu-id="80257-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="80257-149">**非可疑域**：域未通过显式电子邮件身份验证检查 [SPF、DKIM](how-office-365-uses-spf-to-prevent-spoofing.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。 [](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="80257-149">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="80257-150">但是，域已通过隐式电子邮件身份验证检查， ([身份验证) 。](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="80257-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="80257-151">因此，未对邮件执行反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="80257-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="80257-152">从欺骗智能见解中查看有关可疑域的详细信息</span><span class="sxs-lookup"><span data-stu-id="80257-152">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="80257-153">在"欺骗智能见解"上，单击" **可疑** 域或非 **可疑** 域"以转到" **欺骗智能见解"** 页面。</span><span class="sxs-lookup"><span data-stu-id="80257-153">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="80257-154">" **欺骗智能见解** "页包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="80257-154">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="80257-155">**欺骗性** 域：电子邮件客户端的"来源"框中显示的欺骗用户的域。 </span><span class="sxs-lookup"><span data-stu-id="80257-155">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="80257-156">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="80257-156">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="80257-157">**基础结构**：也称为发送 _基础结构_。</span><span class="sxs-lookup"><span data-stu-id="80257-157">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="80257-158">反向 DNS 查找中的域 (源) IP 地址的 PTR 记录。</span><span class="sxs-lookup"><span data-stu-id="80257-158">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="80257-159">如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="80257-159">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="80257-160">**邮件计数**：过去 7 天内从发送基础结构发送到包含指定欺骗域的组织的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="80257-160">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="80257-161">**上次看到** 时间：从包含欺骗域的发送基础结构接收邮件的最后日期。</span><span class="sxs-lookup"><span data-stu-id="80257-161">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="80257-162">**欺骗类型**：此值为 **External**。</span><span class="sxs-lookup"><span data-stu-id="80257-162">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="80257-163">**允许欺骗？：** 你在此处看到的值是：</span><span class="sxs-lookup"><span data-stu-id="80257-163">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="80257-164">**是**：允许来自欺骗用户域和发送基础结构组合的邮件，且不会被视为欺骗电子邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-164">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="80257-165">**否**：来自欺骗用户域和发送基础结构组合的邮件被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-165">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="80257-166">该操作由默认反网络钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="80257-166">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="80257-167">有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="80257-167">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="80257-168">在列表中选择一个项目，以查看有关在飞出视图中的域/发送基础结构对的详细信息。</span><span class="sxs-lookup"><span data-stu-id="80257-168">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="80257-169">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="80257-169">The information includes:</span></span>
   - <span data-ttu-id="80257-170">我们为什么捕获到此。</span><span class="sxs-lookup"><span data-stu-id="80257-170">Why we caught this.</span></span>
   - <span data-ttu-id="80257-171">需要执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="80257-171">What you need to do.</span></span>
   - <span data-ttu-id="80257-172">域摘要。</span><span class="sxs-lookup"><span data-stu-id="80257-172">A domain summary.</span></span>
   - <span data-ttu-id="80257-173">WhoIs 有关发件人的数据。</span><span class="sxs-lookup"><span data-stu-id="80257-173">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="80257-174">我们在租户中看到的来自同一发件人的类似邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-174">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="80257-175">在此处，还可以选择在允许欺骗发件人允许列表中添加或删除域/发送基础结构对。 </span><span class="sxs-lookup"><span data-stu-id="80257-175">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="80257-176">只需相应地设置切换。</span><span class="sxs-lookup"><span data-stu-id="80257-176">Simply set the toggle accordingly.</span></span>

   !["欺骗智能见解详细信息"窗格中域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="80257-178">将域添加到允许欺骗列表</span><span class="sxs-lookup"><span data-stu-id="80257-178">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="80257-179">将域从欺骗智能见解添加到允许欺骗列表仅允许欺骗域和发送基础结构的组合。 </span><span class="sxs-lookup"><span data-stu-id="80257-179">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="80257-180">它不允许来自任何来源的欺骗性域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-180">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="80257-181">例如，允许以下域进入允许欺骗列表：</span><span class="sxs-lookup"><span data-stu-id="80257-181">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="80257-182">**域**： gmail.com</span><span class="sxs-lookup"><span data-stu-id="80257-182">**Domain**: gmail.com</span></span>
- <span data-ttu-id="80257-183">**基础结构**：tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="80257-183">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="80257-184">仅允许来自该域/发送基础结构对的电子邮件欺骗。</span><span class="sxs-lookup"><span data-stu-id="80257-184">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="80257-185">不允许其他发件人 gmail.com 欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="80257-185">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="80257-186">来自其他域中的邮件 tms.mx.com 欺骗智能进行检查。</span><span class="sxs-lookup"><span data-stu-id="80257-186">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="80257-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="80257-187">Related topics</span></span>

[<span data-ttu-id="80257-188">Microsoft 365 中的反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="80257-188">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)