---
title: 配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理员可以了解如何使用 Exchange Online Protection (EOP) 中的高级传递策略识别不应在特定的支持方案中筛选的邮件 (第三方网络钓鱼模拟以及传递到安全操作 (SecOps) 邮箱的邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b989b11739b5418ad14e147f76dde0e0dd7b1b1a
ms.sourcegitcommit: 233989a02a3fc6db33c995ad06b1f820f08f8f0a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383446"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="11078-103">配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="11078-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="11078-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="11078-104">**Applies to**</span></span>
- [<span data-ttu-id="11078-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="11078-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="11078-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="11078-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="11078-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11078-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="11078-108">本文介绍的功能在预览版中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="11078-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="11078-109">若要在默认情况下保证[](secure-by-default.md)组织安全，Exchange Online Protection (EOP) 不允许对标识为恶意软件或高可信度网络钓鱼的邮件进行安全列表或筛选绕过。</span><span class="sxs-lookup"><span data-stu-id="11078-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="11078-110">但是，有一些特定方案需要传递未筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="11078-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="11078-111">例如：</span><span class="sxs-lookup"><span data-stu-id="11078-111">For example:</span></span>

- <span data-ttu-id="11078-112">**第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="11078-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="11078-113">**SecOps (安全**) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。</span><span class="sxs-lookup"><span data-stu-id="11078-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="11078-114">在邮件 _中，可以使用_ Microsoft 365策略来阻止筛选这些特定方案中的邮件。  <sup>\*</sup>高级传递策略可确保这些方案中的邮件获得以下结果：</span><span class="sxs-lookup"><span data-stu-id="11078-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="11078-115">EOP 和 Microsoft Defender 中的筛选器Office 365这些邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="11078-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="11078-116">[零时差清除 (对 ](zero-hour-auto-purge.md)) 和网络钓鱼的 ZAP 邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="11078-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="11078-117">[对于这些方案](alerts.md) ，不会触发默认系统警报。</span><span class="sxs-lookup"><span data-stu-id="11078-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="11078-118">[AIR 和 Defender for Office 365](office-365-air.md)将忽略这些消息。</span><span class="sxs-lookup"><span data-stu-id="11078-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="11078-119">专用于第三方网络钓鱼模拟：</span><span class="sxs-lookup"><span data-stu-id="11078-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="11078-120">[管理员提交](admin-submission.md) 生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。</span><span class="sxs-lookup"><span data-stu-id="11078-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="11078-121">不会触发警报和 AIR。</span><span class="sxs-lookup"><span data-stu-id="11078-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="11078-122">[保险箱 Defender for Office 365](safe-links.md)中的链接不会阻止或触发这些邮件中专门标识的 URL。</span><span class="sxs-lookup"><span data-stu-id="11078-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="11078-123">[保险箱 Defender for Office 365](safe-attachments.md)中的附件不会触发这些邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="11078-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="11078-124"><sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。</span><span class="sxs-lookup"><span data-stu-id="11078-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="11078-125">由高级传递策略标识的邮件不是安全威胁，因此邮件标记为系统替代。</span><span class="sxs-lookup"><span data-stu-id="11078-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="11078-126">管理员可以在下列体验中筛选和分析这些系统替代：</span><span class="sxs-lookup"><span data-stu-id="11078-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="11078-127">Defender for Office 365 计划 2 中的威胁资源管理器/实时检测</span><span class="sxs-lookup"><span data-stu-id="11078-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="11078-128">威胁[资源管理器/实时](mdo-email-entity-page.md)检测中的电子邮件实体页面</span><span class="sxs-lookup"><span data-stu-id="11078-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="11078-129">[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="11078-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="11078-130">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="11078-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="11078-131">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="11078-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11078-132">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="11078-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11078-133">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="11078-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="11078-134">若要直接转到高级传递 **页面，** 请打开 <https://security.microsoft.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="11078-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="11078-135">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11078-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="11078-136">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="11078-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="11078-137">若要在高级传递策略中创建、修改或删除配置的设置，您需要是 Microsoft 365 Defender 门户中安全管理员角色组的成员以及 **Exchange Online** 中的组织管理角色 **组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="11078-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="11078-138">若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="11078-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="11078-139">有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="11078-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="11078-140">将用户添加到相应的 Azure Active Directory 角色会为用户提供在 Microsoft 365 Defender _门户中_ 所需的权限，以及用户对 Microsoft 365 中其他功能Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="11078-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="11078-141">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="11078-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="11078-142">使用 Microsoft 365 Defender门户在高级传递策略中配置 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="11078-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="11078-143">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** threat \> **policies** page \> **Rules** section \> **Advanced delivery**.</span><span class="sxs-lookup"><span data-stu-id="11078-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="11078-144">在" **高级传递"** 页上，确认 **"SecOps** 邮箱"选项卡已选中，然后执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="11078-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="11078-145">单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="11078-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="11078-146">如果没有配置网络钓鱼模拟，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="11078-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="11078-147">在打开的"编辑 **SecOps** 邮箱"飞出控件上，通过执行以下步骤之一输入要指定为 SecOps 邮箱的现有 Exchange Online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="11078-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="11078-148">在框中单击，让邮箱列表解析，然后选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="11078-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="11078-149">单击框中开始键入邮箱 (名称、显示名称、别名、电子邮件地址、帐户名等 ) 的标识符，然后从结果中选择 (显示名称) 邮箱标识符。</span><span class="sxs-lookup"><span data-stu-id="11078-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="11078-150">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="11078-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="11078-151">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="11078-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="11078-152">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="11078-152">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="11078-154">“删除”。</span><span class="sxs-lookup"><span data-stu-id="11078-154">next to the value.</span></span>

4. <span data-ttu-id="11078-155">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="11078-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="11078-156">您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。</span><span class="sxs-lookup"><span data-stu-id="11078-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="11078-157">使用Microsoft 365 Defender门户在高级传递策略中配置第三方网络钓鱼模拟</span><span class="sxs-lookup"><span data-stu-id="11078-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="11078-158">In the Microsoft 365 Defender portal， go to **Email & Collaboration** Policies & \> **Rules** threat \> **policies** page \> **Rules** section \> **Advanced delivery**.</span><span class="sxs-lookup"><span data-stu-id="11078-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="11078-159">在" **高级传递"** 页上，选择" **网络钓鱼模拟** "选项卡，然后执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="11078-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="11078-160">单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="11078-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="11078-161">如果没有配置网络钓鱼模拟，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="11078-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="11078-162">在打开 **的"编辑第三方网络钓鱼** 模拟"飞出控件上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="11078-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="11078-163">发送域：展开此设置并输入至少一个电子邮件地址域 (例如，contoso.com) 方法是单击该框，输入值，然后按 Enter 或选择显示在框下方的值。</span><span class="sxs-lookup"><span data-stu-id="11078-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="11078-164">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="11078-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="11078-165">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="11078-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="11078-166">**发送 IP：** 展开此设置，并输入至少一个有效的 IPv4 地址，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。</span><span class="sxs-lookup"><span data-stu-id="11078-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="11078-167">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="11078-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="11078-168">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="11078-168">You can add up to 10 entries.</span></span> <span data-ttu-id="11078-169">有效值为：</span><span class="sxs-lookup"><span data-stu-id="11078-169">Valid values are:</span></span>
     - <span data-ttu-id="11078-170">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="11078-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="11078-171">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="11078-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="11078-172">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="11078-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="11078-173">要允许的模拟 URL：展开此设置，并选择输入属于网络钓鱼模拟活动的一部分的特定 URL，这些 URL 不应被阻止或触发，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。</span><span class="sxs-lookup"><span data-stu-id="11078-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="11078-174">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="11078-174">You can add up to 10 entries.</span></span> <span data-ttu-id="11078-175">有关 URL 语法格式，请参阅 [租户允许/阻止列表的 URL 语法](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list)。</span><span class="sxs-lookup"><span data-stu-id="11078-175">For the URL syntax format, see [URL syntax for the Tenant Allow/Block List](/microsoft-365/security/office-365-security/tenant-allow-block-list#url-syntax-for-the-tenant-allowblock-list).</span></span>

   <span data-ttu-id="11078-176">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="11078-176">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="11078-178">“删除”。</span><span class="sxs-lookup"><span data-stu-id="11078-178">next to the value.</span></span>

4. <span data-ttu-id="11078-179">完成后，请执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="11078-179">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="11078-180">**第一次**：单击 **"添加"，** 然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="11078-180">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="11078-181">**编辑现有**：单击"**保存"，** 然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="11078-181">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="11078-182">您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上**。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。</span><span class="sxs-lookup"><span data-stu-id="11078-182">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="11078-183">需要筛选旁路的其他方案</span><span class="sxs-lookup"><span data-stu-id="11078-183">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="11078-184">除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：</span><span class="sxs-lookup"><span data-stu-id="11078-184">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="11078-185">**第三方筛选器**：如果你的域的 MX记录没有指向Office 365 (邮件将路由到其他位置) ，默认情况下，安全 [](secure-by-default.md)*不可用*。</span><span class="sxs-lookup"><span data-stu-id="11078-185">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="11078-186">如果要添加保护，则需要启用连接器的增强筛选 (也称为跳过 *列表) 。*</span><span class="sxs-lookup"><span data-stu-id="11078-186">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="11078-187">有关详细信息，请参阅[使用第三](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)方云服务管理邮件流Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="11078-187">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="11078-188">如果您不希望增强连接器筛选，请使用邮件流规则 (也称为传输规则) ，以绕过 Microsoft 筛选已由第三方筛选评估的邮件。</span><span class="sxs-lookup"><span data-stu-id="11078-188">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="11078-189">有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="11078-189">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="11078-190">正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件，以报告被 [](admin-submission.md)错误地标记为对 Microsoft (误报错误的已知) 。</span><span class="sxs-lookup"><span data-stu-id="11078-190">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="11078-191">与所有替代一样， **_我们强烈建议这些_** 允许是临时的。</span><span class="sxs-lookup"><span data-stu-id="11078-191">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="11078-192">Exchange Online高级传递策略中 SecOps 邮箱的 PowerShell 过程</span><span class="sxs-lookup"><span data-stu-id="11078-192">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="11078-193">在 Exchange Online PowerShell 中，高级传递策略中 SecOps 邮箱的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="11078-193">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="11078-194">**SecOps 覆盖策略**：由 **\* -SecOpsOverridePolicy** cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="11078-194">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="11078-195">**SecOps 重写规则**：由 **\* -SecOpsOverrideRule** cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="11078-195">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="11078-196">此行为具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="11078-196">This behavior has the following results:</span></span>

- <span data-ttu-id="11078-197">首先创建策略，然后创建标识规则所适用的策略的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-197">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="11078-198">从 PowerShell 中删除策略时，也会删除相应的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-198">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="11078-199">从 PowerShell 中删除规则时，不会删除相应的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-199">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="11078-200">需要手动删除相应的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-200">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="11078-201">使用 PowerShell 配置 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="11078-201">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="11078-202">在 PowerShell 的高级传递策略中配置 SecOps 邮箱的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="11078-202">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="11078-203">创建 SecOps 覆盖策略。</span><span class="sxs-lookup"><span data-stu-id="11078-203">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="11078-204">创建 SecOps 替代规则，该规则指定应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-204">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="11078-205">步骤 1：使用 PowerShell 创建 SecOps 覆盖策略</span><span class="sxs-lookup"><span data-stu-id="11078-205">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="11078-206">若要创建 SecOps 覆盖策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-206">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="11078-207">**注意**：无论您指定的 Name 值如何，策略名称都将为 SecOpsOverridePolicy，因此您可能还使用该值。</span><span class="sxs-lookup"><span data-stu-id="11078-207">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="11078-208">本示例将创建 SecOps 邮箱策略。</span><span class="sxs-lookup"><span data-stu-id="11078-208">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="11078-209">有关语法和参数的详细信息，请参阅[New-SecOpsOverridePolicy。](/powershell/module/exchange/new-secopsoverridepolicy)</span><span class="sxs-lookup"><span data-stu-id="11078-209">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="11078-210">步骤 2：使用 PowerShell 创建 SecOps 替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-210">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="11078-211">此示例使用指定的设置创建 SecOps 邮箱规则。</span><span class="sxs-lookup"><span data-stu-id="11078-211">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="11078-212">**注意**：\*\*无论指定 Name 值如何，规则名称将为 SecOpsOverrideRule，其中是唯一的 GUID 值 \<GUID\> (例如 \<GUID\> ，6fed4b63-3563-495d-a481-b24a311f8329) 。</span><span class="sxs-lookup"><span data-stu-id="11078-212">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="11078-213">有关语法和参数的详细信息，请参阅 [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-213">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="11078-214">使用 PowerShell 查看 SecOps 替代策略</span><span class="sxs-lookup"><span data-stu-id="11078-214">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="11078-215">此示例返回有关唯一一个 SecOps 邮箱策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11078-215">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="11078-216">有关语法和参数的详细信息，请参阅 [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-216">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="11078-217">使用 PowerShell 查看 SecOps 替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-217">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="11078-218">此示例返回有关 SecOps 重写规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11078-218">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="11078-219">尽管上一个命令只应返回一个规则，但结果中也可能包含任何挂起删除的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-219">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="11078-220">本示例标识一个规则 (规则) 无效的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-220">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="11078-221">确定无效规则后，可以使用 **Remove-SecOpsOverrideRule** cmdlet 删除这些规则，如本文稍后 [所述](#use-powershell-to-remove-secops-override-rules)。</span><span class="sxs-lookup"><span data-stu-id="11078-221">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="11078-222">有关语法和参数的详细信息，请参阅 [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="11078-222">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="11078-223">使用 PowerShell 修改 SecOps 覆盖策略</span><span class="sxs-lookup"><span data-stu-id="11078-223">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="11078-224">若要修改 SecOps 覆盖策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-224">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="11078-225">此示例将 secops2@contoso.com SecOps 覆盖策略。</span><span class="sxs-lookup"><span data-stu-id="11078-225">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="11078-226">**注意**：如果存在关联的有效 SecOps 替代规则，则规则中的电子邮件地址也将更新。</span><span class="sxs-lookup"><span data-stu-id="11078-226">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="11078-227">有关语法和参数的详细信息，请参阅 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-227">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="11078-228">使用 PowerShell 修改 SecOps 替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-228">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="11078-229">**Set-SecOpsOverrideRule** cmdlet 不会修改 SecOps 替代规则中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="11078-229">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="11078-230">若要修改 SecOps 替代规则中的电子邮件地址，请使用 **Set-SecOpsOverridePolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11078-230">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="11078-231">有关语法和参数的详细信息，请参阅 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-231">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="11078-232">使用 PowerShell 删除 SecOps 覆盖策略</span><span class="sxs-lookup"><span data-stu-id="11078-232">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="11078-233">本示例删除 SecOps 邮箱策略和相应的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-233">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="11078-234">有关语法和参数的详细信息，请参阅 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-234">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="11078-235">使用 PowerShell 删除 SecOps 替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-235">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="11078-236">若要删除 SecOps 替代规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-236">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="11078-237">本示例删除指定的 SecOps 重写规则。</span><span class="sxs-lookup"><span data-stu-id="11078-237">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="11078-238">有关语法和参数的详细信息，请参阅 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-238">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="11078-239">Exchange Online高级传递策略中第三方网络钓鱼模拟的 PowerShell 过程</span><span class="sxs-lookup"><span data-stu-id="11078-239">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="11078-240">在 Exchange Online PowerShell 中，高级传递策略中第三方网络钓鱼模拟的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="11078-240">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="11078-241">**网络钓鱼模拟替代策略**：由 **\* -PhishSimOverridePolicy** cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="11078-241">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="11078-242">**网络钓鱼模拟替代规则**：由 **\* -PhishSimOverrideRule** cmdlet 控制。</span><span class="sxs-lookup"><span data-stu-id="11078-242">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="11078-243">此行为具有以下结果：</span><span class="sxs-lookup"><span data-stu-id="11078-243">This behavior has the following results:</span></span>

- <span data-ttu-id="11078-244">首先创建策略，然后创建标识规则所适用的策略的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-244">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="11078-245">您可以分别修改策略和规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="11078-245">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="11078-246">从 PowerShell 中删除策略时，也会删除相应的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-246">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="11078-247">从 PowerShell 中删除规则时，不会删除相应的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-247">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="11078-248">需要手动删除相应的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-248">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="11078-249">使用 PowerShell 配置第三方网络钓鱼模拟</span><span class="sxs-lookup"><span data-stu-id="11078-249">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="11078-250">在 PowerShell 的高级传递策略中配置第三方网络钓鱼模拟的过程包括两个步骤：</span><span class="sxs-lookup"><span data-stu-id="11078-250">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="11078-251">创建网络钓鱼模拟替代策略。</span><span class="sxs-lookup"><span data-stu-id="11078-251">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="11078-252">创建网络钓鱼模拟替代规则，该规则指定应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="11078-252">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="11078-253">步骤 1：使用 PowerShell 创建网络钓鱼模拟覆盖策略</span><span class="sxs-lookup"><span data-stu-id="11078-253">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="11078-254">此示例创建网络钓鱼模拟替代策略。</span><span class="sxs-lookup"><span data-stu-id="11078-254">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="11078-255">**注意**：无论指定 Name 值如何，策略名称将为 PhishSimOverridePolicy，因此您可能还使用该值。</span><span class="sxs-lookup"><span data-stu-id="11078-255">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="11078-256">有关语法和参数的详细信息，请参阅 [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-256">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="11078-257">步骤 2：使用 PowerShell 创建网络钓鱼模拟替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-257">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="11078-258">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-258">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="11078-259">无论您指定的 Name 值如何，规则名称都是 PhishSimOverrideRule，其中是唯一的 GUID 值 (例如 \<GUID\> \<GUID\> ，a0eae53e-d755-4a42-9320-b9c6b55c5011) 。</span><span class="sxs-lookup"><span data-stu-id="11078-259">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="11078-260">有效的 IP 地址条目是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="11078-260">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="11078-261">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="11078-261">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="11078-262">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="11078-262">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="11078-263">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="11078-263">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="11078-264">此示例使用指定的设置创建网络钓鱼模拟替代规则。</span><span class="sxs-lookup"><span data-stu-id="11078-264">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="11078-265">有关语法和参数的详细信息，请参阅 [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-265">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="11078-266">使用 PowerShell 查看网络钓鱼模拟替代策略</span><span class="sxs-lookup"><span data-stu-id="11078-266">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="11078-267">此示例返回有关唯一网络钓鱼模拟替代策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11078-267">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="11078-268">有关语法和参数的详细信息，请参阅 [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-268">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="11078-269">使用 PowerShell 查看网络钓鱼模拟替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-269">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="11078-270">此示例返回有关网络钓鱼模拟替代规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="11078-270">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="11078-271">尽管上一个命令只应返回一个规则，但结果中也可能包含任何挂起删除的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-271">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="11078-272">本示例标识一个规则 (规则) 无效的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-272">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="11078-273">确定无效规则后，可以使用 **Remove-PhisSimOverrideRule** cmdlet 删除这些规则，如本文稍后 [所述](#use-powershell-to-remove-phishing-simulation-override-rules)。</span><span class="sxs-lookup"><span data-stu-id="11078-273">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="11078-274">有关语法和参数的详细信息，请参阅 [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-274">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="11078-275">使用 PowerShell 修改网络钓鱼模拟替代策略</span><span class="sxs-lookup"><span data-stu-id="11078-275">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="11078-276">若要修改网络钓鱼模拟替代策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-276">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="11078-277">此示例禁用网络钓鱼模拟替代策略。</span><span class="sxs-lookup"><span data-stu-id="11078-277">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="11078-278">有关语法和参数的详细信息，请参阅 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-278">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="11078-279">使用 PowerShell 修改网络钓鱼模拟替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-279">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="11078-280">若要修改网络钓鱼模拟替代规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-280">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="11078-281">此示例使用下列设置修改指定的网络钓鱼模拟替代规则：</span><span class="sxs-lookup"><span data-stu-id="11078-281">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="11078-282">添加域条目 blueyonderairlines.com。</span><span class="sxs-lookup"><span data-stu-id="11078-282">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="11078-283">删除 IP 地址条目 192.168.1.55。</span><span class="sxs-lookup"><span data-stu-id="11078-283">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="11078-284">请注意，这些更改不会影响现有条目。</span><span class="sxs-lookup"><span data-stu-id="11078-284">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="11078-285">有关语法和参数的详细信息，请参阅 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-285">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="11078-286">使用 PowerShell 删除网络钓鱼模拟替代策略</span><span class="sxs-lookup"><span data-stu-id="11078-286">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="11078-287">此示例删除网络钓鱼模拟覆盖策略和相应的规则。</span><span class="sxs-lookup"><span data-stu-id="11078-287">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="11078-288">有关语法和参数的详细信息，请参阅 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)。</span><span class="sxs-lookup"><span data-stu-id="11078-288">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="11078-289">使用 PowerShell 删除网络钓鱼模拟替代规则</span><span class="sxs-lookup"><span data-stu-id="11078-289">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="11078-290">若要删除网络钓鱼模拟替代规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="11078-290">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="11078-291">此示例删除指定的网络钓鱼模拟替代规则。</span><span class="sxs-lookup"><span data-stu-id="11078-291">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="11078-292">有关语法和参数的详细信息，请参阅 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)。</span><span class="sxs-lookup"><span data-stu-id="11078-292">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
