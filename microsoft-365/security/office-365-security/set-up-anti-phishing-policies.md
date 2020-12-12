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
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Microsoft Defender for Office 365 中提供的防钓鱼策略。
ms.openlocfilehash: 34c66d8ab39af443462e8c5ac99009b4170be21e
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659851"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="932c4-103">Microsoft 365 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="932c4-103">Anti-phishing policies in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="932c4-104">配置防钓鱼保护设置的策略适用于具有 Exchange Online 邮箱的 Microsoft 365 组织、没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织和适用于 Office 365 的 Microsoft Defender 组织。</span><span class="sxs-lookup"><span data-stu-id="932c4-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Microsoft Defender for Office 365 organizations.</span></span>

<span data-ttu-id="932c4-105">Microsoft Defender for Office 365 中的反网络钓鱼策略仅适用于具有 Defender for Office 365 的组织。</span><span class="sxs-lookup"><span data-stu-id="932c4-105">Anti-phishing policies in Microsoft Defender for Office 365 are only available in organizations that have Defender for Office 365.</span></span> <span data-ttu-id="932c4-106">例如：</span><span class="sxs-lookup"><span data-stu-id="932c4-106">For example:</span></span>

- <span data-ttu-id="932c4-107">Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等</span><span class="sxs-lookup"><span data-stu-id="932c4-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="932c4-108">Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="932c4-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="932c4-109">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="932c4-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="932c4-110">作为加载项的 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="932c4-110">Microsoft Defender for Office 365 as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="932c4-111">下表介绍了 EOP 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的反网络钓鱼策略之间的高级差异：</span><span class="sxs-lookup"><span data-stu-id="932c4-111">The high-level differences between anti-phishing policies in EOP and anti-phishing policies in Microsoft Defender for Office 365 are described in the following table:</span></span>

****

|<span data-ttu-id="932c4-112">功能</span><span class="sxs-lookup"><span data-stu-id="932c4-112">Feature</span></span>|<span data-ttu-id="932c4-113">EOP 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="932c4-113">Anti-phishing policies in EOP</span></span>|<span data-ttu-id="932c4-114">Microsoft Defender for Office 365 中的防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="932c4-114">Anti-phishing policies in Microsoft Defender for Office 365</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="932c4-115">自动创建的默认策略</span><span class="sxs-lookup"><span data-stu-id="932c4-115">Automatically created default policy</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="932c4-118">创建自定义策略</span><span class="sxs-lookup"><span data-stu-id="932c4-118">Create custom policies</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="932c4-121">策略设置<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="932c4-121">Policy settings<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="932c4-124">模拟设置</span><span class="sxs-lookup"><span data-stu-id="932c4-124">Impersonation settings</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="932c4-126">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="932c4-126">Spoof settings</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="932c4-129">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="932c4-129">Advanced phishing thresholds</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="932c4-131"><sup>\*</sup> 在默认策略中，策略名称和说明是只读的 (说明为空) ，并且你无法指定策略应用于 (默认策略应用于所有收件人) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-131"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="932c4-132">若要配置防钓鱼策略，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="932c4-132">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="932c4-133">在 EOP 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="932c4-133">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="932c4-134">在 Microsoft Defender for Office 365 中配置防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="932c4-134">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="932c4-135">本文的其余部分介绍了 EOP 和 Defender for Office 365 中的反钓鱼策略中可用的设置。</span><span class="sxs-lookup"><span data-stu-id="932c4-135">The rest of this article describes the settings that are available in anti-phishing policies in EOP and Defender for Office 365.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="932c4-136">策略设置</span><span class="sxs-lookup"><span data-stu-id="932c4-136">Policy settings</span></span>

<span data-ttu-id="932c4-137">以下策略设置在 EOP 和 Microsoft Defender for Office 365 中的防钓鱼策略中可用：</span><span class="sxs-lookup"><span data-stu-id="932c4-137">The following policy settings are available in anti-phishing policies in EOP and Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="932c4-138">**名称**：无法重命名默认的防钓鱼策略，但您可以命名和重命名您创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="932c4-138">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="932c4-139">**说明** 无法向默认防钓鱼策略添加说明，但可以添加和更改所创建的自定义策略的说明。</span><span class="sxs-lookup"><span data-stu-id="932c4-139">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="932c4-140">**应用于**：标识应用防钓鱼策略的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-140">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="932c4-141">此值在自定义策略中是必需的，在默认策略 (默认策略应用于所有收件人) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-141">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="932c4-142">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="932c4-142">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="932c4-143">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="932c4-143">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="932c4-144">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="932c4-144">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="932c4-145">**收件人为**：您组织中一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="932c4-145">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="932c4-146">**收件人是组织中** 一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="932c4-146">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="932c4-147">**收件人域为**：Microsoft 365 中配置的一个或多个接受域。</span><span class="sxs-lookup"><span data-stu-id="932c4-147">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="932c4-148">**例外：** 规则例外。</span><span class="sxs-lookup"><span data-stu-id="932c4-148">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="932c4-149">设置和行为与条件完全相同：</span><span class="sxs-lookup"><span data-stu-id="932c4-149">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="932c4-150">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="932c4-150">**Recipient is**</span></span>
    - <span data-ttu-id="932c4-151">**收件人是**</span><span class="sxs-lookup"><span data-stu-id="932c4-151">**Recipient is a member of**</span></span>
    - <span data-ttu-id="932c4-152">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="932c4-152">**The recipient domain is**</span></span>

  > [!NOTE]
  > <span data-ttu-id="932c4-153">自定义 **防** 钓鱼策略中需要"应用于"设置，以标识策略应用于 <u>的邮件收件人</u>。</span><span class="sxs-lookup"><span data-stu-id="932c4-153">The **Applied to** setting is required in custom anti-phishing policies to identify the message **recipients** <u>that the policy applies to</u>.</span></span> <span data-ttu-id="932c4-154">Microsoft Defender for Office 365 中的反网络钓鱼[](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)策略还具有模拟设置，可在其中指定将接收模拟保护的单个<u></u>发件人电子邮件地址或发件人域，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="932c4-154">Anti-phishing policies in Microsoft Defender for Office 365 also have [impersonation settings](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) where you can specify individual sender email addresses or sender domains <u>that will receive impersonation protection</u> as described later in this article.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="932c4-155">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="932c4-155">Spoof settings</span></span>

<span data-ttu-id="932c4-156">欺骗是电子邮件中的发件人地址 (电子邮件客户端中显示发件人地址) 与电子邮件源的域不匹配。</span><span class="sxs-lookup"><span data-stu-id="932c4-156">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="932c4-157">有关欺骗功能详细信息，请参阅 [Microsoft 365](anti-spoofing-protection.md)中的反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="932c4-157">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="932c4-158">EOP 和 Microsoft Defender for Office 365 中的反网络钓鱼策略中提供了以下欺骗设置：</span><span class="sxs-lookup"><span data-stu-id="932c4-158">The following spoof settings are available in anti-phishing policies in EOP and Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="932c4-159">**反欺骗保护**：启用或禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="932c4-159">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="932c4-160">建议保持启用状态。</span><span class="sxs-lookup"><span data-stu-id="932c4-160">We recommend that you leave it enabled.</span></span> <span data-ttu-id="932c4-161">使用欺骗 **智能策略允许** 或阻止特定的欺骗内部和外部发件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-161">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="932c4-162">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="932c4-162">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="932c4-163">默认情况下，在默认防钓鱼策略和您创建的任何新的自定义防钓鱼策略中启用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="932c4-163">Anti-spoofing protection is enabled by default in the default anti-phishing policy and in any new custom anti-phishing policies that you create.</span></span>
  >
  > - <span data-ttu-id="932c4-164">如果 MX 记录未指向 Microsoft 365，无需禁用反欺骗保护;改为启用连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="932c4-164">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="932c4-165">有关说明，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="932c4-165">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="932c4-166">对于来自被阻止的欺骗发件人的邮件，还可以指定对邮件要采取的操作：</span><span class="sxs-lookup"><span data-stu-id="932c4-166">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="932c4-167">**将邮件移动到"垃圾邮件"文件夹**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="932c4-167">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="932c4-168">邮件将传递到邮箱并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="932c4-168">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="932c4-169">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移动到"垃圾邮件"文件夹 (该邮件默认) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-169">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="932c4-170">有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="932c4-170">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="932c4-171">**隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-171">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="932c4-172">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="932c4-172">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="932c4-173">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="932c4-173">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="932c4-174">在 Microsoft 365 中以管理员角色管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="932c4-174">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="932c4-175">在 Microsoft 365 中以用户状态查找并释放隔离邮件</span><span class="sxs-lookup"><span data-stu-id="932c4-175">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="932c4-176">**未经身份验证的发件人**：请参阅下一节中的信息。</span><span class="sxs-lookup"><span data-stu-id="932c4-176">**Unauthenticated Sender**: See the information in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="932c4-177">未经身份验证的发件人</span><span class="sxs-lookup"><span data-stu-id="932c4-177">Unauthenticated Sender</span></span>

<span data-ttu-id="932c4-178">未经身份验证的发件人标识是 EOP 和[](#spoof-settings)Microsoft Defender for Office 365 中的反网络钓鱼策略中提供的欺骗设置的一部分，如上一部分所述。</span><span class="sxs-lookup"><span data-stu-id="932c4-178">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies in EOP and Microsoft Defender for Office 365 as described in the previous section.</span></span>

<span data-ttu-id="932c4-179">" **未经身份验证的发件人"** 设置在 Outlook 中启用或禁用未经身份验证的发件人标识。</span><span class="sxs-lookup"><span data-stu-id="932c4-179">The **Unauthenticated Sender** setting enables or disables unauthenticated sender identification in Outlook.</span></span> <span data-ttu-id="932c4-180">具体来说：</span><span class="sxs-lookup"><span data-stu-id="932c4-180">Specifically:</span></span>

- <span data-ttu-id="932c4-181">如果邮件未通过 SPF 或 DKIM 检查，并且邮件未通过 DMARC 或复合身份验证，则向发件人的照片添加问号[ (？) 。](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="932c4-181">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="932c4-182">禁用未经身份验证的发件人标识可防止将问号添加到发件人的照片中。</span><span class="sxs-lookup"><span data-stu-id="932c4-182">Disabling unauthenticated sender identification prevents the question mark from being added to the sender's photo.</span></span>

- <span data-ttu-id="932c4-183">如果"发件人"地址 <u> (电子邮件</u> 客户端中显示的邮件发件人) 中的域不同于 DKIM 签名或 **MAIL FROM** 地址中的域，则添加通过 michelle@fabrikam.com) 的通过标记。 (chris@contoso.com</span><span class="sxs-lookup"><span data-stu-id="932c4-183">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="932c4-184">有关这些地址详细信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="932c4-184">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

  <span data-ttu-id="932c4-185">如果发件人地址中的域不同于 DKIM 签名中的域或 MAIL FROM 地址中的域，则禁用未经身份验证的发件人标识不会阻止添加通过标记。</span><span class="sxs-lookup"><span data-stu-id="932c4-185">Disabling unauthenticated sender identification does not prevent the via tag from being added if the domain in the From address is different from the domain in the DKIM signature or the MAIL FROM address.</span></span>

<span data-ttu-id="932c4-186">若要阻止向来自特定发件人的邮件添加问号或通过标记，有以下选项：</span><span class="sxs-lookup"><span data-stu-id="932c4-186">To prevent the question mark or via tag from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="932c4-187">允许发件人在欺骗智能策略中欺骗。</span><span class="sxs-lookup"><span data-stu-id="932c4-187">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="932c4-188">当禁用未经身份验证的发件人标识时，此操作将阻止通过标记出现在发件人的邮件中。</span><span class="sxs-lookup"><span data-stu-id="932c4-188">This action will prevent the via tag from appearing in messages from the sender when unauthenticated sender identification is disabled.</span></span> <span data-ttu-id="932c4-189">有关说明，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="932c4-189">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="932c4-190">[为发件人域](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 配置电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="932c4-190">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  - <span data-ttu-id="932c4-191">对于发件人照片中的问号，SPF 或 DKIM 是最重要的。</span><span class="sxs-lookup"><span data-stu-id="932c4-191">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="932c4-192">对于通过标记，请确认 DKIM 签名中的域或 **MAIL FROM** 地址与 (匹配，或是) 地址中域的子域。</span><span class="sxs-lookup"><span data-stu-id="932c4-192">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="932c4-193">有关详细信息，请参阅"识别 Outlook.com [和 Outlook 网页中的可疑邮件](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="932c4-193">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="932c4-194">Microsoft Defender for Office 365 中的防钓鱼策略中的独占设置</span><span class="sxs-lookup"><span data-stu-id="932c4-194">Exclusive settings in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="932c4-195">本部分介绍仅在 Microsoft Defender for Office 365 中的反网络钓鱼策略中可用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="932c4-195">This section describes the policy settings that are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="932c4-196">Microsoft Defender for Office 365 中的默认防钓鱼 [策略为所有](set-up-anti-phishing-policies.md#spoof-settings) 收件人提供欺骗保护和邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="932c4-196">The default anti-phishing policy in Microsoft Defender for Office 365 provides [spoof protection](set-up-anti-phishing-policies.md#spoof-settings) and mailbox intelligence for all recipients.</span></span> <span data-ttu-id="932c4-197">但是，其他可用的 [模拟保护](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高级](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 设置未在默认策略中配置或启用。</span><span class="sxs-lookup"><span data-stu-id="932c4-197">However, the other available [impersonation protection](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) features and [advanced settings](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are not configured or enabled in the default policy.</span></span> <span data-ttu-id="932c4-198">若要启用所有保护功能，请修改默认的防钓鱼策略或创建其他防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="932c4-198">To enable all protection features, modify the default anti-phishing policy or create additional anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="932c4-199">Microsoft Defender for Office 365 中的防钓鱼策略中的模拟设置</span><span class="sxs-lookup"><span data-stu-id="932c4-199">Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="932c4-200">模拟是邮件中发件人或发件人的电子邮件域看起来与真实发件人或域类似的地方：</span><span class="sxs-lookup"><span data-stu-id="932c4-200">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="932c4-201">域 contoso.com 的模拟示例是 ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="932c4-201">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="932c4-202">用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="932c4-202">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="932c4-203">模拟的域可能被视为合法（注册的域、配置的电子邮件身份验证记录等），但其意图是欺骗收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-203">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="932c4-204">以下模拟设置仅适用于 Microsoft Defender for Office 365 中的防钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="932c4-204">The following impersonation settings are only available in anti-phishing policies in Microsoft Defender for Office 365:</span></span>

- <span data-ttu-id="932c4-205">**要保护的用户**：防止指定的内部或外部电子邮件地址被模拟 **为邮件发件人**。</span><span class="sxs-lookup"><span data-stu-id="932c4-205">**Users to protect**: Prevents the specified internal or external email addresses from being impersonated **as message senders**.</span></span> <span data-ttu-id="932c4-206">例如，您收到来自公司副总裁的电子邮件，要求您向她发送一些内部公司信息。</span><span class="sxs-lookup"><span data-stu-id="932c4-206">For example, you receive an email message from the Vice President of your company asking you to send her some internal company information.</span></span> <span data-ttu-id="932c4-207">是否执行？</span><span class="sxs-lookup"><span data-stu-id="932c4-207">Would you do it?</span></span> <span data-ttu-id="932c4-208">许多人在未思考的情况下发送回复。</span><span class="sxs-lookup"><span data-stu-id="932c4-208">Many people would send the reply without thinking.</span></span>

  <span data-ttu-id="932c4-209">您可以使用受保护的用户添加内部和外部发件人电子邮件地址，防止模拟。</span><span class="sxs-lookup"><span data-stu-id="932c4-209">You can use protected users to add internal and external sender email addresses to protect from impersonation.</span></span> <span data-ttu-id="932c4-210">受 **用户模拟** 保护的发件人列表不同于策略应用于默认策略的所有 (收件人的收件人列表; 特定收件人，如"策略设置"部分"应用于"设置 [) 。](#policy-settings)</span><span class="sxs-lookup"><span data-stu-id="932c4-210">This list of **senders** that are protected from user impersonation is different from the list of **recipients** that the policy applies to (all recipients for the default policy; specific recipients as configured in the **Applied to** setting in the [Policy settings](#policy-settings) section).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="932c4-211">在每个防钓鱼策略中，最多可以指定 60 个受保护的 (发件人电子邮件地址) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-211">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="932c4-212">不能在多个策略中指定同一受保护用户。</span><span class="sxs-lookup"><span data-stu-id="932c4-212">You can't specify the same protected user in multiple policies.</span></span>
  >
  > - <span data-ttu-id="932c4-213">如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。</span><span class="sxs-lookup"><span data-stu-id="932c4-213">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="932c4-214">如果发件人和收件人从未通过电子邮件进行通信，邮件将被标识为模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="932c4-214">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

  <span data-ttu-id="932c4-215">默认情况下，不会将发件人电子邮件地址配置为在用户中用于保护模拟 **保护**。</span><span class="sxs-lookup"><span data-stu-id="932c4-215">By default, no sender email addresses are configured for impersonation protection in **Users to protect**.</span></span> <span data-ttu-id="932c4-216">因此，默认情况下，默认策略或自定义策略中的模拟保护不会覆盖发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="932c4-216">Therefore, by default, no sender email addresses are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="932c4-217">向用户添加内部或外部电子邮件地址以保护列表时，来自这些发件人的邮件将接受模拟保护检查。</span><span class="sxs-lookup"><span data-stu-id="932c4-217">When you add internal or external email addresses to the **Users to protect** list, messages from those **senders** are subject to impersonation protection checks.</span></span> <span data-ttu-id="932c4-218">如果邮件发送到应用于默认策略 **的所有** 收件人的收件人，则检查 (是否模拟;**应用于自定义** 策略策略中的) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-218">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="932c4-219">如果在发件人的电子邮件地址中检测到模拟，则用户的模拟保护操作将应用于邮件 (对邮件执行哪些操作，是否显示模拟用户安全提示等) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-219">If impersonation is detected in the sender's email address, the impersonation protections actions for users are applied to the message (what to do with the message, whether to show impersonated users safety tips, etc.).</span></span>

- <span data-ttu-id="932c4-220">**要保护的** 域：防止在邮件发件人的域中模拟 **指定的域**。</span><span class="sxs-lookup"><span data-stu-id="932c4-220">**Domains to protect**: Prevents the specified domains from being impersonated **in the message sender's domain**.</span></span> <span data-ttu-id="932c4-221">例如，你拥有的所有域 ([接受](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或 (域或合作伙伴域) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-221">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="932c4-222">此 **防止模拟** 的发件人域列表不同于策略应用于默认策略的所有 (收件人的收件人列表;特定收件人，如"策略设置"部分"应用于"设置 [) 。](#policy-settings)</span><span class="sxs-lookup"><span data-stu-id="932c4-222">This list of **sender domains** that are protected from impersonation is different from the list of **recipients** that the policy applies to (all recipients for the default policy; specific recipients as configured in the **Applied to** setting in the [Policy settings](#policy-settings) section).</span></span>

  > [!NOTE]
  > <span data-ttu-id="932c4-223">可以在所有反网络钓鱼策略中定义的受保护域的最大数量为 50 个。</span><span class="sxs-lookup"><span data-stu-id="932c4-223">The maximum number of protected domains that you can define in all anti-phishing policies is 50.</span></span>

  <span data-ttu-id="932c4-224">默认情况下，不会将发件人域配置为在域中进行模拟 **保护以保护**。</span><span class="sxs-lookup"><span data-stu-id="932c4-224">By default, no sender domains are configured for impersonation protection in **Domains to protect**.</span></span> <span data-ttu-id="932c4-225">因此，默认情况下，在默认策略或自定义策略中，模拟保护不会覆盖任何发件人域。</span><span class="sxs-lookup"><span data-stu-id="932c4-225">Therefore, by default, no sender domains are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="932c4-226">当您将域添加到 **"域"以保护** 列表时，来自这些域中发件人的邮件将接受模拟保护检查。</span><span class="sxs-lookup"><span data-stu-id="932c4-226">When you add domains to the **Domains to protect** list, messages from **senders in those domains** are subject to impersonation protection checks.</span></span> <span data-ttu-id="932c4-227">如果邮件发送到应用于默认策略 **的所有** 收件人的收件人，则检查 (是否模拟;**应用于自定义** 策略策略中的) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-227">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="932c4-228">如果在发件人域中检测到模拟，域的模拟保护操作将应用于邮件 (对邮件执行什么操作，是否显示模拟用户安全提示等) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-228">If impersonation is detected in the sender's domain, the impersonation protection actions for domains are applied to the message (what to do with the message, whether to show impersonated users safety tips, etc.).</span></span>

- <span data-ttu-id="932c4-229">**针对受保护用户或域的操作**：选择要对入站邮件采取的操作，这些入站邮件包含针对策略中受保护用户和受保护域的模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="932c4-229">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="932c4-230">可以指定用于模拟受保护用户与模拟受保护域的不同操作：</span><span class="sxs-lookup"><span data-stu-id="932c4-230">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="932c4-231">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="932c4-231">**Don't apply any action**</span></span>

  - <span data-ttu-id="932c4-232">**将邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-232">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="932c4-233">**将邮件移动到"垃圾邮件"文件夹**：邮件将传递到邮箱并移动到"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="932c4-233">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="932c4-234">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移动到"垃圾邮件"文件夹 (该邮件默认) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-234">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="932c4-235">有关详细信息，请参阅在 [Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)中配置 Exchange Online 邮箱上的垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="932c4-235">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="932c4-236">**隔离邮件**：将邮件发送到隔离邮箱，而不是目标收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-236">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="932c4-237">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="932c4-237">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="932c4-238">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="932c4-238">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="932c4-239">在 Microsoft 365 中以管理员角色管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="932c4-239">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="932c4-240">在 Microsoft 365 中以用户状态查找并释放隔离邮件</span><span class="sxs-lookup"><span data-stu-id="932c4-240">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="932c4-241">**传递邮件，将其他地址添加到"Bcc"** 行：将邮件传递至目标收件人，以静默方式将邮件发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-241">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="932c4-242">**在邮件传递之前删除** 邮件：以无提示方式删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="932c4-242">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="932c4-243">**安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：</span><span class="sxs-lookup"><span data-stu-id="932c4-243">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="932c4-244">**模拟用户**："来自"地址包含受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="932c4-244">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="932c4-245">**模拟域**："来自"地址包含受保护的域。</span><span class="sxs-lookup"><span data-stu-id="932c4-245">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="932c4-246">**异常字符**：发件人地址包含异常字符集 (例如，数学符号和文本，或大写和小写字母) 在受保护的发件人或域中。</span><span class="sxs-lookup"><span data-stu-id="932c4-246">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

  > [!IMPORTANT]
  >
  > <span data-ttu-id="932c4-247">即使关闭模拟安全提示，我们也建议您使用邮件流规则 (也称为传输规则) 来添加名为 **X-MS-Exchange-EnableFirstContactSafetyTip** 的邮件头，并启用对邮件的值。 </span><span class="sxs-lookup"><span data-stu-id="932c4-247">Even when the impersonation safety tips are turned off, **we recommended** that you use a mail flow rule (also known as a transport rule) to add a message header named **X-MS-Exchange-EnableFirstContactSafetyTip** with value **enable** to messages.</span></span> <span data-ttu-id="932c4-248">安全提示将在收件人第一次收到来自发件人的邮件时或他们经常不从发件人获取邮件时通知收件人。</span><span class="sxs-lookup"><span data-stu-id="932c4-248">A safety tip will notify recipients the first time they get a message from the sender or if they don't often get messages from the sender.</span></span>
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="用于使用多个收件人进行模拟保护的安全提示文本。":::

- <span data-ttu-id="932c4-250">**邮箱智能**：启用或禁用 (AI) ，该智能技术可确定具有常用联系人的用户电子邮件模式。</span><span class="sxs-lookup"><span data-stu-id="932c4-250">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="932c4-251">此设置可帮助 AI 区分合法电子邮件和欺骗性电子邮件与这些联系人。</span><span class="sxs-lookup"><span data-stu-id="932c4-251">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="932c4-252">邮箱智能仅适用于 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="932c4-252">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="932c4-253">**基于邮箱智能的模拟保护**：启用或禁用基于每个用户的单个发件人映射的增强模拟结果。</span><span class="sxs-lookup"><span data-stu-id="932c4-253">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="932c4-254">此智能允许 Microsoft 365 自定义用户模拟检测并更好地处理误报。</span><span class="sxs-lookup"><span data-stu-id="932c4-254">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="932c4-255">检测到用户模拟时，可以定义对邮件执行的特定操作：</span><span class="sxs-lookup"><span data-stu-id="932c4-255">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="932c4-256">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="932c4-256">**Don't apply any action**</span></span>
  - <span data-ttu-id="932c4-257">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="932c4-257">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="932c4-258">**将邮件移动到"垃圾邮件"文件夹**</span><span class="sxs-lookup"><span data-stu-id="932c4-258">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="932c4-259">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="932c4-259">**Quarantine the message**</span></span>
  - <span data-ttu-id="932c4-260">**传递邮件，将其他地址添加到"Bcc"行**</span><span class="sxs-lookup"><span data-stu-id="932c4-260">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="932c4-261">**在邮件传递之前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="932c4-261">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="932c4-262">**受信任的发件人和域**：模拟保护设置的例外。</span><span class="sxs-lookup"><span data-stu-id="932c4-262">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="932c4-263">来自指定发件人和发件人域的邮件从不被策略分类为基于模拟的攻击。</span><span class="sxs-lookup"><span data-stu-id="932c4-263">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="932c4-264">换句话说，对受保护的发件人、受保护的域或邮箱智能保护的操作不适用于这些受信任的发件人或发件人域。</span><span class="sxs-lookup"><span data-stu-id="932c4-264">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="932c4-265">这些列表的最大限制为大约 1000 个条目。</span><span class="sxs-lookup"><span data-stu-id="932c4-265">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="932c4-266">Microsoft Defender for Office 365 中的防钓鱼策略中的高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="932c4-266">Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="932c4-267">以下高级网络钓鱼阈值仅适用于 Microsoft Defender for Office 365 中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="932c4-267">The following advanced phishing thresholds are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="932c4-268">这些阈值控制将机器学习模型应用到邮件以确定网络钓鱼裁定的敏感度：</span><span class="sxs-lookup"><span data-stu-id="932c4-268">These thresholds control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="932c4-269">**1 - 标准**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="932c4-269">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="932c4-270">对邮件采取的操作的严重性取决于邮件是网络钓鱼邮件的可信度 (低、中、高或非常高) 。</span><span class="sxs-lookup"><span data-stu-id="932c4-270">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="932c4-271">例如，被标识为可信度非常高的网络钓鱼的邮件应用了最严重的操作，而被标识为低可信度的网络钓鱼的邮件应用了不太严重的操作。</span><span class="sxs-lookup"><span data-stu-id="932c4-271">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="932c4-272">**2 - 积极**：被标识为高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。</span><span class="sxs-lookup"><span data-stu-id="932c4-272">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="932c4-273">**3 -** 更积极：被标识为具有中等或高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。</span><span class="sxs-lookup"><span data-stu-id="932c4-273">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="932c4-274">**4 -** 最积极：被标识为低、中或高可信度的网络钓鱼的邮件被视为可信度非常高的邮件。</span><span class="sxs-lookup"><span data-stu-id="932c4-274">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="932c4-275">当增加此设置时， (标记为错误) 误报的可能性会增加。</span><span class="sxs-lookup"><span data-stu-id="932c4-275">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="932c4-276">有关建议设置的信息，请参阅 [Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)设置中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="932c4-276">For information about the recommended settings, see [anti-phishing policy in Microsoft Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>
