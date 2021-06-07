---
title: 使用欺骗智能策略和欺骗智能见解管理欺骗发件人
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
description: 管理员可以了解如何使用欺骗智能策略和欺骗智能见解来允许或阻止检测到的欺骗发件人。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793204"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="e9788-103">使用 EOP 中的欺骗智能策略和欺骗智能见解管理欺骗发件人</span><span class="sxs-lookup"><span data-stu-id="e9788-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e9788-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="e9788-104">**Applies to**</span></span>
- [<span data-ttu-id="e9788-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="e9788-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e9788-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9788-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e9788-107">本文介绍了要替换的旧版欺骗性发件人管理体验。</span><span class="sxs-lookup"><span data-stu-id="e9788-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="e9788-108">有关新体验详细信息，请参阅 [EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="e9788-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="e9788-109">在具有 Exchange Online 或独立 Exchange Online Protection (EOP) 组织邮箱且没有 Exchange Online 邮箱的 Microsoft 365 组织中，自 2018 年 10 日起，入站电子邮件将自动受到 EOP 的欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="e9788-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="e9788-110">EOP **使用欺骗智能** 作为组织防御网络钓鱼的整体防御的一部分。</span><span class="sxs-lookup"><span data-stu-id="e9788-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="e9788-111">有关详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e9788-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e9788-112">默认 (仅) 欺骗智能策略有助于确保合法发件人发送的欺骗性电子邮件不会在 EOP 垃圾邮件筛选器中被发现，同时保护用户免受垃圾邮件或网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="e9788-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="e9788-113">您还可以使用欺骗智能见解快速确定哪些外部发件人从未通过 SPF、DKIM 或 DMARC 检查的域合法地向您发送未经身份验证 (电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="e9788-114">可以在安全与合规中心内或在 PowerShell & PowerShell 中管理欺骗智能， (Exchange Online PowerShell 中Microsoft 365邮箱位于 Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e9788-115">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e9788-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e9788-116">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="e9788-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="e9788-117">若要直接转到欺骗 **智能策略的"反** 垃圾邮件设置"页，请使用 <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="e9788-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="e9788-118">若要直接转到安全 **仪表板页面** 获取欺骗智能见解，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e9788-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="e9788-119">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e9788-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e9788-120">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e9788-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e9788-121">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="e9788-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e9788-122">若要修改欺骗智能策略或启用或禁用欺骗智能，你需要是组织管理或安全 **管理员\*\*\*\*角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="e9788-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e9788-123">若要对欺骗智能策略进行只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="e9788-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e9788-124">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="e9788-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e9788-125">**注意**：</span><span class="sxs-lookup"><span data-stu-id="e9788-125">**Notes**:</span></span>

  - <span data-ttu-id="e9788-126">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="e9788-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e9788-127">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e9788-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e9788-128">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="e9788-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e9788-129">反网络钓鱼策略中的欺骗设置中 [介绍了欺骗智能选项](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e9788-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="e9788-130">可以在反网络钓鱼策略中启用、禁用和配置欺骗智能设置。</span><span class="sxs-lookup"><span data-stu-id="e9788-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="e9788-131">有关基于订阅的说明，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="e9788-132">[在 EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e9788-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="e9788-133">[在 Microsoft Defender 中为用户配置Office 365。](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e9788-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="e9788-134">有关建议的欺骗智能设置，请参阅 [EOP 防钓鱼策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="e9788-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="e9788-135">管理欺骗性发件人</span><span class="sxs-lookup"><span data-stu-id="e9788-135">Manage spoofed senders</span></span>

<span data-ttu-id="e9788-136">有两种方法允许和阻止欺骗发件人：</span><span class="sxs-lookup"><span data-stu-id="e9788-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="e9788-137">使用欺骗智能策略</span><span class="sxs-lookup"><span data-stu-id="e9788-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="e9788-138">使用欺骗智能见解</span><span class="sxs-lookup"><span data-stu-id="e9788-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="e9788-139">管理欺骗智能策略中的欺骗发件人</span><span class="sxs-lookup"><span data-stu-id="e9788-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="e9788-140">在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="e9788-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e9788-141">在"**反垃圾邮件设置"页上**，单击" ![ 展开图标 ](../../media/scc-expand-icon.png) "展开 **"欺骗智能策略"。**</span><span class="sxs-lookup"><span data-stu-id="e9788-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![选择欺骗智能策略](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="e9788-143">进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="e9788-144">**查看新发件人**</span><span class="sxs-lookup"><span data-stu-id="e9788-144">**Review new senders**</span></span>
   - <span data-ttu-id="e9788-145">**向我显示我已审阅的发件人**</span><span class="sxs-lookup"><span data-stu-id="e9788-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="e9788-146">在 **确定是否允许这些发件人欺骗** 出现的用户飞出邮件中，选择以下选项卡之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="e9788-147">**你的域**：发件人欺骗内部域中的用户。</span><span class="sxs-lookup"><span data-stu-id="e9788-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="e9788-148">**外部域**：发件人欺骗外部域中的用户。</span><span class="sxs-lookup"><span data-stu-id="e9788-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="e9788-149">单击 ![ "允许 ](../../media/scc-expand-icon.png) 欺骗 **？"列中的"展开图标** "。</span><span class="sxs-lookup"><span data-stu-id="e9788-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="e9788-150&quot;>选择 **&quot;** 是&quot;以允许欺骗发件人，或选择&quot; **否** &quot;将邮件标记为欺骗邮件。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e9788-150&quot;>Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id=&quot;e9788-151&quot;>该操作由默认反网络钓鱼策略或自定义防钓鱼策略控制， (默认值为&quot;将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="e9788-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e9788-152">有关详细信息，请参阅[反钓鱼策略中的“欺骗”设置](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e9788-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![显示欺骗性发件人飞出以及是否允许发件人欺骗的屏幕截图](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="e9788-154">您看到的列和值如下列表所示：</span><span class="sxs-lookup"><span data-stu-id="e9788-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="e9788-155">**欺骗用户**：被欺骗的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e9788-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="e9788-156">这是"发件人"地址 (也称为电子邮件 `5322.From`) 中显示的地址发件人。</span><span class="sxs-lookup"><span data-stu-id="e9788-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="e9788-157">SPF 不检查此地址的有效性。</span><span class="sxs-lookup"><span data-stu-id="e9788-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="e9788-158">在 **"你的域** "选项卡上，值包含一个电子邮件地址，或者，如果源电子邮件服务器欺骗多个用户帐户，则它包含 **多个**。</span><span class="sxs-lookup"><span data-stu-id="e9788-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="e9788-159">在 **"外部域** "选项卡上，值包含欺骗用户的域，而不是完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e9788-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="e9788-160">**发送基础结构**：在反向 DNS 查找 (找到的域) 源电子邮件服务器的 IP 地址的 PTR 记录。</span><span class="sxs-lookup"><span data-stu-id="e9788-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="e9788-161">如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="e9788-162">有关邮件源和邮件发件人的信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="e9788-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="e9788-163">**邮件数**：过去 30 天内从发送基础结构发送到包含指定欺骗性发件人或发件人的组织的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="e9788-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="e9788-164">**用户投诉数**：用户最近 30 天内针对此发件人提出投诉。</span><span class="sxs-lookup"><span data-stu-id="e9788-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="e9788-165">投诉通常采用向 Microsoft 提交垃圾邮件的形式。</span><span class="sxs-lookup"><span data-stu-id="e9788-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="e9788-166">**身份验证结果**：下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="e9788-167">**已通过**：发件人已通过 SPF 或 DKIM (发件人电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="e9788-168">**失败**：发件人未通过 EOP 发件人身份验证检查。</span><span class="sxs-lookup"><span data-stu-id="e9788-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="e9788-169">**未知**：这些检查的结果未知。</span><span class="sxs-lookup"><span data-stu-id="e9788-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="e9788-170">**决策集：** 显示谁确定发送基础结构是否允许欺骗用户：</span><span class="sxs-lookup"><span data-stu-id="e9788-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="e9788-171">**欺骗智能策略** (自动) </span><span class="sxs-lookup"><span data-stu-id="e9788-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="e9788-172">**管理员** (手动) </span><span class="sxs-lookup"><span data-stu-id="e9788-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="e9788-173">**Last seen**： The last date when a message was received from the sending infrastructure that contains the spoofed user.</span><span class="sxs-lookup"><span data-stu-id="e9788-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="e9788-174">**允许欺骗？：** 你在此处看到的值是：</span><span class="sxs-lookup"><span data-stu-id="e9788-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="e9788-175">**是**：允许来自欺骗用户和发送基础结构组合的邮件，并且不会被视为欺骗电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="e9788-176">**否**：来自欺骗用户和发送基础结构组合的邮件被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="e9788-177">该操作由默认反网络钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="e9788-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e9788-178">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="e9788-178">See the next section for more information.</span></span>

     - <span data-ttu-id="e9788-179">**某些用户** (你的域"选项卡) ：发送基础结构是欺骗多个用户，其中允许一些欺骗用户，另一些不允许。</span><span class="sxs-lookup"><span data-stu-id="e9788-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="e9788-180">使用 **"详细** "选项卡查看特定地址。</span><span class="sxs-lookup"><span data-stu-id="e9788-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="e9788-181">在页面底部，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="e9788-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="e9788-182">使用 PowerShell 管理欺骗性发件人</span><span class="sxs-lookup"><span data-stu-id="e9788-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="e9788-183">若要查看欺骗智能中允许和阻止的发件人，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="e9788-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="e9788-184">此示例返回有关允许其欺骗域中用户的所有发件人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9788-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="e9788-185">有关语法和参数的详细信息，请参阅 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e9788-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="e9788-186">若要在欺骗智能中配置允许和阻止的发件人，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e9788-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="e9788-187">通过运行以下命令将 **Get-PhishFilterPolicy** cmdlet 的输出写入 CSV 文件，捕获检测到的欺骗发件人的当前列表：</span><span class="sxs-lookup"><span data-stu-id="e9788-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="e9788-188">编辑 CSV 文件以添加或修改以下值：</span><span class="sxs-lookup"><span data-stu-id="e9788-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="e9788-189">**发件人** (源服务器的 PTR 记录或 IP/24 地址记录中的) </span><span class="sxs-lookup"><span data-stu-id="e9788-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="e9788-190">**SpoofedUser：** 下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="e9788-191">内部用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e9788-191">The internal user's email address.</span></span>
     - <span data-ttu-id="e9788-192">外部用户的电子邮件域。</span><span class="sxs-lookup"><span data-stu-id="e9788-192">The external user's email domain.</span></span>
     - <span data-ttu-id="e9788-193">一个空白值，指示你想要阻止或允许来自指定发件人的任何及所有欺骗邮件，而不考虑欺骗的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e9788-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="e9788-194">**AllowedToSpoof** (是或否) </span><span class="sxs-lookup"><span data-stu-id="e9788-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="e9788-195">**SpoofType** (内部或外部) </span><span class="sxs-lookup"><span data-stu-id="e9788-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="e9788-196">通过运行以下命令保存文件、读取文件，将内容存储为名为 `$UpdateSpoofedSenders` 的变量：</span><span class="sxs-lookup"><span data-stu-id="e9788-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="e9788-197">通过 `$UpdateSpoofedSenders` 运行以下命令，使用 变量配置欺骗智能策略：</span><span class="sxs-lookup"><span data-stu-id="e9788-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="e9788-198">有关语法和参数的详细信息，请参阅 [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="e9788-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="e9788-199">在欺骗智能见解中管理欺骗发件人</span><span class="sxs-lookup"><span data-stu-id="e9788-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="e9788-200">在安全与&中心，转到"**威胁管理仪表板** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="e9788-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="e9788-201">在 **"Insights"** 行中，查找以下项目之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="e9788-202">**过去七天内** 可能欺骗的域：此见解表明在默认情况下 (已启用欺骗智能) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="e9788-203">**启用欺骗** 保护：此见解表明已禁用欺骗智能，单击该见解将允许你启用欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="e9788-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="e9788-204">仪表板上的见解显示如下所示的信息：</span><span class="sxs-lookup"><span data-stu-id="e9788-204">The insight on the dashboard shows you information like this:</span></span>

   ![欺骗智能见解的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="e9788-206">此见解有两种模式：</span><span class="sxs-lookup"><span data-stu-id="e9788-206">This insight has two modes:</span></span>

   - <span data-ttu-id="e9788-207">**见解模式**：如果启用了欺骗智能，该见解将展示在过去七天内我们的欺骗智能功能所影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="e9788-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="e9788-208">**如果模式**：如果禁用了欺骗智能，那么该见解将展示在过去七天内有多少邮件会受我们的欺骗智能功能的影响。</span><span class="sxs-lookup"><span data-stu-id="e9788-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="e9788-209">无论使用哪种方式，见解中显示的欺骗性域都分为两类： **可疑** 域 **和非可疑域**。</span><span class="sxs-lookup"><span data-stu-id="e9788-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="e9788-210">**可疑域**：</span><span class="sxs-lookup"><span data-stu-id="e9788-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="e9788-211">**高可信度欺骗**：根据历史发送模式和域的信誉分数，我们高度确信这些域是欺骗，来自这些域的邮件更有可能是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="e9788-212">**中等** 可信度欺骗：根据历史发送模式和域的信誉分数，我们确信这些域是欺骗的，并且从这些域发送的邮件是合法的。</span><span class="sxs-lookup"><span data-stu-id="e9788-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="e9788-213">在此类别中，误报的可能性大于高可信度欺骗。</span><span class="sxs-lookup"><span data-stu-id="e9788-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="e9788-214">**非可疑域**：域未通过显式电子邮件身份验证检查 [SPF、DKIM](how-office-365-uses-spf-to-prevent-spoofing.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。 [](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="e9788-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="e9788-215">但是，域已通过隐式电子邮件身份验证检查， ([身份验证) 。](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="e9788-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="e9788-216">因此，未对邮件执行反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="e9788-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="e9788-217">查看有关可疑域和非可疑域的详细信息</span><span class="sxs-lookup"><span data-stu-id="e9788-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="e9788-218">在"欺骗智能见解"上，单击" **可疑** 域或非 **可疑** 域"以转到" **欺骗智能见解"** 页面。</span><span class="sxs-lookup"><span data-stu-id="e9788-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="e9788-219">" **欺骗智能见解** "页包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="e9788-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="e9788-220">**欺骗性** 域：电子邮件客户端的"来源"框中显示的欺骗用户的域。 </span><span class="sxs-lookup"><span data-stu-id="e9788-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="e9788-221">此地址也称为 `5322.From` 地址。</span><span class="sxs-lookup"><span data-stu-id="e9788-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="e9788-222">**基础结构**：也称为发送 _基础结构_。</span><span class="sxs-lookup"><span data-stu-id="e9788-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="e9788-223">反向 DNS 查找中的域 (源) IP 地址的 PTR 记录。</span><span class="sxs-lookup"><span data-stu-id="e9788-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="e9788-224">如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。</span><span class="sxs-lookup"><span data-stu-id="e9788-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="e9788-225">**邮件计数**：过去 7 天内从发送基础结构发送到包含指定欺骗域的组织的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="e9788-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="e9788-226">**上次看到** 时间：从包含欺骗域的发送基础结构接收邮件的最后日期。</span><span class="sxs-lookup"><span data-stu-id="e9788-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="e9788-227">**欺骗类型**：此值为 **External**。</span><span class="sxs-lookup"><span data-stu-id="e9788-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="e9788-228">**允许欺骗？：** 你在此处看到的值是：</span><span class="sxs-lookup"><span data-stu-id="e9788-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="e9788-229">**是**：允许来自欺骗用户域和发送基础结构组合的邮件，且不会被视为欺骗电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="e9788-230">**否**：来自欺骗用户域和发送基础结构组合的邮件被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="e9788-231">该操作由默认反网络钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="e9788-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="e9788-232">在列表中选择一个项目，以查看有关在飞出视图中的域/发送基础结构对的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9788-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="e9788-233">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="e9788-233">The information includes:</span></span>
   - <span data-ttu-id="e9788-234">我们为什么捕获到此。</span><span class="sxs-lookup"><span data-stu-id="e9788-234">Why we caught this.</span></span>
   - <span data-ttu-id="e9788-235">需要执行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="e9788-235">What you need to do.</span></span>
   - <span data-ttu-id="e9788-236">域摘要。</span><span class="sxs-lookup"><span data-stu-id="e9788-236">A domain summary.</span></span>
   - <span data-ttu-id="e9788-237">WhoIs 有关发件人的数据。</span><span class="sxs-lookup"><span data-stu-id="e9788-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="e9788-238">我们在租户中看到的来自同一发件人的类似邮件。</span><span class="sxs-lookup"><span data-stu-id="e9788-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="e9788-239">在此处，还可以选择在允许欺骗发件人允许列表中添加或删除域/发送基础结构对。 </span><span class="sxs-lookup"><span data-stu-id="e9788-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="e9788-240">只需相应地设置切换。</span><span class="sxs-lookup"><span data-stu-id="e9788-240">Simply set the toggle accordingly.</span></span>

   !["欺骗智能见解详细信息"窗格中域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e9788-242">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="e9788-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="e9788-243">若要验证是否向允许和不允许欺骗的发件人配置了欺骗智能，请执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="e9788-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="e9788-244">在安全&合规中心，转到"威胁管理""策略""反垃圾邮件"展开"反垃圾邮件智能策略"，选择"向我显示已审阅的发件人"选择"你的域"或"外部域"选项卡，并验证发件人的" \>  \>  \>  \>  \> **允许** 欺骗？"值。</span><span class="sxs-lookup"><span data-stu-id="e9788-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="e9788-245">在 PowerShell 中，运行以下命令以查看允许和不允许欺骗的发件人：</span><span class="sxs-lookup"><span data-stu-id="e9788-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="e9788-246">在 PowerShell 中，运行以下命令，将所有欺骗性发件人的列表导出到 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="e9788-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
