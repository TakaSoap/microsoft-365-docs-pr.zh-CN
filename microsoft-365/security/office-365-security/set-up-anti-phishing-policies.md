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
description: 管理员可以了解 Exchange Online Protection (EOP) 和 Office 365 高级威胁防护 (Office 365 ATP) 中提供的反网络钓鱼策略。
ms.openlocfilehash: 7118bca15102fd52e7825ee873187fa11d9fc0f9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308191"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="8345e-103">Microsoft 365 中的反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="8345e-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="8345e-104">使用 Exchange Online 邮箱、独立 Exchange Online Protection (EOP) 组织（无 Exchange Online 邮箱）和 Office 365 高级威胁防护 (Office 365 ATP) 组织的 Microsoft 365 组织中提供了用于配置反钓鱼保护设置的策略。</span><span class="sxs-lookup"><span data-stu-id="8345e-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="8345e-105">ATP 反网络钓鱼策略仅在具有 Office 365 ATP 的组织中可用。</span><span class="sxs-lookup"><span data-stu-id="8345e-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="8345e-106">例如：</span><span class="sxs-lookup"><span data-stu-id="8345e-106">For example:</span></span>

- <span data-ttu-id="8345e-107">Microsoft 365 企业版 E5、Microsoft 365 教育版 A5 等。</span><span class="sxs-lookup"><span data-stu-id="8345e-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="8345e-108">Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="8345e-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="8345e-109">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="8345e-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="8345e-110">作为附加项的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8345e-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="8345e-111">所有其他组织都具有反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="8345e-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="8345e-112">反网络钓鱼策略和 ATP 反网络钓鱼策略之间的高级别差异如下表所述：</span><span class="sxs-lookup"><span data-stu-id="8345e-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="8345e-113">功能</span><span class="sxs-lookup"><span data-stu-id="8345e-113">Feature</span></span>|<span data-ttu-id="8345e-114">防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="8345e-114">Anti-phishing policies</span></span>|<span data-ttu-id="8345e-115">ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="8345e-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="8345e-116">自动创建的默认策略</span><span class="sxs-lookup"><span data-stu-id="8345e-116">Automatically created default policy</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="8345e-119">创建自定义策略</span><span class="sxs-lookup"><span data-stu-id="8345e-119">Create custom policies</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="8345e-122">策略设置<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8345e-122">Policy settings<sup>\*</sup></span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="8345e-125">模拟设置</span><span class="sxs-lookup"><span data-stu-id="8345e-125">Impersonation settings</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="8345e-127">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="8345e-127">Spoof settings</span></span>|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="8345e-130">高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="8345e-130">Advanced phishing thresholds</span></span>||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="8345e-132"><sup>\*</sup> 在默认策略中，"策略名称" 和 "说明" 是只读的 (说明为空) ，您不能指定该策略应用于的用户 (默认策略将应用于) 的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="8345e-133">若要配置反网络钓鱼策略，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8345e-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="8345e-134">在 EOP 中配置反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="8345e-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="8345e-135">在 Microsoft 365 中配置 ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="8345e-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="8345e-136">本文的其余部分介绍了反网络钓鱼策略和 ATP 反网络钓鱼策略中提供的设置。</span><span class="sxs-lookup"><span data-stu-id="8345e-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="8345e-137">策略设置</span><span class="sxs-lookup"><span data-stu-id="8345e-137">Policy settings</span></span>

<span data-ttu-id="8345e-138">以下策略设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：</span><span class="sxs-lookup"><span data-stu-id="8345e-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="8345e-139">**名称**：无法重命名默认的反网络钓鱼策略，但可以命名和重命名所创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="8345e-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="8345e-140">**说明** 您不能将说明添加到默认的反网络钓鱼策略中，但可以添加和更改所创建的自定义策略的说明。</span><span class="sxs-lookup"><span data-stu-id="8345e-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="8345e-141">**应用**于：标识应用了反网络钓鱼策略的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="8345e-142">此值在自定义策略中是必需的，在默认策略中不可用 (默认策略适用于) 的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="8345e-143">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="8345e-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="8345e-144">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="8345e-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8345e-145">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="8345e-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="8345e-146">**收件人为**：组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="8345e-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="8345e-147">**收件人是**组织中的一个或多个组的成员：</span><span class="sxs-lookup"><span data-stu-id="8345e-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="8345e-148">**收件人域为**： Microsoft 365 中已配置的一个或多个接受的域。</span><span class="sxs-lookup"><span data-stu-id="8345e-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="8345e-149">例外情况**除外**：规则例外。</span><span class="sxs-lookup"><span data-stu-id="8345e-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="8345e-150">设置和行为与条件完全一样：</span><span class="sxs-lookup"><span data-stu-id="8345e-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="8345e-151">**收件人为**</span><span class="sxs-lookup"><span data-stu-id="8345e-151">**Recipient is**</span></span>
    - <span data-ttu-id="8345e-152">**收件人是的成员**</span><span class="sxs-lookup"><span data-stu-id="8345e-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="8345e-153">**收件人域为**</span><span class="sxs-lookup"><span data-stu-id="8345e-153">**The recipient domain is**</span></span>

  > [!NOTE]
  > <span data-ttu-id="8345e-154">"**应用于**" 设置在自定义反网络钓鱼策略中是必需的，以标识这些<u>策略应用于的</u>邮件**收件人**。</span><span class="sxs-lookup"><span data-stu-id="8345e-154">The **Applied to** setting is required in custom anti-phishing policies to identify them message **recipients** <u>that the policy applies to</u>.</span></span> <span data-ttu-id="8345e-155">ATP 反网络钓鱼策略还具有 [模拟设置](#impersonation-settings-in-atp-anti-phishing-policies) ，您可以在其中指定 <u>将接收模拟保护的</u> 单个发件人电子邮件地址或发件人域，如本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="8345e-155">ATP anti-phishing policies also have [impersonation settings](#impersonation-settings-in-atp-anti-phishing-policies) where you can specify individual sender email addresses or sender domains <u>that will receive impersonation protection</u> as described later in this topic.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="8345e-156">欺骗设置</span><span class="sxs-lookup"><span data-stu-id="8345e-156">Spoof settings</span></span>

<span data-ttu-id="8345e-157">哄骗是指电子邮件中的发件人地址 (在电子邮件客户端中显示的发件人地址) 与电子邮件源的域不匹配。</span><span class="sxs-lookup"><span data-stu-id="8345e-157">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="8345e-158">有关哄骗的详细信息，请参阅 [Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8345e-158">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="8345e-159">以下欺骗设置在反网络钓鱼策略和 ATP 反网络钓鱼策略中可用：</span><span class="sxs-lookup"><span data-stu-id="8345e-159">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="8345e-160">**反欺骗保护**：启用或禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="8345e-160">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="8345e-161">建议您将其保留为启用状态。</span><span class="sxs-lookup"><span data-stu-id="8345e-161">We recommend that you leave it enabled.</span></span> <span data-ttu-id="8345e-162">您可以使用 **欺骗智能策略** 来允许或阻止特定的欺骗内部和外部发件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-162">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="8345e-163">有关详细信息，请参阅[在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="8345e-163">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="8345e-164">默认情况下，在 EOP 的默认反网络钓鱼策略中启用了欺骗设置、默认的 ATP 反网络钓鱼策略，以及您创建的新的自定义反网络钓鱼策略或 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="8345e-164">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="8345e-165">如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。</span><span class="sxs-lookup"><span data-stu-id="8345e-165">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="8345e-166">有关说明，请参阅 [增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="8345e-166">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="8345e-167">对于阻止欺骗发件人发送的邮件，您还可以指定对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="8345e-167">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="8345e-168">**将邮件移动到 "垃圾邮件" 文件夹**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="8345e-168">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="8345e-169">邮件传递到邮箱并移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8345e-169">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="8345e-170">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移至 "垃圾邮件" 文件夹 (默认情况下，将启用该规则) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-170">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8345e-171">有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="8345e-171">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="8345e-172">**隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-172">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="8345e-173">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8345e-173">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="8345e-174">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="8345e-174">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="8345e-175">在 Microsoft 365 中以管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="8345e-175">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="8345e-176">在 Microsoft 365 中查找并以用户的形式发布隔离邮件</span><span class="sxs-lookup"><span data-stu-id="8345e-176">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="8345e-177">**未经身份验证的发件人**：请参阅下一节中的说明。</span><span class="sxs-lookup"><span data-stu-id="8345e-177">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="8345e-178">未经身份验证发件人</span><span class="sxs-lookup"><span data-stu-id="8345e-178">Unauthenticated Sender</span></span>

<span data-ttu-id="8345e-179">未经身份验证的发件人标识是反网络钓鱼策略和 ATP 反网络钓鱼策略中提供的 [欺骗设置](#spoof-settings) 的一部分，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="8345e-179">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="8345e-180">**未经身份验证的发件人**设置启用或禁用 Outlook 中未识别的发件人标识。</span><span class="sxs-lookup"><span data-stu-id="8345e-180">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="8345e-181">具体来说：</span><span class="sxs-lookup"><span data-stu-id="8345e-181">Specifically:</span></span>

- <span data-ttu-id="8345e-182">如果邮件未通过 SPF 或 DKIM 检查且邮件未通过 DMARC 或[复合身份验证](email-validation-and-authentication.md#composite-authentication) **，** 则会将 ) 添加到发件人的照片中的 ( 问号。</span><span class="sxs-lookup"><span data-stu-id="8345e-182">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="8345e-183">如果 "发件人" 地址中的域 (电子邮件客户) 端中显示的邮件发件人不同于 DKIM 签名中的域或**邮件的 "发**件人" 地址中的域，则会添加 via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-183">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="8345e-184">有关这些地址的详细信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="8345e-184">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="8345e-185">若要防止将这些标识符添加到特定发件人的邮件中，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="8345e-185">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="8345e-186">允许发件人在欺骗智能策略中进行欺骗。</span><span class="sxs-lookup"><span data-stu-id="8345e-186">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="8345e-187">有关说明，请参阅 [在 Microsoft 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="8345e-187">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="8345e-188">为发件人域[配置电子邮件身份验证](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)。</span><span class="sxs-lookup"><span data-stu-id="8345e-188">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="8345e-189">对于发件人照片中的问号，SPF 或 DKIM 是最重要的。</span><span class="sxs-lookup"><span data-stu-id="8345e-189">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="8345e-190">对于 via 标记，确认 DKIM 签名中的域，或 "发 **件人地址匹配** (" 或 "发件人地址中) 域的子域"。</span><span class="sxs-lookup"><span data-stu-id="8345e-190">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="8345e-191">有关详细信息，请参阅 [识别可疑邮件在 Outlook.com 和 web 上的 Outlook](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="8345e-191">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="8345e-192">ATP 反网络钓鱼策略中的独占设置</span><span class="sxs-lookup"><span data-stu-id="8345e-192">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="8345e-193">本节介绍仅在 ATP 反网络钓鱼策略中可用的策略设置。</span><span class="sxs-lookup"><span data-stu-id="8345e-193">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="8345e-194">默认情况下，未配置或打开 ATP 专用设置，即使在默认策略中也是如此。</span><span class="sxs-lookup"><span data-stu-id="8345e-194">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="8345e-195">若要利用这些功能，您需要在默认的 ATP 反网络钓鱼策略中启用和配置这些功能，或者创建和配置自定义 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="8345e-195">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="8345e-196">ATP 反网络钓鱼策略中的模拟设置</span><span class="sxs-lookup"><span data-stu-id="8345e-196">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="8345e-197">模拟是邮件中发件人或发件人的电子邮件域类似于真实的发件人或域：</span><span class="sxs-lookup"><span data-stu-id="8345e-197">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="8345e-198">域 contoso.com 的模拟示例是ćóntoso.com。</span><span class="sxs-lookup"><span data-stu-id="8345e-198">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="8345e-199">用户 michelle@contoso.com 的模拟示例是 michele@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8345e-199">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="8345e-200">否则，模拟域可能被视为合法 (注册域、配置的电子邮件身份验证记录等 ) ，但其目的是欺骗收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-200">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="8345e-201">以下模拟设置仅适用于 ATP 反网络钓鱼策略：</span><span class="sxs-lookup"><span data-stu-id="8345e-201">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="8345e-202">**要保护的用户**：阻止将指定的内部或外部电子邮件地址模拟 **为邮件发件人**。</span><span class="sxs-lookup"><span data-stu-id="8345e-202">**Users to protect**: Prevents the specified internal or external email addresses from being impersonated **as message senders**.</span></span> <span data-ttu-id="8345e-203">例如，主管 (内部发件人) 和董事会成员 (外部发件人) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-203">For example, executives (internal senders) and board members (external senders).</span></span> <span data-ttu-id="8345e-204">您可以添加最高为60的内部和外部发件人电子邮件地址，以防止模拟。</span><span class="sxs-lookup"><span data-stu-id="8345e-204">You can add up to 60 internal and external sender email addresses to protect from impersonation.</span></span> <span data-ttu-id="8345e-205">受模拟保护的 **发件人** 列表与该策略所应用于的 **收件人** 列表不同。</span><span class="sxs-lookup"><span data-stu-id="8345e-205">This list of **senders** that are protected from impersonation is different from the list of **recipients** that the policy applies to.</span></span>

  <span data-ttu-id="8345e-206">默认策略适用于发送给所有收件人的邮件，而自定义策略仅适用于发送到您在 "[策略设置](#policy-settings)" 部分中所述的 "**应用于**" 设置中定义的收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="8345e-206">The default policy applies to messages sent to all recipients, while custom policies apply only to messages sent to the recipients you define in the **Applied to** setting as described in the [Policy settings](#policy-settings) section.</span></span>

  <span data-ttu-id="8345e-207">默认情况下，不会为 **要保护的用户**中的模拟保护配置发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8345e-207">By default, no sender email addresses are configured for impersonation protection in **Users to protect**.</span></span> <span data-ttu-id="8345e-208">因此，在默认策略或自定义策略中，默认情况下，模拟保护不会覆盖任何发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8345e-208">Therefore, by default, no sender email addresses are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="8345e-209">将内部或外部电子邮件地址添加到 " **要保护的用户** " 列表中时，来自这些 **发件人** 的邮件将受到模拟保护检查。</span><span class="sxs-lookup"><span data-stu-id="8345e-209">When you add internal or external email addresses to the **Users to protect** list, messages from those **senders** are subject to impersonation protection checks.</span></span> <span data-ttu-id="8345e-210">**如果**将邮件发送给**收件人**，该邮件将被检查以模拟邮件，以确保该邮件应用于默认策略的所有收件人 (。**应用**于自定义策略) 中的收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-210">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="8345e-211">如果在发件人的电子邮件地址中检测到模拟，用户的模拟保护操作将应用于邮件， (邮件上的操作、模拟的用户安全提示等 ) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-211">If impersonation is detected in the sender's email address, the impersonation protections actions for users are applied to the message (the action on the message, the impersonated users safety tip, etc.).</span></span>

- <span data-ttu-id="8345e-212">**要保护的域**：阻止 **在邮件发件人的域中**模拟指定的域。</span><span class="sxs-lookup"><span data-stu-id="8345e-212">**Domains to protect**: Prevents the specified domains from being impersonated **in the message sender's domain**.</span></span> <span data-ttu-id="8345e-213">例如，您拥有的所有域都 ([接受的域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 或拥有您拥有的域或合作伙伴域) 的特定域 (域。</span><span class="sxs-lookup"><span data-stu-id="8345e-213">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="8345e-214">受模拟保护的 **发件人域** 的列表与该策略所应用于的 **收件人** 列表不同。</span><span class="sxs-lookup"><span data-stu-id="8345e-214">This list of **sender domains** that are protected from impersonation is different from the list of **recipients** that the policy applies to.</span></span>

  <span data-ttu-id="8345e-215">默认策略适用于发送给所有收件人的邮件，而自定义策略仅适用于发送到您在 "[策略设置](#policy-settings)" 部分中所述的 "**应用于**" 设置中定义的收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="8345e-215">The default policy applies to messages sent to all recipients, while custom policies apply only to messages sent to the recipients you define in the **Applied to** setting as described in the [Policy settings](#policy-settings) section.</span></span>

  <span data-ttu-id="8345e-216">默认情况下，不会为 **要保护的域**中的模拟保护配置任何发件人域。</span><span class="sxs-lookup"><span data-stu-id="8345e-216">By default, no sender domains are configured for impersonation protection in **Domains to protect**.</span></span> <span data-ttu-id="8345e-217">因此，在默认策略或自定义策略中，默认情况下，模拟保护不会覆盖任何发件人域。</span><span class="sxs-lookup"><span data-stu-id="8345e-217">Therefore, by default, no sender domains are covered by impersonation protection, either in the default policy or in custom policies.</span></span>

  <span data-ttu-id="8345e-218">将域添加到 " **要保护的域** " 列表中时，来自 **这些域中发件人** 的邮件将受到模拟保护检查。</span><span class="sxs-lookup"><span data-stu-id="8345e-218">When you add domains to the **Domains to protect** list, messages from **senders in those domains** are subject to impersonation protection checks.</span></span> <span data-ttu-id="8345e-219">**如果**将邮件发送给**收件人**，该邮件将被检查以模拟邮件，以确保该邮件应用于默认策略的所有收件人 (。**应用**于自定义策略) 中的收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-219">The message is checked for impersonation **if** the message is sent to a **recipient** that the policy applies to (all recipients for the default policy; **Applied to** recipients in custom policies).</span></span> <span data-ttu-id="8345e-220">如果在发件人的域中检测到模拟，则域的模拟保护操作将应用于邮件 (邮件上的操作、模拟的域安全提示等 ) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-220">If impersonation is detected in the sender's domain, the impersonation protection actions for domains are applied to the message (the action on the message, the impersonated domains safety tip, etc.).</span></span>

- <span data-ttu-id="8345e-221">**针对受保护的用户或域的操作**：选择对入站邮件执行的操作，这些邮件包含对策略中的受保护用户和受保护域的模拟尝试。</span><span class="sxs-lookup"><span data-stu-id="8345e-221">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="8345e-222">您可以为受保护的用户和模拟的受保护域的模拟指定不同的操作：</span><span class="sxs-lookup"><span data-stu-id="8345e-222">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="8345e-223">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="8345e-223">**Don't apply any action**</span></span>

  - <span data-ttu-id="8345e-224">将**邮件重定向到其他电子邮件地址**：将邮件发送给指定的收件人，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-224">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="8345e-225">**将邮件移动到 "垃圾邮件" 文件夹**：邮件将传递到邮箱并移动到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="8345e-225">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="8345e-226">在 Exchange Online 中，如果在邮箱上启用了垃圾邮件规则，则邮件将移至 "垃圾邮件" 文件夹 (默认情况下，将启用该规则) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-226">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="8345e-227">有关详细信息，请参阅 [Microsoft 365 中的 Exchange Online 邮箱上的配置垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="8345e-227">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="8345e-228">**隔离邮件**：将邮件发送到隔离，而不是发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-228">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="8345e-229">有关隔离的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8345e-229">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="8345e-230">Microsoft 365 中的隔离</span><span class="sxs-lookup"><span data-stu-id="8345e-230">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="8345e-231">在 Microsoft 365 中以管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="8345e-231">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="8345e-232">在 Microsoft 365 中查找并以用户的形式发布隔离邮件</span><span class="sxs-lookup"><span data-stu-id="8345e-232">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="8345e-233">**传递邮件并向 "密件抄送" 行添加其他地址**：将邮件传递给预期收件人，并以无提示方式将邮件传递给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="8345e-233">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="8345e-234">**邮件传递前将其删除**：悄悄删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="8345e-234">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="8345e-235">**安全提示**：启用或禁用以下模拟安全提示，这些提示将显示未通过模拟检查的邮件：</span><span class="sxs-lookup"><span data-stu-id="8345e-235">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="8345e-236">**模拟用户**： "发件人" 地址包含受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="8345e-236">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="8345e-237">**模拟域**： "发件人" 地址包含受保护的域。</span><span class="sxs-lookup"><span data-stu-id="8345e-237">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="8345e-238">**异常字符**： From 地址包含不寻常的字符集 (例如，数学符号和文本，或者在受保护的发件人或域中的大写和小写字母的组合) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-238">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="8345e-239">**邮箱智能**：启用或禁用用于确定用户的电子邮件模式与其常用联系人的智能 (AI) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-239">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="8345e-240">此设置可帮助 AI 区分合法和欺骗的电子邮件与这些联系人。</span><span class="sxs-lookup"><span data-stu-id="8345e-240">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="8345e-241">邮箱智能仅适用于 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="8345e-241">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="8345e-242">**基于邮箱智能的模拟保护**：基于每个用户的个人发件人地图启用或禁用增强的模拟结果。</span><span class="sxs-lookup"><span data-stu-id="8345e-242">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="8345e-243">此智能允许 Microsoft 365 自定义用户模拟检测，并更好地处理误报。</span><span class="sxs-lookup"><span data-stu-id="8345e-243">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="8345e-244">当检测到用户模拟时，您可以定义对邮件执行的特定操作：</span><span class="sxs-lookup"><span data-stu-id="8345e-244">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="8345e-245">**不应用任何操作**</span><span class="sxs-lookup"><span data-stu-id="8345e-245">**Don't apply any action**</span></span>
  - <span data-ttu-id="8345e-246">**将邮件重定向到其他电子邮件地址**</span><span class="sxs-lookup"><span data-stu-id="8345e-246">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="8345e-247">**将邮件移动到 "垃圾邮件" 文件夹**</span><span class="sxs-lookup"><span data-stu-id="8345e-247">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="8345e-248">**隔离邮件**</span><span class="sxs-lookup"><span data-stu-id="8345e-248">**Quarantine the message**</span></span>
  - <span data-ttu-id="8345e-249">**传递邮件并向 "密件抄送" 行添加其他地址**</span><span class="sxs-lookup"><span data-stu-id="8345e-249">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="8345e-250">**邮件传递前删除邮件**</span><span class="sxs-lookup"><span data-stu-id="8345e-250">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="8345e-251">**受信任的发件人和域**：模拟保护设置的例外。</span><span class="sxs-lookup"><span data-stu-id="8345e-251">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="8345e-252">来自指定发件人和发件人域的邮件永远不会归为策略的基于模拟的攻击。</span><span class="sxs-lookup"><span data-stu-id="8345e-252">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="8345e-253">换句话说，受保护的发件人、受保护域或邮箱智能保护的操作不会应用于这些受信任的发件人或发件人域。</span><span class="sxs-lookup"><span data-stu-id="8345e-253">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="8345e-254">这些列表的最大限制约为1000个条目。</span><span class="sxs-lookup"><span data-stu-id="8345e-254">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="8345e-255">ATP 反网络钓鱼策略中的高级网络钓鱼阈值</span><span class="sxs-lookup"><span data-stu-id="8345e-255">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="8345e-256">以下高级网络钓鱼阈值仅在 ATP 反网络钓鱼策略中可用，以控制将机器学习模型应用于邮件以确定仿冒判定的邮件的灵敏度：</span><span class="sxs-lookup"><span data-stu-id="8345e-256">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="8345e-257">**1-Standard**：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="8345e-257">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="8345e-258">对邮件执行的操作的严重性取决于邮件是网络钓鱼 (低、中、高或非常高的可信度) 的可信度程度。</span><span class="sxs-lookup"><span data-stu-id="8345e-258">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="8345e-259">例如，以非常高的可信度标识为网络钓鱼的邮件会应用最严重的操作，而标识为具有较低可信度的网络钓鱼的邮件则应用了较少的严重操作。</span><span class="sxs-lookup"><span data-stu-id="8345e-259">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="8345e-260">**2-严格**：被标识为高度可信度的网络钓鱼的邮件被视为以非常高的可信度进行识别。</span><span class="sxs-lookup"><span data-stu-id="8345e-260">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="8345e-261">**3-更主动**：被标识为中等或高可信度的网络钓鱼的邮件将被视为以非常高的可信度进行识别。</span><span class="sxs-lookup"><span data-stu-id="8345e-261">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="8345e-262">**4-最严格**：被标识为低、中或高可信度的网络钓鱼的邮件被视为以非常高的置信度进行标识。</span><span class="sxs-lookup"><span data-stu-id="8345e-262">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="8345e-263">误报 (正常的可能性可能会随着此设置的增加而被标记为坏) 。</span><span class="sxs-lookup"><span data-stu-id="8345e-263">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="8345e-264">有关推荐设置的信息，请参阅 [OFFICE ATP 反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="8345e-264">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
