---
title: 配置欺骗智能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection 电子邮件中的欺骗 (EOP) ，您可在其中允许或阻止特定的欺骗性发件人。
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826573"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="8cffa-103">在 EOP 中配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="8cffa-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="8cffa-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，从 2018 年 10 月起，EOP 将自动防止 EOP 欺骗。</span><span class="sxs-lookup"><span data-stu-id="8cffa-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="8cffa-105">EOP 使用欺骗智能作为组织整体防御网络钓鱼的一部分。</span><span class="sxs-lookup"><span data-stu-id="8cffa-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="8cffa-106">有关详细信息，请参阅 [EOP 中的防欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="8cffa-107">如果发件人欺骗了电子邮件地址，则显示为某个组织的域中的用户，或者是外部域中向您组织发送电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="8cffa-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="8cffa-108">需要阻止欺骗发件人发送垃圾邮件或网络钓鱼电子邮件的攻击者。</span><span class="sxs-lookup"><span data-stu-id="8cffa-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="8cffa-109">但是，在某些场景中，合法发件人是欺骗性发件人。</span><span class="sxs-lookup"><span data-stu-id="8cffa-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="8cffa-110">例如：</span><span class="sxs-lookup"><span data-stu-id="8cffa-110">For example:</span></span>

- <span data-ttu-id="8cffa-111">欺骗内部域的合法情形：</span><span class="sxs-lookup"><span data-stu-id="8cffa-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="8cffa-112">第三方发件人使用您的域向你自己的员工发送批量邮件，进行公司轮询。</span><span class="sxs-lookup"><span data-stu-id="8cffa-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="8cffa-113">外部公司代表你生成和发送广告或产品更新。</span><span class="sxs-lookup"><span data-stu-id="8cffa-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="8cffa-114">助理定期需要向组织内的其他人发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="8cffa-115">内部应用程序发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="8cffa-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="8cffa-116">欺骗外部域的合法方案：</span><span class="sxs-lookup"><span data-stu-id="8cffa-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="8cffa-117">发件人位于邮件列表 (也称为讨论列表) ，同时将来自原始发件人的电子邮件中继到邮件列表上的所有参与者。</span><span class="sxs-lookup"><span data-stu-id="8cffa-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="8cffa-118">外部公司代表其他公司代表其他公司 (例如，自动报告或软件即服务服务公司发送) 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="8cffa-119">欺骗智能，特别是 (（特别是) ）智能策略，有助于确保由合法发件人发送的欺骗性电子邮件不会被 EOP 垃圾邮件筛选器或外部电子邮件系统中泄连，同时保护用户以防你的用户受到垃圾邮件或网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="8cffa-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="8cffa-120">你可以在安全& 合规中心，或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (PowerShell 中管理欺骗智能;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8cffa-121">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8cffa-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8cffa-122">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="8cffa-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8cffa-123">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="8cffa-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="8cffa-124">若要直接转到 **"反网络钓鱼"页面，** 请使用 <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="8cffa-125">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8cffa-126">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8cffa-127">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="8cffa-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8cffa-128">若要修改欺骗智能策略或者启用或禁用欺骗智能保护，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="8cffa-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8cffa-129">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="8cffa-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8cffa-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="8cffa-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8cffa-131">若要对欺骗智能策略进行只读访问，需要是以下角色之一的成员：</span><span class="sxs-lookup"><span data-stu-id="8cffa-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8cffa-132">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="8cffa-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8cffa-133">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="8cffa-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="8cffa-134">有关我们推荐的欺骗智能设置， [请参阅 EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="8cffa-135">使用安全&合规中心管理欺骗性发件人</span><span class="sxs-lookup"><span data-stu-id="8cffa-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="8cffa-136">如果拥有 Microsoft 365 企业版 E5 订阅或已单独购买 Office 365 高级威胁防护 (Office 365 ATP) 加载项，则还可以通过欺骗智能见解来管理正在欺骗你的域的 [发件人](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="8cffa-137">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="8cffa-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8cffa-138">在" **反垃圾邮件设置"页面上** ，单击" ![ 展开"图标 ](../../media/scc-expand-icon.png) 以 **展开"欺骗"智能策略**。</span><span class="sxs-lookup"><span data-stu-id="8cffa-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![选择欺骗智能策略](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="8cffa-140">做出以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="8cffa-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="8cffa-141">**查看新发件人**</span><span class="sxs-lookup"><span data-stu-id="8cffa-141">**Review new senders**</span></span>
   - <span data-ttu-id="8cffa-142">**显示我已审阅的发件人**</span><span class="sxs-lookup"><span data-stu-id="8cffa-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="8cffa-143">在 **"确定是否允许这些发件人"出现的** 浮出控件中，选择下列选项卡之一：</span><span class="sxs-lookup"><span data-stu-id="8cffa-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="8cffa-144">**您的域**：内部域中的发件人欺骗用户。</span><span class="sxs-lookup"><span data-stu-id="8cffa-144">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="8cffa-145">**外部域**：发件人欺骗外部域中的用户。</span><span class="sxs-lookup"><span data-stu-id="8cffa-145">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="8cffa-146">单击 ![ "允许 ](../../media/scc-expand-icon.png) 欺骗 **"列中的"展开"** 图标。</span><span class="sxs-lookup"><span data-stu-id="8cffa-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="8cffa-147">选择 **"是** "允许欺骗性发件人，或者选择" **否** "将邮件标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="8cffa-148">此操作由默认的反网络钓鱼策略或自定义 ATP 反网络钓鱼策略 (默认值为将 **邮件移至垃圾邮件文件夹格式的**) 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-148">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="8cffa-149">有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![显示欺骗性发件人浮出控件以及是否允许发件人欺骗的屏幕截图](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="8cffa-151">您看到的列和值如以下列表进行了说明：</span><span class="sxs-lookup"><span data-stu-id="8cffa-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="8cffa-152">**欺骗用户**：被欺骗的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8cffa-152">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="8cffa-153">这是在"发件人"地址中的邮件 (也称为 `5322.From` 电子邮件客户端) 中显示的地址。</span><span class="sxs-lookup"><span data-stu-id="8cffa-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="8cffa-154">SPF 不会检查此地址的有效性。</span><span class="sxs-lookup"><span data-stu-id="8cffa-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="8cffa-155">在 **"域** "选项卡上，该值包含一个电子邮件地址，或者如果源电子邮件服务器正在欺骗多个用户帐户，则此地址 **包含多个用户帐户**。</span><span class="sxs-lookup"><span data-stu-id="8cffa-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="8cffa-156">在" **外部域** "选项卡上，该值包含欺骗用户的域，而不是完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8cffa-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="8cffa-157">**发送基础结构**：在源电子邮件服务器的 IP 地址的反向 DNS 查找 (PTR 记录) 中找到的域，或者源没有 PTR 记录时则为 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8cffa-157">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="8cffa-158">有关邮件来源和邮件发件人的更多信息， [请参阅电子邮件标准的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="8cffa-159">**邮件数量**：来自发送基础结构的邮件数量，包含过去 30 天内包含指定的欺骗性发件人或发件人数量。</span><span class="sxs-lookup"><span data-stu-id="8cffa-159">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="8cffa-160">**用户复合的数量：** 用户在过去 30 天内针对此发件人进行处理。</span><span class="sxs-lookup"><span data-stu-id="8cffa-160">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="8cffa-161">商标通常以垃圾邮件的形式向 Microsoft 提交。</span><span class="sxs-lookup"><span data-stu-id="8cffa-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="8cffa-162">**身份验证结果**：以下值之一：</span><span class="sxs-lookup"><span data-stu-id="8cffa-162">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="8cffa-163">**已**传递：发件人通过了检查服务， (SPF 或 DKIM) 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-163">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="8cffa-164">**失败**：发件人未通过 EOP 发件人身份验证检查。</span><span class="sxs-lookup"><span data-stu-id="8cffa-164">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="8cffa-165">**未**知：这些检查的结果未知。</span><span class="sxs-lookup"><span data-stu-id="8cffa-165">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="8cffa-166">**由以下方式**设置的决策：显示是否允许发送基础结构欺骗用户进行：</span><span class="sxs-lookup"><span data-stu-id="8cffa-166">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="8cffa-167">**自动设置的** (性) </span><span class="sxs-lookup"><span data-stu-id="8cffa-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="8cffa-168">**管理员** (手动) </span><span class="sxs-lookup"><span data-stu-id="8cffa-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="8cffa-169">**上次见**过：从包含欺骗性的用户的发送基础结构收到邮件时的上次日期。</span><span class="sxs-lookup"><span data-stu-id="8cffa-169">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="8cffa-170">**允许欺骗？**：你在此处看到的值如下：</span><span class="sxs-lookup"><span data-stu-id="8cffa-170">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="8cffa-171">**是**：允许来自欺骗用户和发送基础结构组合的邮件，但不会被视为欺骗性电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-171">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="8cffa-172">**否**：欺骗用户和发送基础结构组合的消息标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-172">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="8cffa-173">此操作由默认的反网络钓鱼策略或自定义 ATP 反网络钓鱼策略 (默认值为将 **邮件移至垃圾邮件文件夹格式的**) 。</span><span class="sxs-lookup"><span data-stu-id="8cffa-173">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="8cffa-174">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="8cffa-174">See the next section for more information.</span></span>

     - <span data-ttu-id="8cffa-175">**Some users** (**Your Domains** tab only) ： A sending infrastructure is spoofing multiple users， where some spoofed users are allowed and others are not.</span><span class="sxs-lookup"><span data-stu-id="8cffa-175">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="8cffa-176">使用 **"详细** "选项卡查看特定地址。</span><span class="sxs-lookup"><span data-stu-id="8cffa-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="8cffa-177">在页面底部，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8cffa-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="8cffa-178">使用 PowerShell 管理欺骗性发件人</span><span class="sxs-lookup"><span data-stu-id="8cffa-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="8cffa-179">若要在欺骗智能中查看允许和阻止的发件人，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8cffa-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="8cffa-180">本示例返回有关允许您的域中的欺骗用户的所有发件人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cffa-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="8cffa-181">有关语法和参数的详细信息，请参阅[Get-PhishFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="8cffa-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="8cffa-182">若要在欺骗智能中配置允许和阻止的发件人，请按照以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="8cffa-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="8cffa-183">通过将 **Get-PhishFilterPolicy** cmdlet 的输出写入 CSV 文件，捕获检测到的欺骗发件人的当前列表：</span><span class="sxs-lookup"><span data-stu-id="8cffa-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="8cffa-184">编辑 CSV 文件以添加或修改 **SpoofedUser** 以 (**或 AllowedToSpoof**)  (是"或"否") 值。</span><span class="sxs-lookup"><span data-stu-id="8cffa-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="8cffa-185">保存文件，阅读文件并将内容存储为名为： `$UpdateSpoofedSenders`</span><span class="sxs-lookup"><span data-stu-id="8cffa-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="8cffa-186">使用 `$UpdateSpoofedSenders` 变量配置欺骗智能策略：</span><span class="sxs-lookup"><span data-stu-id="8cffa-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="8cffa-187">有关语法和参数的详细信息，请参阅[Set-PhishFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="8cffa-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="8cffa-188">使用安全与&中心配置欺骗智能</span><span class="sxs-lookup"><span data-stu-id="8cffa-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="8cffa-189">在防钓鱼策略的欺骗设置中描述 [了欺骗智能配置选项](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="8cffa-190">可以在默认防钓鱼策略和自定义策略中配置欺骗智能设置。</span><span class="sxs-lookup"><span data-stu-id="8cffa-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="8cffa-191">有关基于您的订阅的说明，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="8cffa-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="8cffa-192">[在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="8cffa-193">[在 Microsoft 365 中配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-193">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8cffa-194">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="8cffa-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="8cffa-195">若要验证你是否已通过允许或不允许欺骗的发件人以及是否配置伪信智能设置配置了欺骗智能保护，请按照以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8cffa-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="8cffa-196">在安全 & 合规中心内，转至**威胁管理**策略反垃圾邮件，反垃圾邮件可展开"欺骗智能 \> **Policy** \> **Anti-spam** \> **"** \> 策略选择 **"向我我**已经审阅的发件人 \> " 选择**了'域'或\*\*\*\*外部域"** 选项卡，然后验证**是否允许欺骗？** 此值适用于发件人。</span><span class="sxs-lookup"><span data-stu-id="8cffa-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="8cffa-197">在 PowerShell 中，运行以下命令来查看允许和不允许欺骗的发件人：</span><span class="sxs-lookup"><span data-stu-id="8cffa-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="8cffa-198">在 PowerShell 中，运行以下命令，将所有欺骗性发件人列表导出为 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="8cffa-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="8cffa-199">在安全与&合规中心内，**转到威** \> **胁**管理策略 \> **Anti-phishing**防钓鱼或 ATP 防**钓鱼**，并执行以下步骤之一：  </span><span class="sxs-lookup"><span data-stu-id="8cffa-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="8cffa-200">从列表中选择一个策略。</span><span class="sxs-lookup"><span data-stu-id="8cffa-200">Select a policy from the list.</span></span> <span data-ttu-id="8cffa-201">在显示的浮出控件中，验证"欺骗 **"部分中的** 值。</span><span class="sxs-lookup"><span data-stu-id="8cffa-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="8cffa-202">单击 **"默认策略"。**</span><span class="sxs-lookup"><span data-stu-id="8cffa-202">Click **Default policy**.</span></span> <span data-ttu-id="8cffa-203">在显示的浮出控件中，验证"欺骗 **"部分中的** 值。</span><span class="sxs-lookup"><span data-stu-id="8cffa-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="8cffa-204">在 Exchange Online PowerShell 中， \<Name\> 将 Office 365 AntiPhish Default 或自定义策略名称替换为自定义策略，然后运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="8cffa-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="8cffa-205">管理欺骗和网络钓鱼的其他方法</span><span class="sxs-lookup"><span data-stu-id="8cffa-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="8cffa-206">关于欺骗和网络钓鱼防护的一定费用。</span><span class="sxs-lookup"><span data-stu-id="8cffa-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="8cffa-207">下面提供了检查发件人欺骗域的相关方法，以及防止它们充分分你的组织：</span><span class="sxs-lookup"><span data-stu-id="8cffa-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="8cffa-208">检查 **欺骗邮件报告**。</span><span class="sxs-lookup"><span data-stu-id="8cffa-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="8cffa-209">你可以经常使用此报告来查看和帮助管理欺骗性发件人。</span><span class="sxs-lookup"><span data-stu-id="8cffa-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="8cffa-210">有关信息，请参阅 [欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="8cffa-211">查看 SPF 配置的 (策略) 框架。</span><span class="sxs-lookup"><span data-stu-id="8cffa-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="8cffa-212">若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="8cffa-213">有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="8cffa-214">查看域密钥标识邮件， (DKIM 名称) 邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="8cffa-215">除了使用 SPF 和 DMARC 之外，还应使用 DKIM，这样有助于防止攻击者发送看起来像自你的域中的邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="8cffa-216">你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。</span><span class="sxs-lookup"><span data-stu-id="8cffa-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="8cffa-217">有关信息，请参阅" [使用 DKIM"在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="8cffa-218">查看基于域的邮件身份验证、报告和一致性， (DMARC 测试) 配置。</span><span class="sxs-lookup"><span data-stu-id="8cffa-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="8cffa-219">实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="8cffa-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="8cffa-220">DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。</span><span class="sxs-lookup"><span data-stu-id="8cffa-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="8cffa-221">有关信息，请参阅 [使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="8cffa-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
