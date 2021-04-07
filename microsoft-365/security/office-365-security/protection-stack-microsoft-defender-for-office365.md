---
title: Microsoft Defender for Office 365 中的分步威胁防护堆栈
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: 通过 Microsoft Defender for Office 365 中的威胁筛选堆栈，按照传入邮件的路径操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0760bd7a67f175e4af114324ccc729355ad5f593
ms.sourcegitcommit: 4e05f19c00e172b65f637f19ca461db5b21dff4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51601365"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8489c-103">Microsoft Defender for Office 365 中的分步威胁防护</span><span class="sxs-lookup"><span data-stu-id="8489c-103">Step-by-step threat protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8489c-104">Microsoft Defender for Office 365 保护或筛选堆栈可以分为 4 个阶段，如本文所介绍。</span><span class="sxs-lookup"><span data-stu-id="8489c-104">The Microsoft Defender for Office 365 protection or filtering stack can be broken out into 4 phases, as in this article.</span></span> <span data-ttu-id="8489c-105">一般来说，传入邮件在传递之前会通过所有这些阶段，但电子邮件的实际路径受组织的 Defender for Office 365 配置限制。</span><span class="sxs-lookup"><span data-stu-id="8489c-105">Generally speaking, incoming mail passes through all of these phases before delivery, but the actual path email takes is subject to an organization's Defender for Office 365 configuration.</span></span>

> [!TIP]
> <span data-ttu-id="8489c-106">请继续关注到本文末尾，了解 Defender  for Office 365 保护的所有 4 个阶段的统一图形！</span><span class="sxs-lookup"><span data-stu-id="8489c-106">Stay tuned till the end of this article for a *unified* graphic of all 4 phases of Defender for Office 365 protection!</span></span>

## <a name="phase-1---edge-protection"></a><span data-ttu-id="8489c-107">第 1 阶段 - 边缘保护</span><span class="sxs-lookup"><span data-stu-id="8489c-107">Phase 1 - Edge Protection</span></span>

<span data-ttu-id="8489c-108">遗憾的是，曾经至关重要 *的边缘块现在* 相对简单，让坏角色能够克服这些障碍。</span><span class="sxs-lookup"><span data-stu-id="8489c-108">Unfortunately, Edge blocks that were once *critical* are now relatively simple for bad actors to overcome.</span></span> <span data-ttu-id="8489c-109">随着时间的推移，此处阻止的流量较少，但它仍是堆栈的重要部分。</span><span class="sxs-lookup"><span data-stu-id="8489c-109">Over time, less traffic is blocked here, but it remains an important part of the stack.</span></span>  

<span data-ttu-id="8489c-110">边缘块设计为自动。</span><span class="sxs-lookup"><span data-stu-id="8489c-110">Edge blocks are designed to be automatic.</span></span> <span data-ttu-id="8489c-111">如果误报，将通知发件人并告知发件人如何处理其问题。</span><span class="sxs-lookup"><span data-stu-id="8489c-111">In the case of false positive, senders will be notified and told how to address their issue.</span></span> <span data-ttu-id="8489c-112">来自信誉有限的受信任合作伙伴的连接器可以确保可交付性，或在载入新终结点时可以设置临时替代。</span><span class="sxs-lookup"><span data-stu-id="8489c-112">Connectors from trusted partners with limited reputation can ensure deliverability, or temporary overrides can be put in place, when onboarding new endpoints.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="在 Defender for Office 365 中筛选的第 1 阶段是边缘保护。":::

1. <span data-ttu-id="8489c-114">网络 **限制** 通过限制一组特定基础结构可以提交的消息数，保护 Office 365 基础结构和客户免受拒绝服务 (DOS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="8489c-114">**Network throttling** protects Office 365 infrastructure and customers from Denial of Service (DOS) attacks by limiting the number of messages that can be submitted by a specific set of infrastructure.</span></span>

2. <span data-ttu-id="8489c-115">**IP 信誉和限制将** 阻止从已知的连接 IP 地址错误发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-115">**IP reputation and throttling** will block messages being sent from known bad connecting IP addresses.</span></span> <span data-ttu-id="8489c-116">如果特定 IP 在短时间内发送许多邮件，则这些邮件将被限制。</span><span class="sxs-lookup"><span data-stu-id="8489c-116">If a specific IP sends many messages in a short period of time they will be throttled.</span></span>

3. <span data-ttu-id="8489c-117">**域信誉** 将阻止从已知错误域发送的任何邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-117">**Domain reputation** will block any messages being sent from a known bad domain.</span></span>

4. <span data-ttu-id="8489c-118">**基于目录的边缘筛选** 阻止通过 SMTP 获取组织的目录信息的尝试。</span><span class="sxs-lookup"><span data-stu-id="8489c-118">**Directory-based edge filtering** blocks attempts to harvest an organization's directory information through SMTP.</span></span>

5. <span data-ttu-id="8489c-119">**退退检测** 可防止组织通过无效的未送达报告 (未送达报告) 。</span><span class="sxs-lookup"><span data-stu-id="8489c-119">**Backscatter detection** prevents an organization from being attacked through invalid non-delivery reports (NDRs).</span></span>

6. <span data-ttu-id="8489c-120">**连接器的增强** 筛选功能可保留身份验证信息，即使流量在到达 Office 365 之前通过其他设备。</span><span class="sxs-lookup"><span data-stu-id="8489c-120">**Enhanced filtering for connectors** preserves authentication information even when traffic passes through another device before it reaches Office 365.</span></span> <span data-ttu-id="8489c-121">这提高了筛选堆栈的准确性，包括启发式群集、反欺骗和防钓鱼机器学习模型，即使在复杂或混合路由方案中也可以。</span><span class="sxs-lookup"><span data-stu-id="8489c-121">This improves filtering stack accuracy, including heuristic clustering, anti-spoofing, and anti-phishing machine learning models, even when in complex or hybrid routing scenarios.</span></span>

## <a name="phase-2---sender-intelligence"></a><span data-ttu-id="8489c-122">阶段 2 - 发件人智能</span><span class="sxs-lookup"><span data-stu-id="8489c-122">Phase 2 - Sender Intelligence</span></span>

<span data-ttu-id="8489c-123">发件人智能中的功能对于捕获垃圾邮件、批量、模拟和未经授权的欺骗邮件至关重要，还会成为网络钓鱼检测的因素。</span><span class="sxs-lookup"><span data-stu-id="8489c-123">Features in sender intelligence are critical for catching spam, bulk, impersonation, and unauthorized spoof messages, and also factor into phish detection.</span></span> <span data-ttu-id="8489c-124">这些功能中的大多数是可单独配置的。</span><span class="sxs-lookup"><span data-stu-id="8489c-124">Most of these features are individually configurable.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="MDO 中的筛选阶段 2 是发件人智能。":::

1. <span data-ttu-id="8489c-126">**帐户具有** 异常行为且与泄露一致时，会引发帐户泄露检测触发器和警报。</span><span class="sxs-lookup"><span data-stu-id="8489c-126">**Account compromise detection** triggers and alerts are raised when an account has anomalous behavior, consistent with compromise.</span></span> <span data-ttu-id="8489c-127">在某些情况下，在组织的安全运营团队解决问题之前，用户帐户将被阻止并阻止发送任何进一步的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-127">In some cases, the user account is blocked and prevented from sending any further email messages until the issue is resolved by an organization's security operations team.</span></span>

2. <span data-ttu-id="8489c-128">**电子邮件** 身份验证涉及客户配置的方法和在云中设置的方法，旨在确保发件人得到授权，是可信的邮件发送者。</span><span class="sxs-lookup"><span data-stu-id="8489c-128">**Email Authentication** involves both customer configured methods and methods set up in the Cloud, aimed at ensuring that senders are authorized, authentic mailers.</span></span> <span data-ttu-id="8489c-129">这些方法可抵御欺骗。</span><span class="sxs-lookup"><span data-stu-id="8489c-129">These methods resist spoofing.</span></span>
    - <span data-ttu-id="8489c-130">**SPF** 可以拒绝基于 DNS TXT 记录的邮件，这些记录列出允许代表组织发送邮件的 IP 地址和服务器。</span><span class="sxs-lookup"><span data-stu-id="8489c-130">**SPF** can reject mails based on DNS TXT records that list IP addresses and servers allowed to send mail on the organization's behalf.</span></span>
    - <span data-ttu-id="8489c-131">**DKIM** 提供对发件人进行身份验证的加密签名。</span><span class="sxs-lookup"><span data-stu-id="8489c-131">**DKIM** provides an encrypted signature that authenticates the sender.</span></span>
    - <span data-ttu-id="8489c-132">**DMARC** 允许管理员按其域中的要求标记 SPF 和 DKIM，并强制在这两种技术的结果之间保持一致。</span><span class="sxs-lookup"><span data-stu-id="8489c-132">**DMARC** lets admins mark SPF and DKIM as required in their domain and enforces alignment between the results of these two technologies.</span></span>
    - <span data-ttu-id="8489c-133">**ARC** 未进行客户配置，但基于 DMARC 构建，以用于邮件列表中的转发，同时记录身份验证链。</span><span class="sxs-lookup"><span data-stu-id="8489c-133">**ARC** is not customer configured, but builds on DMARC to work with forwarding in mailing lists, while recording an authentication chain.</span></span>

3. <span data-ttu-id="8489c-134">欺骗智能能够筛选允许"欺骗" (即代表其他帐户发送邮件，或转发来自恶意欺骗程序模仿组织或已知外部域的邮件列表) 的用户。</span><span class="sxs-lookup"><span data-stu-id="8489c-134">**Spoof intelligence** is capable of filtering those allowed to 'spoof' (that is, those sending mail on behalf of another account, or forwarding for a mailing list) from malicious spoofers imitating an organizational, or known external, domain.</span></span> <span data-ttu-id="8489c-135">它将合法"代表"邮件与欺骗发件人分开，以传递垃圾邮件和网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-135">It separates legitimate 'on behalf of' mail from senders spoofing to deliver spam and phishing messages.</span></span> 

    <span data-ttu-id="8489c-136">**组织内部欺骗智能** 检测并阻止来自组织内部域的欺骗尝试。</span><span class="sxs-lookup"><span data-stu-id="8489c-136">**Intra-org spoof intelligence** detects and blocks spoof attempts from a domain within the organization.</span></span>

4. <span data-ttu-id="8489c-137">**跨域欺骗智能** 检测并阻止来自组织外部的域的欺骗尝试。</span><span class="sxs-lookup"><span data-stu-id="8489c-137">**Cross-domain spoof intelligence** detects and blocks spoof attempts from a domain outside of the organization.</span></span>

5. <span data-ttu-id="8489c-138">**批量筛选** 允许管理员配置批量可信度 (BCL) 指示邮件是否从批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="8489c-138">**Bulk filtering** lets admins configure a bulk confidence level (BCL) indicating whether the message was sent from a bulk sender.</span></span> <span data-ttu-id="8489c-139">管理员可以使用反垃圾邮件策略中的批量滑块决定要视为垃圾邮件的批量邮件的级别。</span><span class="sxs-lookup"><span data-stu-id="8489c-139">Administrators can use the Bulk Slider in the Antispam policy to decide what level of bulk mail to treat as spam.</span></span>

6. <span data-ttu-id="8489c-140">**邮箱智能** 从标准用户电子邮件行为中学习。</span><span class="sxs-lookup"><span data-stu-id="8489c-140">**Mailbox intelligence** learns from standard user email behaviors.</span></span> <span data-ttu-id="8489c-141">它利用用户的通信图来检测发件人何时看起来只是用户通常通信但实际上是恶意的人。</span><span class="sxs-lookup"><span data-stu-id="8489c-141">It leverages a user's communication graph to detect when a sender only appears to be someone the user usually communicates with, but is actually malicious.</span></span> <span data-ttu-id="8489c-142">此方法检测模拟。</span><span class="sxs-lookup"><span data-stu-id="8489c-142">This method detects impersonation.</span></span>

7. <span data-ttu-id="8489c-143">**邮箱智能模拟** 基于每个用户的单个发件人映射启用或禁用增强的模拟结果。</span><span class="sxs-lookup"><span data-stu-id="8489c-143">**Mailbox intelligence impersonation** enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="8489c-144">启用后，此功能有助于识别模拟。</span><span class="sxs-lookup"><span data-stu-id="8489c-144">When enabled, this feature helps to identify impersonation.</span></span>

8. <span data-ttu-id="8489c-145">**用户模拟** 允许管理员创建可能模拟的高值目标列表。</span><span class="sxs-lookup"><span data-stu-id="8489c-145">**User impersonation** allows an admin to create a list of high value targets likely to be impersonated.</span></span> <span data-ttu-id="8489c-146">如果邮件到达发件人看起来与受保护的高值帐户相同的名称和地址，则标记该邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-146">If a mail arrives where the sender only appears to have the same name and address as the protected high value account, the mail is marked or tagged.</span></span> <span data-ttu-id="8489c-147"> (例如 *，tr cye@contoso.com* for *tracye@contoso.com) 。*</span><span class="sxs-lookup"><span data-stu-id="8489c-147">(For example, *trαcye@contoso.com* for *tracye@contoso.com*).</span></span>

9. <span data-ttu-id="8489c-148">**域模拟** 可检测类似于收件人域且尝试看起来像内部域的域。</span><span class="sxs-lookup"><span data-stu-id="8489c-148">**Domain impersonation** detects domains that are similar to the recipient's domain and that attempt to look like an internal domain.</span></span> <span data-ttu-id="8489c-149">例如，此模拟tracye@liw re.com tracye@litware.com。 </span><span class="sxs-lookup"><span data-stu-id="8489c-149">For example, this impersonation *tracye@liwαre.com* for *tracye@litware.com*.</span></span>

## <a name="phase-3---content-filtering"></a><span data-ttu-id="8489c-150">阶段 3 - 内容筛选</span><span class="sxs-lookup"><span data-stu-id="8489c-150">Phase 3 - Content Filtering</span></span>

<span data-ttu-id="8489c-151">在此阶段，筛选堆栈开始处理邮件的特定内容，包括其超链接和附件。</span><span class="sxs-lookup"><span data-stu-id="8489c-151">In this phase the filtering stack begins to handle the specific contents of the mail, including its hyperlinks and attachments.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO 中的筛选阶段 3 是内容筛选。":::

1. <span data-ttu-id="8489c-153">**传输 (** 也称为邮件流规则或 Exchange 传输规则) 当邮件满足同样广泛的条件时，管理员可采取各种操作。</span><span class="sxs-lookup"><span data-stu-id="8489c-153">**Transport rules** (also known as mail flow rules or Exchange transport rules) allow an admin to take a wide range of actions when an equally wide range of conditions are met for a message.</span></span> <span data-ttu-id="8489c-154">根据已启用的邮件流规则/传输规则评估通过组织传递的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-154">All messages that flow through your organization are evaluated against the enabled mail flow rules / transport rules.</span></span>

2. <span data-ttu-id="8489c-155">**Microsoft Defender 防病毒** 和两个第三方 *防病毒* 引擎用于检测附件中所有已知的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="8489c-155">**Microsoft Defender Antivirus** and two *third-party Antivirus engines* are used to detect all known malware in attachments.</span></span>

3. <span data-ttu-id="8489c-156">防病毒 (AV) 引擎也用于真正键入所有附件，以便类型阻止可以阻止管理员指定类型的所有附件。</span><span class="sxs-lookup"><span data-stu-id="8489c-156">The anti-virus (AV) engines are also used to true-type all attachments, so that **Type blocking** can block all attachments of types the admin specifies.</span></span>

4. <span data-ttu-id="8489c-157">只要 Microsoft Defender for Office 365 检测到恶意附件，文件哈希及其活动内容的哈希就会添加到 Exchange Online Protection (EOP) 信誉。</span><span class="sxs-lookup"><span data-stu-id="8489c-157">Whenever Microsoft Defender for Office 365 detects a malicious attachment, the file's hash, and a hash of its active content, are added to Exchange Online Protection (EOP) reputation.</span></span> <span data-ttu-id="8489c-158">**附件信誉阻止** 会通过 MSAV 云调用在所有 Office 365 和终结点上阻止该文件。</span><span class="sxs-lookup"><span data-stu-id="8489c-158">**Attachment reputation blocking** will block that file across all Office 365, and on endpoints, through MSAV cloud calls.</span></span>

5. <span data-ttu-id="8489c-159">**启发式群集** 可以基于传递启发确定文件是否可疑。</span><span class="sxs-lookup"><span data-stu-id="8489c-159">**Heuristic clustering** can determine that a file is suspicious based on delivery heuristics.</span></span> <span data-ttu-id="8489c-160">当发现可疑附件时，整个市场活动将暂停，文件将沙盒。</span><span class="sxs-lookup"><span data-stu-id="8489c-160">When a suspicious attachment is found, the entire campaign pauses, and the file is sandboxed.</span></span> <span data-ttu-id="8489c-161">如果发现该文件是恶意的，将阻止整个市场活动。</span><span class="sxs-lookup"><span data-stu-id="8489c-161">If the file is found to be malicious, the entire campaign is blocked.</span></span>

6. <span data-ttu-id="8489c-162">**机器学习模型** 作用于邮件头、正文内容和 URL，以检测网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="8489c-162">**Machine learning models** act on the header, body content, and URLs of a message to detect phishing attempts.</span></span>

7. <span data-ttu-id="8489c-163">Microsoft 使用来自 URL 沙盒的信誉以及 URL 信誉阻止中第三方源的 **URL** 信誉来阻止任何包含已知恶意 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-163">Microsoft uses a determination of reputation from URL sandboxing as well as URL reputation from third party feeds in **URL reputation blocking**, to block any message with a known malicious URL.</span></span>

8. <span data-ttu-id="8489c-164">**内容启发式功能** 可以使用机器学习模型，根据邮件正文中的结构和字词频率检测可疑邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-164">**Content heuristics** can detect suspicious messages based on structure and word frequency within the body of the message, using machine learning models.</span></span>

9. <span data-ttu-id="8489c-165">**安全附件** 将适用于 Office 365 客户的 Defender 每个附件都沙盒化，使用动态分析检测之前未发现的威胁。</span><span class="sxs-lookup"><span data-stu-id="8489c-165">**Safe Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.</span></span>

10. <span data-ttu-id="8489c-166">**链接内容触发** 将电子邮件中链接到文件的每一个 URL 视为附件，在传送时以异步方式对文件进行沙盒处理。</span><span class="sxs-lookup"><span data-stu-id="8489c-166">**Linked content detonation** treats every URL linking to a file in an email as an attachment, asynchronously sandboxing the file at the time of delivery.</span></span>

11. <span data-ttu-id="8489c-167">**当上游** 防钓鱼技术发现邮件或 URL 可疑时，会发生 URL 触发。</span><span class="sxs-lookup"><span data-stu-id="8489c-167">**URL Detonation** happens when upstream anti-phishing technology finds a message or URL to be suspicious.</span></span> <span data-ttu-id="8489c-168">URL 触发在传递时对邮件中的 URL 进行沙盒化。</span><span class="sxs-lookup"><span data-stu-id="8489c-168">URL detonation sandboxes the URLs in the message at the time of delivery.</span></span>

## <a name="phase-4---post-delivery-protection"></a><span data-ttu-id="8489c-169">第 4 阶段 - 传递后保护</span><span class="sxs-lookup"><span data-stu-id="8489c-169">Phase 4 - Post-Delivery Protection</span></span>

<span data-ttu-id="8489c-170">最后一个阶段发生在邮件或文件传递之后，对各种邮箱中的邮件以及 Microsoft Teams 等客户端中显示的文件和链接执行。</span><span class="sxs-lookup"><span data-stu-id="8489c-170">The last stage takes place after mail or file delivery, acting on mail that is in various mailboxes and files and links that appear in clients like Microsoft Teams.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="在 Defender for Office 365 中筛选的第 4 阶段是传递后保护。":::

1. <span data-ttu-id="8489c-172">**安全链接** 是 MDO 的单击时保护。</span><span class="sxs-lookup"><span data-stu-id="8489c-172">**Safe Links** is MDO's time-of-click protection.</span></span> <span data-ttu-id="8489c-173">每封邮件中的每个 URL 都打包为指向 Microsoft 安全链接服务器。</span><span class="sxs-lookup"><span data-stu-id="8489c-173">Every URL in every message is wrapped to point to Microsoft Safe Links servers.</span></span> <span data-ttu-id="8489c-174">单击 URL 时，将针对最新信誉检查 URL，然后用户重定向到目标网站。</span><span class="sxs-lookup"><span data-stu-id="8489c-174">When a URL is clicked it is checked against the latest reputation, before the user is redirected to the target site.</span></span> <span data-ttu-id="8489c-175">URL 是异步沙盒，用于更新其信誉。</span><span class="sxs-lookup"><span data-stu-id="8489c-175">The URL is asynchronously sandboxed to update its reputation.</span></span>

2. <span data-ttu-id="8489c-176">**网络钓鱼Zero-Hour ZAP** (自动清除) 反作用地检测并清除已传递到 Exchange Online 邮箱的恶意网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-176">**Phish Zero-Hour Auto-purge (ZAP)** retroactively detects and neutralizes malicious phishing messages that have already been delivered to Exchange Online mailboxes.</span></span>

3. <span data-ttu-id="8489c-177">**恶意软件 ZAP** 会主动检测并中性化已传递到 Exchange Online 邮箱的恶意恶意软件邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-177">**Malware ZAP** retroactively detects and neutralizes malicious malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

4. <span data-ttu-id="8489c-178">**垃圾邮件 ZAP** 可主动检测并中性化已传递到 Exchange Online 邮箱的恶意垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="8489c-178">**Spam ZAP** retroactively detects and neutralizes malicious spam messages that have already been delivered to Exchange Online mailboxes.</span></span>

5. <span data-ttu-id="8489c-179">**与没有** 自动化的任何团队一样，市场活动视图使管理员能够更快、更完整地查看攻击的全局信息。</span><span class="sxs-lookup"><span data-stu-id="8489c-179">**Campaign Views** let administrators see the big picture of an attack, faster and more completely, than any team could without automation.</span></span> <span data-ttu-id="8489c-180">Microsoft 利用整个服务中的大量反网络钓鱼、反垃圾邮件和反恶意软件数据来帮助识别市场活动，然后允许管理员从头到尾调查它们，包括目标、影响和流，这些对象、影响和流也可在可下载的活动写入中提供。</span><span class="sxs-lookup"><span data-stu-id="8489c-180">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns, and then allows admins to investigate them from start to end, including targets, impacts, and flows, that are also available in a downloadable campaign write-up.</span></span>

6. <span data-ttu-id="8489c-181">通过报告邮件外接程序，用户可以轻松地向 Microsoft 报告误报 (错误标记为错误 *)* 或误报 (将错误电子邮件标记为) 以便进一步分析。 </span><span class="sxs-lookup"><span data-stu-id="8489c-181">**The Report Message add-ins** enable people to easily report false positives (good email, mistakenly marked as *bad*) or false negatives (bad email marked as *good*) to Microsoft for further analysis.</span></span>

7. <span data-ttu-id="8489c-182">**Office 客户端的安全链接在** Office 客户端（如 Word、PowerPoint 和 Excel）内部提供相同的单击时安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="8489c-182">**Safe Links for Office clients** offers the same Safe Links time-of-click protection, natively, inside of Office clients like Word, PowerPoint, and Excel.</span></span>

8. <span data-ttu-id="8489c-183">**对 OneDrive、SharePoint** 和 Teams 的保护在 OneDrive、SharePoint 和 Microsoft Teams 内部提供相同的安全附件保护，防止恶意文件。</span><span class="sxs-lookup"><span data-stu-id="8489c-183">**Protection for OneDrive, SharePoint, and Teams** offers the same Safe Attachments protection against malicious files, natively, inside of OneDrive, SharePoint, and Microsoft Teams.</span></span>

9. <span data-ttu-id="8489c-184">当选择指向文件的 URL 后，链接内容触发将显示一个警告页面，直到文件的沙盒完成，并且发现该 URL 是安全的。</span><span class="sxs-lookup"><span data-stu-id="8489c-184">When a URL that points to a file is selected post delivery, **linked content detonation** displays a warning page until the sandboxing of the file is complete, and the URL is found to be safe.</span></span>


## <a name="the-filtering-stack-diagram"></a><span data-ttu-id="8489c-185">筛选堆栈图</span><span class="sxs-lookup"><span data-stu-id="8489c-185">The filtering stack diagram</span></span>

<span data-ttu-id="8489c-186">最终图表 (图表的所有部分一样，) 随着产品的增长和开发 *而发生变化*。</span><span class="sxs-lookup"><span data-stu-id="8489c-186">The final diagram (as with all parts of the diagram composing it) *is subject to change as the product grows and develops*.</span></span> <span data-ttu-id="8489c-187">为此页面添加 **书签，并使用** 你在底部找到的反馈选项（如果需要在更新后询问）。</span><span class="sxs-lookup"><span data-stu-id="8489c-187">Bookmark this page and use the **feedback** option you'll find at the bottom if you need to ask after updates.</span></span> <span data-ttu-id="8489c-188">对于记录，这是按顺序排列的所有阶段的堆栈：</span><span class="sxs-lookup"><span data-stu-id="8489c-188">For your records, this is the the stack with all the phases in order:</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="MDO 中筛选的所有阶段的顺序为 1 到 4。":::

## <a name="more-information"></a><span data-ttu-id="8489c-190">更多信息</span><span class="sxs-lookup"><span data-stu-id="8489c-190">More information</span></span>

<span data-ttu-id="8489c-191">现在是否需要为 Office 365 \***设置** Microsoft Defender _？</span><span class="sxs-lookup"><span data-stu-id="8489c-191">Do you need to set up Microsoft Defender for Office 365 \***right now** _?</span></span> <span data-ttu-id="8489c-192">使用此堆栈_now\*，通过此 [分](protect-against-threats.md) 步操作开始保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="8489c-192">Use this stack, _now\*, with [this step-by-step](protect-against-threats.md) to start protecting your organization.</span></span>

<span data-ttu-id="8489c-193">*特别感谢 MSFTTracyP 和编写团队的文档向 Giulian Garruba 提供此内容*。</span><span class="sxs-lookup"><span data-stu-id="8489c-193">*Special thanks from MSFTTracyP and the docs writing team to Giulian Garruba for this content*.</span></span>
