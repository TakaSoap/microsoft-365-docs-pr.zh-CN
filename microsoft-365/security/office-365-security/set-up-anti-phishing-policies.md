---
title: 防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护的 Office 365 ATP 策略 (网络钓鱼) 。
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825097"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="50619-103">Microsoft 365 中的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="50619-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="50619-104">用于配置反网络钓鱼保护设置的策略在具有 Exchange Online 邮箱的 Microsoft 365 组织中可用，具有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织，以及 Office 365 高级威胁防护 (Office 365 ATP) 组织。</span><span class="sxs-lookup"><span data-stu-id="50619-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="50619-105">ATP 防钓鱼策略仅适用于已安装 Office 365 ATP 的组织。</span><span class="sxs-lookup"><span data-stu-id="50619-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="50619-106">例如：</span><span class="sxs-lookup"><span data-stu-id="50619-106">For example:</span></span>

- <span data-ttu-id="50619-107">Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等</span><span class="sxs-lookup"><span data-stu-id="50619-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="50619-108">Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="50619-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="50619-109">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="50619-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="50619-110">Office 365 ATP 作为加载项</span><span class="sxs-lookup"><span data-stu-id="50619-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="50619-111">所有其他组织都有防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="50619-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="50619-112">下表介绍了防钓鱼策略与 ATP 防钓鱼策略之间的高级别差异：</span><span class="sxs-lookup"><span data-stu-id="50619-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="50619-113">功能</span><span class="sxs-lookup"><span data-stu-id="50619-113">Feature</span></span>|<span data-ttu-id="50619-114">防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="50619-114">Anti-phishing policies</span></span>|<span data-ttu-id="50619-115">ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="50619-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="50619-116">自动创建的默认策略</span><span class="sxs-lookup"><span data-stu-id="50619-116">Automatically created default policy</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="50619-119">创建自定义策略</span><span class="sxs-lookup"><span data-stu-id="50619-119">Create custom policies</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="50619-122">策略设置<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="50619-122">Policy settings<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="50619-125">模拟设置</span><span class="sxs-lookup"><span data-stu-id="50619-125">Impersonation settings</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="50619-127">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="50619-127">Spoof settings</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="50619-130">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="50619-130">Advanced phishing thresholds</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="50619-132"><sup>\*</sup> 在默认策略中，策略名称和说明是只读的 (说明为空) ，并且不能指定谁应用到策略 (则默认策略应用于所有收件人) 。</span><span class="sxs-lookup"><span data-stu-id="50619-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="50619-133">若要配置防钓鱼策略，请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="50619-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="50619-134">在 EOP 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="50619-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="50619-135">在 Microsoft 365 中配置 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="50619-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="50619-136">本文的其余部分介绍了反网络钓鱼策略和 ATP 防钓鱼策略中可用的设置。</span><span class="sxs-lookup"><span data-stu-id="50619-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="50619-137">策略设置</span><span class="sxs-lookup"><span data-stu-id="50619-137">Policy settings</span></span>

<span data-ttu-id="50619-138">防钓鱼策略和 ATP 防钓鱼策略中提供以下策略设置：</span><span class="sxs-lookup"><span data-stu-id="50619-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="50619-139">**名称**：您不能重命名默认的反网络钓鱼策略，但可以命名和重命名您创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="50619-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="50619-140">**描述** 您无法向默认的反网络钓鱼策略添加描述，但可以添加和更改您创建的自定义策略的说明。</span><span class="sxs-lookup"><span data-stu-id="50619-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="50619-141">**应用于**：标识将要应用反网络钓鱼策略的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="50619-142">在自定义策略中需要使用此值，并且在默认策略中不可用， (默认策略应用于所有) 。</span><span class="sxs-lookup"><span data-stu-id="50619-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="50619-143">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="50619-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="50619-144">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="50619-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="50619-145">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="50619-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="50619-146">**收件人是**：组织中一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="50619-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="50619-147">**收件人为以下组的成员**：您所在组织的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="50619-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="50619-148">**收件人域是**：Microsoft 365 中配置的一个或多个接受的域。</span><span class="sxs-lookup"><span data-stu-id="50619-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="50619-149">**除外**：该规则的例外情况。</span><span class="sxs-lookup"><span data-stu-id="50619-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="50619-150">设置和行为与条件完全一样：</span><span class="sxs-lookup"><span data-stu-id="50619-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="50619-151">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="50619-151">**Recipient is**</span></span>
    - <span data-ttu-id="50619-152">**收件人为以下组的成员**</span><span class="sxs-lookup"><span data-stu-id="50619-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="50619-153">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="50619-153">**The recipient domain is**</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="50619-154">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="50619-154">Spoof settings</span></span>

<span data-ttu-id="50619-155">欺骗是电子邮件中的发件人地址 (电子邮件客户端地址与电子邮件源的域不匹配) 的发件人地址。</span><span class="sxs-lookup"><span data-stu-id="50619-155">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="50619-156">有关欺骗的详细信息，请参阅 Microsoft [365 中的防欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="50619-156">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="50619-157">防钓鱼策略和 ATP 防钓鱼策略中提供以下欺骗性设置：</span><span class="sxs-lookup"><span data-stu-id="50619-157">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="50619-158">**防欺骗保护**：启用或禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="50619-158">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="50619-159">建议将其保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="50619-159">We recommend that you leave it enabled.</span></span> <span data-ttu-id="50619-160">使用欺 **骗智能策略来** 允许或阻止特定欺骗性的内部和外部发件人。</span><span class="sxs-lookup"><span data-stu-id="50619-160">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="50619-161">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="50619-161">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="50619-162">在 EOP 的默认反网络钓鱼策略、默认 ATP 防钓鱼策略和你创建的自定义反网络钓鱼策略或 ATP 防钓鱼策略中，默认情况下会启用欺骗设置。</span><span class="sxs-lookup"><span data-stu-id="50619-162">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="50619-163">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;改为启用连接器的增强筛选功能。</span><span class="sxs-lookup"><span data-stu-id="50619-163">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="50619-164">有关说明，请参阅["增强的 Exchange Online 中的连接器筛选"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="50619-164">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="50619-165">对于来自受阻止的欺骗性发件人的邮件，你还可以指定要对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="50619-165">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="50619-166">**将邮件移动到垃圾邮件文件夹**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="50619-166">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="50619-167">邮件递送到邮箱，并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="50619-167">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="50619-168">如果对邮箱邮箱启用了默认的垃圾邮件规则，则邮件) 移动到"垃圾邮件" (。</span><span class="sxs-lookup"><span data-stu-id="50619-168">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="50619-169">有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="50619-169">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="50619-170">**隔离邮件：将**邮件发送到隔离，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-170">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="50619-171">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="50619-171">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="50619-172">在 Microsoft 365 隔离</span><span class="sxs-lookup"><span data-stu-id="50619-172">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="50619-173">在 Microsoft 365 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="50619-173">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="50619-174">在 Microsoft 365 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="50619-174">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="50619-175">**Unauthenticated Sender：** 请参阅下一节中的说明。</span><span class="sxs-lookup"><span data-stu-id="50619-175">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="50619-176">未经身份验证的发件人</span><span class="sxs-lookup"><span data-stu-id="50619-176">Unauthenticated Sender</span></span>

<span data-ttu-id="50619-177">未经身份验证的发件人标识是防钓鱼策略和 ATP 反网络钓鱼策略中提供的欺骗设置的一部分，如上一节所述。 [Spoof settings](#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="50619-177">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="50619-178">" **未经身份验证的** 发件人"设置启用或禁用 Outlook 中未经识别的发件人标识。</span><span class="sxs-lookup"><span data-stu-id="50619-178">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="50619-179">具体来说：</span><span class="sxs-lookup"><span data-stu-id="50619-179">Specifically:</span></span>

- <span data-ttu-id="50619-180">如果邮件未通过 SPF ) 或 DKIM 检查并且邮件未通过 DMARC**and**或复合身份验证，则将一个问号 (？"复选框中的标识添加到发件人[的照片](email-validation-and-authentication.md#composite-authentication)中。</span><span class="sxs-lookup"><span data-stu-id="50619-180">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="50619-181">如果 <u>"发件人</u> (chris@contoso.com"中的域不同 (电子邮件客户端) 中显示的邮件发件人不同于 DKIM 签名或 **MAIL FROM** 地址中的域，通过 michelle@fabrikam.com) 添加的邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="50619-181">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="50619-182">有关这些地址的详细信息，请参阅 [电子邮件标准的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="50619-182">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="50619-183">为防止将这些标识符添加到来自特定发件人的邮件，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="50619-183">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="50619-184">允许发件人在欺骗智能策略中进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="50619-184">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="50619-185">有关说明，请参阅在 [Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="50619-185">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="50619-186">[为发件人域](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 配置电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="50619-186">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="50619-187">对于发件人照片中的问号，SPF 或 DKIM 最重要。</span><span class="sxs-lookup"><span data-stu-id="50619-187">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="50619-188">对于通过标记，确认 DKIM 签名中的域或者 **MAIL FROM** 地址与 (匹配，或者是发件人地址中该域) 子域的子域。</span><span class="sxs-lookup"><span data-stu-id="50619-188">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="50619-189">有关详细信息，请参阅 ["在 Outlook 和 Web 上的 Outlook Outlook.com中识别可疑邮件](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="50619-189">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="50619-190">ATP 防钓鱼策略中的独占设置</span><span class="sxs-lookup"><span data-stu-id="50619-190">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="50619-191">本部分介绍仅在 ATP 防钓鱼策略中可用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="50619-191">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="50619-192">默认情况下，ATP 独占设置未配置或打开，即使在默认策略中也是个设置。</span><span class="sxs-lookup"><span data-stu-id="50619-192">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="50619-193">要利用这些功能，需要在默认 ATP 防钓鱼策略中启用和配置这些功能，或创建和配置自定义 ATP 防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="50619-193">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="50619-194">ATP 防钓鱼策略中的模拟设置</span><span class="sxs-lookup"><span data-stu-id="50619-194">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="50619-195">模拟是邮件中的发件人或发件人电子邮件域与实际发件人或域的相似位置：</span><span class="sxs-lookup"><span data-stu-id="50619-195">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="50619-196">例如，将域记录contoso.com源ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="50619-196">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="50619-197">有关对用户进行设置的michelle@contoso.com示例michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="50619-197">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="50619-198">仿模拟域可能被视为合法的 (注册域、配置的电子邮件身份验证记录 ) 等，但其目的是拒绝收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-198">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="50619-199">以下模拟设置仅在 ATP 防钓鱼策略中提供：</span><span class="sxs-lookup"><span data-stu-id="50619-199">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="50619-200">**保护的用户**：防止模拟指定的内部或外部用户。</span><span class="sxs-lookup"><span data-stu-id="50619-200">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="50619-201">例如，主管人员 (外的) 板 (板) 。</span><span class="sxs-lookup"><span data-stu-id="50619-201">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="50619-202">最多可以添加 60 个内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="50619-202">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="50619-203">此受保护的用户列表与该策略应用于设置中的收件人 **列表** 不同。</span><span class="sxs-lookup"><span data-stu-id="50619-203">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="50619-204">例如，在应用于名为"管理人员"的 (felipea@contoso.com) 的策略中，将 Felipe Apodaca 指定为受保护用户。</span><span class="sxs-lookup"><span data-stu-id="50619-204">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="50619-205">将按策略输入为模拟的用户配置的操作，将对向执行人员组成员 (发送 Felipe Apodaca 的入站邮件执行) 。</span><span class="sxs-lookup"><span data-stu-id="50619-205">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="50619-206">**要保护**的域：阻止模拟指定域。</span><span class="sxs-lookup"><span data-stu-id="50619-206">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="50619-207">例如，您拥有的域 ([接受的域，) ](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 或特定 (您拥有或合作伙伴域) 。</span><span class="sxs-lookup"><span data-stu-id="50619-207">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="50619-208">此受保护域列表不同于该策略应用于设置中的 **域** 列表。</span><span class="sxs-lookup"><span data-stu-id="50619-208">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="50619-209">例如，您可tailspintoys.com为策略中应用于名为 Executives 的成员的受保护域。</span><span class="sxs-lookup"><span data-stu-id="50619-209">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="50619-210">向管理人员组成员发送 tailspintoys.com的入站邮件将由策略类型 (为模拟域管理员配置的操作对) 。</span><span class="sxs-lookup"><span data-stu-id="50619-210">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="50619-211">**受保护的用户或域的操作**：选择要对包含在策略中的受保护用户和受保护的域进行模拟尝试的入站邮件时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="50619-211">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="50619-212">您可以指定其他操作以模拟受保护的用户和模拟受保护的域：</span><span class="sxs-lookup"><span data-stu-id="50619-212">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="50619-213">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="50619-213">**Don't apply any action**</span></span>

  - <span data-ttu-id="50619-214">**重定向至其他电子邮件地址**：将邮件发送给指定收件人，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-214">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="50619-215">**"将邮件移动到垃圾邮件**文件夹：邮件递送到邮箱"并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="50619-215">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="50619-216">如果对邮箱邮箱启用了默认的垃圾邮件规则，则邮件) 移动到"垃圾邮件" (。</span><span class="sxs-lookup"><span data-stu-id="50619-216">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="50619-217">有关详细信息，请参阅在 [Microsoft 365 中配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="50619-217">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="50619-218">**隔离邮件：将**邮件发送到隔离，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-218">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="50619-219">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="50619-219">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="50619-220">在 Microsoft 365 隔离</span><span class="sxs-lookup"><span data-stu-id="50619-220">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="50619-221">在 Microsoft 365 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="50619-221">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="50619-222">在 Microsoft 365 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="50619-222">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="50619-223">**传递邮件并向密件抄送行添加其他地址：** 将邮件传递给目标收件人并以静默方式将邮件传递给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="50619-223">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="50619-224">**在邮件传递前将其删除：** 自动删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="50619-224">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="50619-225">**安全提示：** 启用或禁用以下会显示将会检查失败的消息的模拟安全提示：</span><span class="sxs-lookup"><span data-stu-id="50619-225">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="50619-226">**模拟用户："** 发件人"地址包含受保护用户。</span><span class="sxs-lookup"><span data-stu-id="50619-226">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="50619-227">**模拟域："** 发件人"地址包含受保护域。</span><span class="sxs-lookup"><span data-stu-id="50619-227">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="50619-228">**不常见的**字符："发件人"地址包含异常字符集 (例如，数字符号和文本，或者是受保护的发件人或域中大写和小写字母) 的混合。</span><span class="sxs-lookup"><span data-stu-id="50619-228">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="50619-229">**邮箱智能**：根据用户的经常 (联系人，启用或禁用项目智能 (AI) ，该服务将决定用户电子邮件模式。</span><span class="sxs-lookup"><span data-stu-id="50619-229">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="50619-230">此设置可帮助 AI 区分合法电子邮件和欺骗性电子邮件和这些联系人。</span><span class="sxs-lookup"><span data-stu-id="50619-230">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="50619-231">邮箱智能仅适用于 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="50619-231">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="50619-232">**基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图，启用或禁用增强的模拟结果。</span><span class="sxs-lookup"><span data-stu-id="50619-232">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="50619-233">通过此智能，Microsoft 365 可以自定义用户模拟检测，并更好地处理误报。</span><span class="sxs-lookup"><span data-stu-id="50619-233">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="50619-234">检测到用户模拟时，你可以定义要对邮件执行的特定操作：</span><span class="sxs-lookup"><span data-stu-id="50619-234">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="50619-235">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="50619-235">**Don't apply any action**</span></span>
  - <span data-ttu-id="50619-236">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="50619-236">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="50619-237">**将邮件移动到垃圾邮件文件夹**</span><span class="sxs-lookup"><span data-stu-id="50619-237">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="50619-238">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="50619-238">**Quarantine the message**</span></span>
  - <span data-ttu-id="50619-239">**传递邮件并向"送达"行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="50619-239">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="50619-240">**在邮件传递前将其删除**</span><span class="sxs-lookup"><span data-stu-id="50619-240">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="50619-241">**受信任的发件人和域**：模拟保护设置的例外。</span><span class="sxs-lookup"><span data-stu-id="50619-241">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="50619-242">来自指定发件人和发件人域的邮件永远不会被按策略分类为基于模拟的攻击。</span><span class="sxs-lookup"><span data-stu-id="50619-242">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="50619-243">换句话说，对受保护的发件人、受保护的域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。</span><span class="sxs-lookup"><span data-stu-id="50619-243">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="50619-244">这些列表的最大限制是大约 1000 个条目。</span><span class="sxs-lookup"><span data-stu-id="50619-244">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="50619-245">ATP 防钓鱼策略中的高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="50619-245">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="50619-246">以下高级网络钓鱼阈值仅在 ATP 防钓鱼策略中提供，用于控制将机器学习模型应用于消息以确定网络钓鱼是否断开的敏感性：</span><span class="sxs-lookup"><span data-stu-id="50619-246">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="50619-247">**1 - Standard：** 此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="50619-247">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="50619-248">对邮件执行的操作的严重性取决于邮件是网络钓鱼邮件、中、高 (高或非常高可信度) 。</span><span class="sxs-lookup"><span data-stu-id="50619-248">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="50619-249">例如，对于优先级高的网络钓鱼邮件，系统将应用严重操作，而标识为网络钓鱼邮件的重度较低，但可信度较低。</span><span class="sxs-lookup"><span data-stu-id="50619-249">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="50619-250">**2 - 高可行：** 被识别为高可信度的网络钓鱼的邮件被视为是以非常高可信度进行标识的。</span><span class="sxs-lookup"><span data-stu-id="50619-250">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="50619-251">**3 - 更高效：** 识别为具有中等或高可信度的网络钓鱼的邮件被视为是以高可信度确定的。</span><span class="sxs-lookup"><span data-stu-id="50619-251">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="50619-252">**4 - 最高级别：** 标识为低、中或高可信度的网络钓鱼的邮件被视为具有高可信度的网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="50619-252">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="50619-253">误报可能做 (标记为不好的消息) 增加此设置后不良消息。</span><span class="sxs-lookup"><span data-stu-id="50619-253">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="50619-254">有关推荐设置的信息，请参阅 [Office ATP 防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="50619-254">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
