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
description: 了解新的欺骗智能洞察力的工作方式，包括如何快速确定哪些发件人合法地向您发送未经身份验证的电子邮件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 481d248b833c7910152cd39113ff32fdc1217a5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033640"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a><span data-ttu-id="14b75-103">演练-在 Microsoft 365 中 ATP 欺骗智能洞察力</span><span class="sxs-lookup"><span data-stu-id="14b75-103">Walkthrough - ATP Spoof intelligence insight in Microsoft 365</span></span>

<span data-ttu-id="14b75-104">在具有高级威胁防护（ATP）的 Microsoft 365 组织中，您可以使用欺骗智能洞察力快速确定哪些发件人合法地向您发送未经身份验证的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="14b75-104">In Microsoft 365 organizations with Advanced Threat Protection (ATP), you can use the spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="14b75-105">通过允许他们发送欺骗邮件，可以降低任何误报给用户带来的风险。</span><span class="sxs-lookup"><span data-stu-id="14b75-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span> <span data-ttu-id="14b75-106">您还可以使用欺骗智能洞察力来监视和管理允许的域对，以提供额外的安全措施，并防止不安全的邮件到达您的组织中。</span><span class="sxs-lookup"><span data-stu-id="14b75-106">You can also use the spoof intelligence insight to monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="14b75-107">如果您不熟悉[安全 & 合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)，它可能会帮助您了解如何轻松地从仪表板导航到真知灼见和推荐的操作。</span><span class="sxs-lookup"><span data-stu-id="14b75-107">If you're new to [reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>

<span data-ttu-id="14b75-108">本演练是安全 & 合规中心的几个演练之一。</span><span class="sxs-lookup"><span data-stu-id="14b75-108">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="14b75-109">若要导航报告和见解，请参阅相关主题部分中的演练。</span><span class="sxs-lookup"><span data-stu-id="14b75-109">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="14b75-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="14b75-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="14b75-111">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="14b75-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="14b75-112">若要直接转到**安全仪表板**页面， <https://protection.office.com/searchandinvestigation/dashboard>请使用。</span><span class="sxs-lookup"><span data-stu-id="14b75-112">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="14b75-113">您可以从安全 & 合规中心的多个仪表板中查看欺骗性智能洞察力。</span><span class="sxs-lookup"><span data-stu-id="14b75-113">You can view the spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="14b75-114">无论您正在查看哪个仪表板，真知灼见都会提供相同的详细信息，并允许您快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="14b75-114">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="14b75-115">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="14b75-115">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="14b75-116">若要使用欺骗性智能洞察力，您必须是 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="14b75-116">To use the spoof intelligence insight, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="14b75-117">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="14b75-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="14b75-118">在 ATP 反网络钓鱼策略中启用和禁用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="14b75-118">You enable and disable spoof intelligence in ATP anti-phishing policies.</span></span> <span data-ttu-id="14b75-119">有关详细信息，请参阅[在 Microsoft 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="14b75-119">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="14b75-120">在使用 Exchange Online 邮箱的 Microsoft 365 组织中，在没有 Exchange Online 邮箱的独立 Exchange Online Protection （EOP）中，可以使用欺骗智能来监视和管理您向其发送未经身份验证的邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="14b75-120">In Microsoft 365 organizations with Exchange Online mailboxes, and in standalone Exchange Online Protection (EOP) without Exchange Online mailboxes, you can use spoof intelligence to monitor and manage senders you are sending you unauthenticated messages.</span></span> <span data-ttu-id="14b75-121">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="14b75-121">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="14b75-122">在安全 & 合规中心中打开欺骗性智能洞察力</span><span class="sxs-lookup"><span data-stu-id="14b75-122">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="14b75-123">在安全 & 合规性中心中，转到 "**威胁管理** \> **仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="14b75-123">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="14b75-124">在 "**见解**" 行中，查找以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="14b75-124">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="14b75-125">**启用欺骗智能**：该洞察力被命名为**欺骗性域，在过去30天的身份验证失败**。</span><span class="sxs-lookup"><span data-stu-id="14b75-125">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="14b75-126">这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="14b75-126">This is the default.</span></span>

   - <span data-ttu-id="14b75-127">**已禁用欺骗情报**：已命名**启用欺骗保护**的洞察力，单击它可启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="14b75-127">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="14b75-128">仪表板上的洞察力显示如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="14b75-128">The insight on the dashboard shows you information like this:</span></span>

   ![欺骗性智能洞察力的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="14b75-130">此洞察力有两种模式：</span><span class="sxs-lookup"><span data-stu-id="14b75-130">This insight has two modes:</span></span>

   - <span data-ttu-id="14b75-131">**真知灼见模式**。</span><span class="sxs-lookup"><span data-stu-id="14b75-131">**Insight mode**.</span></span> <span data-ttu-id="14b75-132">如果你启用了任何欺骗策略，则真知灼见将显示在过去30天内受到欺骗智能功能影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="14b75-132">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="14b75-133">**If 模式**。</span><span class="sxs-lookup"><span data-stu-id="14b75-133">**What if mode**.</span></span> <span data-ttu-id="14b75-134">如果未启用任何欺骗策略，则真知灼见将显示在过去30天内，我们的欺骗智能功能*会*影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="14b75-134">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="14b75-135">无论哪种方式，真知灼见中显示的欺骗性域都分为两类：**可疑域对**和**非可疑域对**。</span><span class="sxs-lookup"><span data-stu-id="14b75-135">Either way, the spoofed domains displayed in the insight are separated into two categories: **suspicious domain pairs** and **non-suspicious domain pairs**.</span></span> <span data-ttu-id="14b75-136">这些类别进一步细分为三个不同的存储桶供您查看。</span><span class="sxs-lookup"><span data-stu-id="14b75-136">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="14b75-137">**域对**是 "发件人" 地址和发送基础结构的组合：</span><span class="sxs-lookup"><span data-stu-id="14b75-137">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="14b75-138">发件人地址是在电子邮件客户端中显示的发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="14b75-138">The From address is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="14b75-139">此地址标识电子邮件的作者。</span><span class="sxs-lookup"><span data-stu-id="14b75-139">This address identifies the author of the email.</span></span> <span data-ttu-id="14b75-140">即，负责撰写邮件的个人或系统的邮箱。</span><span class="sxs-lookup"><span data-stu-id="14b75-140">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="14b75-141">此地址也称为`5322.From`地址。</span><span class="sxs-lookup"><span data-stu-id="14b75-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="14b75-142">发送方结构或发件人是发送 IP 地址的反向 DNS 查找（PTR 记录）的组织域。</span><span class="sxs-lookup"><span data-stu-id="14b75-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="14b75-143">如果发送 IP 地址没有 PTR 记录，则发件人由使用 CIDR 表示法（/24）中的255.255.255.0 子网掩码的发送 IP 进行标识。</span><span class="sxs-lookup"><span data-stu-id="14b75-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="14b75-144">例如，如果 IP 地址为192.168.100.100，则发件人的完整 IP 地址为 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="14b75-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="14b75-145">**可疑域对**包括：</span><span class="sxs-lookup"><span data-stu-id="14b75-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="14b75-146">**高可信度欺骗**： Microsoft 365 收到了基于历史发送模式和域信誉分数的强信号，这些域是可疑的。</span><span class="sxs-lookup"><span data-stu-id="14b75-146">**High-confidence spoof**: Microsoft 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="14b75-147">Microsoft 365 非常确信域是哄骗的，并且从这些域发送的邮件不太可能是合法的。</span><span class="sxs-lookup"><span data-stu-id="14b75-147">Microsoft 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span>

   - <span data-ttu-id="14b75-148">**中等可信度欺骗**： Microsoft 365 收到了中等信号，这些域根据历史发送模式和域的信誉得分而受到怀疑。</span><span class="sxs-lookup"><span data-stu-id="14b75-148">**Moderate confidence spoof**: Microsoft 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="14b75-149">Office 365 适度确信域是欺骗的，并且从这些域发送的邮件是合法的。</span><span class="sxs-lookup"><span data-stu-id="14b75-149">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="14b75-150">此存储桶具有包含误报（FPs）的更多可能性，而不是高可信度欺骗存储桶。</span><span class="sxs-lookup"><span data-stu-id="14b75-150">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span>

   - <span data-ttu-id="14b75-151">**非可疑域对**（包括**rescued 欺骗**）： rescued 欺骗是未通过显式身份验证检查[SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)）的域，但通过了隐式电子邮件身份验证检查（[复合身份验证](email-validation-and-authentication.md#composite-authentication)）。</span><span class="sxs-lookup"><span data-stu-id="14b75-151">**Non-suspicious domain pairs** (includes **rescued spoof**): Rescued spoof are domains that have failed the explicit authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) but passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="14b75-152">因此，Microsoft 365 会代表您 rescued 邮件，并且不会对邮件执行任何反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="14b75-152">As a result, Microsoft 365 rescued the mail on your behalf and no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="14b75-153">查看有关欺骗性智能洞察力的可疑域对的详细信息</span><span class="sxs-lookup"><span data-stu-id="14b75-153">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="14b75-154">在 "哄骗智能洞察力" 中，单击任一域对（high、适中或 rescued）。</span><span class="sxs-lookup"><span data-stu-id="14b75-154">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="14b75-155">此时将显示 "**哄骗智能真知灼见**" 页面，其中显示了向您的组织发送未经身份验证的邮件的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="14b75-155">The **Spoof Intelligence insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="14b75-156">此页上的信息可帮助您确定是否授权欺骗邮件，或者是否需要执行进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="14b75-156">The information on this page helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span> <span data-ttu-id="14b75-157">您可以按邮件数、欺骗的上次检测日期等对信息进行排序。</span><span class="sxs-lookup"><span data-stu-id="14b75-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="14b75-158">（例如，单击 "**邮件数**" 或 "**最后见到**的列标题"。）</span><span class="sxs-lookup"><span data-stu-id="14b75-158">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span>

2. <span data-ttu-id="14b75-159">在表中选择一个项目以打开详细信息窗格，其中包含有关域对的丰富信息，其中包括我们捕获此内容的原因、您需要执行的操作、域摘要、域摘要、WhoIs 有关发件人的数据以及我们在你的租户中从相同的发件人处看到的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="14b75-159">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="14b75-160">在这里，您还可以选择在**AllowedToSpoof**安全发件人列表中添加或删除域对。</span><span class="sxs-lookup"><span data-stu-id="14b75-160">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![欺骗智能洞察力详细信息窗格中的域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="14b75-162">在 AllowedToSpoof 安全发件人列表中添加或删除域</span><span class="sxs-lookup"><span data-stu-id="14b75-162">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="14b75-163">在欺骗性智能洞察力的详细信息窗格中查看域对时，可以在 AllowedToSpoof 安全发件人列表中添加或删除域。</span><span class="sxs-lookup"><span data-stu-id="14b75-163">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="14b75-164">只需设置相应的开关即可。</span><span class="sxs-lookup"><span data-stu-id="14b75-164">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="14b75-165">这将修改欺骗性域和发送基础结构的唯一域对组合，并且不会对整个欺骗域或独立的发送基础结构提供覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="14b75-165">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span>

<span data-ttu-id="14b75-166">例如，如果将以下域对添加到 "AllowedToSpoof" 发件人允许列表：*欺骗域*"gmail.com" 和*发送基础结构*"tm *. mx.com"，* 则仅允许来自该域对的邮件欺骗。</span><span class="sxs-lookup"><span data-stu-id="14b75-166">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and *Sending Infrastructure* "tms *.mx.com",* then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="14b75-167">其他试图欺骗 "gmail.com" 的发件人以及 "tms.mx.com" 尝试欺骗的其他域将继续受到欺骗性智能的保护。</span><span class="sxs-lookup"><span data-stu-id="14b75-167">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="14b75-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="14b75-168">Related topics</span></span>

[<span data-ttu-id="14b75-169">Microsoft 365 中的反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="14b75-169">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="14b75-170">演练 - 从仪表板到见解</span><span class="sxs-lookup"><span data-stu-id="14b75-170">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)

[<span data-ttu-id="14b75-171">演练 - 从详细报告到见解</span><span class="sxs-lookup"><span data-stu-id="14b75-171">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)

[<span data-ttu-id="14b75-172">演练 - 从见解到详细报告</span><span class="sxs-lookup"><span data-stu-id="14b75-172">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)