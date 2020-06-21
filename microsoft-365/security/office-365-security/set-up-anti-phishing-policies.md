---
title: 防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection （EOP）和 Office 365 高级威胁防护（Office 365 ATP）中提供的反网络钓鱼策略。
ms.openlocfilehash: a61123e3d90a4125bf5a8303654973e1b478fc4c
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754660"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="b15e5-103">Microsoft 365 中的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="b15e5-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="b15e5-104">使用 Exchange Online 邮箱、独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）和 Office 365 高级威胁防护（Office 365 ATP）组织在 Microsoft 365 组织中提供配置反网络钓鱼保护设置的策略。</span><span class="sxs-lookup"><span data-stu-id="b15e5-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="b15e5-105">ATP 反网络钓鱼策略仅在具有 Office 365 ATP 的组织中可用。</span><span class="sxs-lookup"><span data-stu-id="b15e5-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="b15e5-106">例如：</span><span class="sxs-lookup"><span data-stu-id="b15e5-106">For example:</span></span>

- <span data-ttu-id="b15e5-107">Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等。</span><span class="sxs-lookup"><span data-stu-id="b15e5-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="b15e5-108">Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b15e5-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="b15e5-109">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="b15e5-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="b15e5-110">作为附加项的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b15e5-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="b15e5-111">所有其他组织都具有反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="b15e5-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="b15e5-112">反网络钓鱼策略和 ATP 反网络钓鱼策略之间的高级别差异如下表所述：</span><span class="sxs-lookup"><span data-stu-id="b15e5-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

||||
|---|:---:|:---:|
|<span data-ttu-id="b15e5-113">**功能**</span><span class="sxs-lookup"><span data-stu-id="b15e5-113">**Feature**</span></span>|<span data-ttu-id="b15e5-114">**防钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="b15e5-114">**Anti-phishing policies**</span></span>|<span data-ttu-id="b15e5-115">**ATP 反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="b15e5-115">**ATP anti-phishing policies**</span></span>|
|<span data-ttu-id="b15e5-116">自动创建的默认策略</span><span class="sxs-lookup"><span data-stu-id="b15e5-116">Automatically created default policy</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b15e5-119">创建自定义策略</span><span class="sxs-lookup"><span data-stu-id="b15e5-119">Create custom policies</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b15e5-122">策略设置<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b15e5-122">Policy settings<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b15e5-125">模拟设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-125">Impersonation settings</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b15e5-127">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-127">Spoof settings</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b15e5-130">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="b15e5-130">Advanced phishing thresholds</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="b15e5-132"><sup>\*</sup>在默认策略中，策略名称和说明为只读（说明为空），您不能指定策略应用于哪个用户（默认策略适用于所有收件人）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="b15e5-133">若要配置反网络钓鱼策略，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="b15e5-133">To configure anti-phishing policies, see the following topics:</span></span>

- [<span data-ttu-id="b15e5-134">在 EOP 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="b15e5-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="b15e5-135">在 Microsoft 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="b15e5-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="b15e5-136">本主题的其余部分介绍了反网络钓鱼策略和 ATP 反网络钓鱼策略中提供的设置。</span><span class="sxs-lookup"><span data-stu-id="b15e5-136">The rest of this topic describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="b15e5-137">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-137">Spoof settings</span></span>

<span data-ttu-id="b15e5-138">哄骗是指电子邮件中的发件人地址（电子邮件客户端中显示的发件人地址）与电子邮件源的域不匹配。</span><span class="sxs-lookup"><span data-stu-id="b15e5-138">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="b15e5-139">有关哄骗的详细信息，请参阅[Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-139">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b15e5-140">以下欺骗设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：</span><span class="sxs-lookup"><span data-stu-id="b15e5-140">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b15e5-141">**反欺骗保护**：启用或禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="b15e5-141">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="b15e5-142">建议您将其保留为启用状态。</span><span class="sxs-lookup"><span data-stu-id="b15e5-142">We recommend that you leave it enabled.</span></span> <span data-ttu-id="b15e5-143">您可以使用**欺骗智能策略**来允许或阻止特定的欺骗内部和外部发件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-143">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="b15e5-144">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-144">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b15e5-145">默认情况下，在 EOP 的默认反网络钓鱼策略中启用了欺骗设置、默认的 ATP 反网络钓鱼策略，以及您创建的新的自定义反网络钓鱼策略或 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="b15e5-145">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="b15e5-146">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="b15e5-146">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b15e5-147">有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-147">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="b15e5-148">对于阻止欺骗发件人发送的邮件，您还可以指定对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="b15e5-148">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="b15e5-149">**将邮件移动到 "垃圾邮件" 文件夹**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="b15e5-149">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="b15e5-150">邮件传递到邮箱并移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b15e5-150">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b15e5-151">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则（默认情况下已启用），邮件将被移动到 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b15e5-151">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b15e5-152">有关详细信息，请参阅[Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-152">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b15e5-153">**隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-153">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b15e5-154">若要了解隔离，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="b15e5-154">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b15e5-155">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="b15e5-155">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b15e5-156">在 Microsoft 365 中以管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="b15e5-156">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b15e5-157">在 Microsoft 365 中查找并以用户的形式发布隔离邮件</span><span class="sxs-lookup"><span data-stu-id="b15e5-157">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="b15e5-158">**未经身份验证的发件人**：启用或禁用 Outlook 中未识别的发件人标识</span><span class="sxs-lookup"><span data-stu-id="b15e5-158">**Unauthenticated Sender**: Enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="b15e5-159">具体来说：</span><span class="sxs-lookup"><span data-stu-id="b15e5-159">Specifically:</span></span>

  - <span data-ttu-id="b15e5-160">如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或[复合身份验证](email-validation-and-authentication.md#composite-authentication) **，** 则会将问号（？）添加到发件人的照片中。</span><span class="sxs-lookup"><span data-stu-id="b15e5-160">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

  - <span data-ttu-id="b15e5-161">如果 "发件人" 地址（电子邮件客户端中显示的邮件发件人）中的域与 DKIM 签名中的域不同或**邮件 "发**件人" 地址中的域不同，则添加 via tag （chris@contoso.com <u>via</u> michelle@fabrikam.com）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-161">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="b15e5-162">有关这些地址的详细信息，请参阅[电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="b15e5-162">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

  <span data-ttu-id="b15e5-163">若要防止将这些标识符添加到特定发件人的邮件中，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="b15e5-163">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

  - <span data-ttu-id="b15e5-164">允许发件人在欺骗智能策略中进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="b15e5-164">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="b15e5-165">有关说明，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-165">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  - <span data-ttu-id="b15e5-166">为发件人域[配置电子邮件身份验证](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-166">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
    - <span data-ttu-id="b15e5-167">对于发件人照片中的问号，SPF 或 DKIM 是最重要的。</span><span class="sxs-lookup"><span data-stu-id="b15e5-167">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
    - <span data-ttu-id="b15e5-168">对于 via 标记，确认域在 "DKIM" 签名中，或 "发件人地址中的**邮件**" 与 "发件人" 地址中的域（或为其子域）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-168">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

  <span data-ttu-id="b15e5-169">有关详细信息，请参阅[识别可疑邮件在 Outlook.com 和 web 上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="b15e5-169">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b15e5-170">ATP 反网络钓鱼策略中的独占设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-170">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b15e5-171">本节介绍仅在 ATP 反网络钓鱼策略中可用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="b15e5-171">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b15e5-172">默认情况下，未配置或打开 ATP 专用设置，即使在默认策略中也是如此。</span><span class="sxs-lookup"><span data-stu-id="b15e5-172">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="b15e5-173">若要利用这些功能，您需要在默认的 ATP 反网络钓鱼策略中启用和配置这些功能，或者创建和配置自定义 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="b15e5-173">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="policy-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b15e5-174">ATP 反网络钓鱼策略中的策略设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-174">Policy settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b15e5-175">以下策略设置仅适用于 ATP 反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="b15e5-175">The following policy settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b15e5-176">**名称**：无法重命名默认的反网络钓鱼策略，但可以命名和重命名所创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b15e5-176">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="b15e5-177">**说明**您不能将说明添加到默认的反网络钓鱼策略中，但可以添加和更改所创建的自定义策略的说明。</span><span class="sxs-lookup"><span data-stu-id="b15e5-177">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="b15e5-178">**应用**于：标识 ATP 反网络钓鱼策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-178">**Applied to**: Identifies internal recipients that the ATP anti-phishing policy applies to.</span></span> <span data-ttu-id="b15e5-179">此值在自定义策略中是必需的，在默认策略中不可用（默认策略适用于所有收件人）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-179">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

    <span data-ttu-id="b15e5-180">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="b15e5-180">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b15e5-181">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-181">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b15e5-182">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-182">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="b15e5-183">**收件人为**：组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-183">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="b15e5-184">**收件人是**组织中的一个或多个组的成员：</span><span class="sxs-lookup"><span data-stu-id="b15e5-184">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="b15e5-185">**收件人域为**： Microsoft 365 中已配置的一个或多个接受的域。</span><span class="sxs-lookup"><span data-stu-id="b15e5-185">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="b15e5-186">例外情况**除外**：规则例外。</span><span class="sxs-lookup"><span data-stu-id="b15e5-186">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="b15e5-187">设置和行为与条件完全一样：</span><span class="sxs-lookup"><span data-stu-id="b15e5-187">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="b15e5-188">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="b15e5-188">**Recipient is**</span></span>
    - <span data-ttu-id="b15e5-189">**收件人是的成员**</span><span class="sxs-lookup"><span data-stu-id="b15e5-189">**Recipient is a member of**</span></span>
    - <span data-ttu-id="b15e5-190">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="b15e5-190">**The recipient domain is**</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b15e5-191">ATP 反网络钓鱼策略中的模拟设置</span><span class="sxs-lookup"><span data-stu-id="b15e5-191">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b15e5-192">模拟是邮件中发件人或发件人的电子邮件域类似于真实的发件人或域：</span><span class="sxs-lookup"><span data-stu-id="b15e5-192">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="b15e5-193">域 contoso.com 的模拟示例是ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="b15e5-193">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>

- <span data-ttu-id="b15e5-194">用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b15e5-194">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="b15e5-195">其他情况下，模拟域可能被视为合法的（注册域、配置的电子邮件身份验证记录等），但其目的是欺骗收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-195">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="b15e5-196">以下模拟设置仅适用于 ATP 反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="b15e5-196">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b15e5-197">**要保护的用户**：阻止模拟指定的内部或外部用户。</span><span class="sxs-lookup"><span data-stu-id="b15e5-197">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="b15e5-198">例如，高级管理人员（内部）和董事会成员（外部）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-198">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="b15e5-199">您可以添加最高为60的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="b15e5-199">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="b15e5-200">此受保护的用户列表与**应用**于设置的策略所适用的收件人列表不同。</span><span class="sxs-lookup"><span data-stu-id="b15e5-200">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b15e5-201">例如，在应用于名为 "主管" 的组的策略中，将 Felipe Apodaca （felipea@contoso.com）指定为受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="b15e5-201">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="b15e5-202">发送给执行人员组成员的入站邮件将由策略（为模拟用户配置的操作）处理 Felipe Apodaca。</span><span class="sxs-lookup"><span data-stu-id="b15e5-202">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="b15e5-203">**要保护的域**：阻止模拟指定的域。</span><span class="sxs-lookup"><span data-stu-id="b15e5-203">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="b15e5-204">例如，您拥有的所有域（[接受域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)）或特定域（拥有或合作伙伴域的域）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-204">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="b15e5-205">此受保护域的列表与**应用**于设置的策略所适用的域列表不同。</span><span class="sxs-lookup"><span data-stu-id="b15e5-205">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b15e5-206">例如，将 tailspintoys.com 指定为应用于名为 "主管" 的组成员的策略中的受保护域。</span><span class="sxs-lookup"><span data-stu-id="b15e5-206">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="b15e5-207">发送到 tailspintoys.com 在其中模拟的行政组成员的入站邮件将由策略处理（为模拟域配置的操作）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-207">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="b15e5-208">**针对受保护的用户或域的操作**：选择对入站邮件执行的操作，这些邮件包含对策略中的受保护用户和受保护域的模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="b15e5-208">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="b15e5-209">您可以为受保护的用户和模拟的受保护域的模拟指定不同的操作：</span><span class="sxs-lookup"><span data-stu-id="b15e5-209">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="b15e5-210">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="b15e5-210">**Don't apply any action**</span></span>

  - <span data-ttu-id="b15e5-211">将**邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-211">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="b15e5-212">**将邮件移动到 "垃圾邮件" 文件夹**：邮件将传递到邮箱并移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b15e5-212">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b15e5-213">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则（默认情况下已启用），邮件将被移动到 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b15e5-213">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b15e5-214">有关详细信息，请参阅[Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-214">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="b15e5-215">**隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-215">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b15e5-216">若要了解隔离，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="b15e5-216">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="b15e5-217">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="b15e5-217">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b15e5-218">在 Microsoft 365 中以管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="b15e5-218">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b15e5-219">在 Microsoft 365 中查找并以用户的形式发布隔离邮件</span><span class="sxs-lookup"><span data-stu-id="b15e5-219">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="b15e5-220">**传递邮件并向 "密件抄送" 行添加其他地址**：将邮件传递给预期收件人，并以无提示方式将邮件传递给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-220">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="b15e5-221">**邮件传递前将其删除**：悄悄删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="b15e5-221">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="b15e5-222">**安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：</span><span class="sxs-lookup"><span data-stu-id="b15e5-222">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="b15e5-223">**模拟用户**： "发件人" 地址包含受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="b15e5-223">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="b15e5-224">**模拟域**： "发件人" 地址包含受保护的域。</span><span class="sxs-lookup"><span data-stu-id="b15e5-224">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="b15e5-225">**异常字符**： "发件人" 地址包含受保护的发件人或域中的异常字符集（例如，数学符号和文本或大写和小写字母的组合）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-225">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="b15e5-226">**邮箱智能**：启用或禁用用于确定用户的电子邮件模式与其常用联系人的人工智能（AI）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-226">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="b15e5-227">此设置可帮助 AI 区分合法和欺骗的电子邮件与这些联系人。</span><span class="sxs-lookup"><span data-stu-id="b15e5-227">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="b15e5-228">邮箱智能仅适用于 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b15e5-228">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b15e5-229">**基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图启用或禁用增强的模拟结果。</span><span class="sxs-lookup"><span data-stu-id="b15e5-229">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="b15e5-230">此智能允许 Microsoft 365 自定义用户模拟检测，并更好地处理误报。</span><span class="sxs-lookup"><span data-stu-id="b15e5-230">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="b15e5-231">当检测到用户模拟时，您可以定义对邮件执行的特定操作：</span><span class="sxs-lookup"><span data-stu-id="b15e5-231">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="b15e5-232">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="b15e5-232">**Don't apply any action**</span></span>
  - <span data-ttu-id="b15e5-233">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="b15e5-233">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="b15e5-234">**将邮件移动到 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="b15e5-234">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="b15e5-235">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="b15e5-235">**Quarantine the message**</span></span>
  - <span data-ttu-id="b15e5-236">**传递邮件并向 "密件抄送" 行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="b15e5-236">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="b15e5-237">**邮件传递前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="b15e5-237">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="b15e5-238">**受信任的发件人和域**：模拟保护设置的例外。</span><span class="sxs-lookup"><span data-stu-id="b15e5-238">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="b15e5-239">来自指定发件人和发件人域的邮件永远不会归为策略的基于模拟的攻击。</span><span class="sxs-lookup"><span data-stu-id="b15e5-239">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="b15e5-240">换句话说，受保护的发件人、受保护域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。</span><span class="sxs-lookup"><span data-stu-id="b15e5-240">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="b15e5-241">这些列表的最大限制约为1000个条目。</span><span class="sxs-lookup"><span data-stu-id="b15e5-241">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="b15e5-242">ATP 反网络钓鱼策略中的高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="b15e5-242">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="b15e5-243">以下高级网络钓鱼阈值仅在 ATP 反网络钓鱼策略中可用，以控制将机器学习模型应用于邮件以确定仿冒判定的邮件的灵敏度：</span><span class="sxs-lookup"><span data-stu-id="b15e5-243">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="b15e5-244">**1-Standard**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="b15e5-244">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="b15e5-245">对邮件执行的操作的严重性取决于邮件是网络钓鱼的置信度（低、中、高或非常高的可信度）。</span><span class="sxs-lookup"><span data-stu-id="b15e5-245">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="b15e5-246">例如，以非常高的可信度标识为网络钓鱼的邮件会应用最严重的操作，而标识为具有较低可信度的网络钓鱼的邮件则应用了较少的严重操作。</span><span class="sxs-lookup"><span data-stu-id="b15e5-246">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="b15e5-247">**2-严格**：被标识为高度可信度的网络钓鱼的邮件被视为以非常高的可信度进行识别。</span><span class="sxs-lookup"><span data-stu-id="b15e5-247">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b15e5-248">**3-更主动**：被标识为中等或高可信度的网络钓鱼的邮件将被视为以非常高的可信度进行识别。</span><span class="sxs-lookup"><span data-stu-id="b15e5-248">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b15e5-249">**4-最严格**：被标识为低、中或高可信度的网络钓鱼的邮件被视为以非常高的置信度进行标识。</span><span class="sxs-lookup"><span data-stu-id="b15e5-249">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="b15e5-250">误报（正确的邮件被标记为坏）可能会随着此设置的增加而增加。</span><span class="sxs-lookup"><span data-stu-id="b15e5-250">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="b15e5-251">有关推荐设置的信息，请参阅[OFFICE ATP 反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b15e5-251">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>