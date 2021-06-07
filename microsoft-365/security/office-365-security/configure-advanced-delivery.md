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
ms.openlocfilehash: a9c1c6f7635b87e25adcb121db79f67d4ec1988f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788988"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="0e4a1-103">配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="0e4a1-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="0e4a1-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-104">**Applies to**</span></span>
- [<span data-ttu-id="0e4a1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0e4a1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0e4a1-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="0e4a1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0e4a1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e4a1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="0e4a1-108">本文介绍的功能在预览版中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="0e4a1-109">若要在默认情况下保证[](secure-by-default.md)组织安全，Exchange Online Protection (EOP) 不允许对标识为恶意软件或高可信度网络钓鱼的邮件进行安全列表或筛选绕过。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="0e4a1-110">但是，有一些特定方案需要传递未筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="0e4a1-111">例如：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-111">For example:</span></span>

- <span data-ttu-id="0e4a1-112">**第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="0e4a1-113">**SecOps (安全**) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="0e4a1-114">在邮件 _中，可以使用_ Microsoft 365策略来阻止筛选这些特定方案中的邮件。  <sup>\*</sup>高级传递策略可确保这些方案中的邮件获得以下结果：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="0e4a1-115">EOP 和 Microsoft Defender 中的筛选器Office 365这些邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4a1-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="0e4a1-116">[零时差清除 (对 ](zero-hour-auto-purge.md)) 和网络钓鱼的 ZAP 邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4a1-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="0e4a1-117">[对于这些方案](alerts.md) ，不会触发默认系统警报。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="0e4a1-118">[AIR 和 Defender for Office 365](office-365-air.md)将忽略这些消息。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="0e4a1-119">专用于第三方网络钓鱼模拟：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="0e4a1-120">[管理员提交](admin-submission.md) 生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="0e4a1-121">不会触发警报和 AIR。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="0e4a1-122">[保险箱 Defender for Office 365](safe-links.md)中的链接不会阻止或触发这些邮件中专门标识的 URL。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="0e4a1-123">[保险箱 Defender for Office 365](safe-attachments.md)中的附件不会触发这些邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="0e4a1-124"><sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="0e4a1-125">由高级传递策略标识的邮件不是安全威胁，因此邮件标记为系统替代。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="0e4a1-126">管理员可以在下列体验中筛选和分析这些系统替代：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="0e4a1-127">Defender for Office 365 计划 2 中的威胁资源管理器/实时检测</span><span class="sxs-lookup"><span data-stu-id="0e4a1-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="0e4a1-128">威胁[资源管理器/实时](mdo-email-entity-page.md)检测中的电子邮件实体页面</span><span class="sxs-lookup"><span data-stu-id="0e4a1-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="0e4a1-129">[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="0e4a1-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="0e4a1-130">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="0e4a1-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="0e4a1-131">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="0e4a1-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0e4a1-132">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0e4a1-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0e4a1-133">在 <https://security.microsoft.com> 打开安全中心。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-133">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="0e4a1-134">若要直接转到高级传递 **页面，** 请打开 <https://security.microsoft.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="0e4a1-135">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-135">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0e4a1-136">若要在高级传递策略中创建、修改或删除配置的设置，您需要是安全中心的安全管理员角色组的成员以及Exchange Online 中的组织管理角色 **组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="0e4a1-136">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **security center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="0e4a1-137">若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-137">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="0e4a1-138">有关详细信息，请参阅安全中心[中的权限Microsoft 365中的权限和](permissions-microsoft-365-security-center.md)[Exchange Online。](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="0e4a1-138">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0e4a1-139">将用户添加到相应的 Azure Active Directory 角色会为用户提供安全中心所需的权限，以及安全中心中其他功能Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-139">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0e4a1-140">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-security-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="0e4a1-141">使用安全中心在高级传递策略中配置 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="0e4a1-141">Use the security center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="0e4a1-142">在安全中心，转到电子邮件&**协作** \> **策略&规则"部分"高级** \>  \>  \> **传递"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-142">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="0e4a1-143">在" **高级传递"** 页上，确认 **"SecOps** 邮箱"选项卡已选中，然后执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-143">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="0e4a1-144">单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-144">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="0e4a1-145">如果没有配置网络钓鱼模拟，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-145">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="0e4a1-146">在打开的"编辑 **SecOps** 邮箱"飞出控件上，通过执行以下步骤之一输入要指定为 SecOps 邮箱的现有 Exchange Online 邮箱：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-146">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="0e4a1-147">在框中单击，让邮箱列表解析，然后选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-147">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="0e4a1-148">单击框中开始键入邮箱 (名称、显示名称、别名、电子邮件地址、帐户名等 ) 的标识符，然后从结果中选择 (显示名称) 邮箱标识符。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-148">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="0e4a1-149">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-149">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="0e4a1-150">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-150">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="0e4a1-151">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="0e4a1-151">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="0e4a1-153">“删除”。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-153">next to the value.</span></span>

4. <span data-ttu-id="0e4a1-154">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-154">When you're finished, click **Save**.</span></span>

<span data-ttu-id="0e4a1-155">您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-155">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-security-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="0e4a1-156">使用安全中心在高级传递策略中配置第三方网络钓鱼模拟</span><span class="sxs-lookup"><span data-stu-id="0e4a1-156">Use the security center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="0e4a1-157">在安全中心，转到电子邮件&**协作** \> **策略&规则"部分"高级** \>  \>  \> **传递"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-157">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="0e4a1-158">在" **高级传递"** 页上，选择" **网络钓鱼模拟** "选项卡，然后执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-158">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="0e4a1-159">单击 ![ "编辑"图标 ](../../media/m365-cc-sc-edit-icon.png) **"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-159">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="0e4a1-160">如果没有配置网络钓鱼模拟，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-160">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="0e4a1-161">在打开 **的"编辑第三方网络钓鱼** 模拟"飞出控件上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-161">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="0e4a1-162">发送域：展开此设置并输入至少一个电子邮件地址域 (例如，contoso.com) 方法是单击该框，输入值，然后按 Enter 或选择显示在框下方的值。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-162">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="0e4a1-163">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-163">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="0e4a1-164">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-164">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="0e4a1-165">**发送 IP：** 展开此设置，并输入至少一个有效的 IPv4 地址，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-165">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="0e4a1-166">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-166">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="0e4a1-167">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-167">You can add up to 10 entries.</span></span> <span data-ttu-id="0e4a1-168">有效值为：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-168">Valid values are:</span></span>
     - <span data-ttu-id="0e4a1-169">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-169">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="0e4a1-170">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-170">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="0e4a1-171">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-171">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="0e4a1-172">要允许的模拟 URL：展开此设置，并选择输入属于网络钓鱼模拟活动的一部分的特定 URL，这些 URL 不应被阻止或触发，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-172">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="0e4a1-173">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-173">You can add up to 10 entries.</span></span>

   <span data-ttu-id="0e4a1-174">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="0e4a1-174">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="0e4a1-176">“删除”。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-176">next to the value.</span></span>

4. <span data-ttu-id="0e4a1-177">完成后，请执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-177">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="0e4a1-178">**第一次**：单击 **"添加"，** 然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-178">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="0e4a1-179">**编辑现有**：单击"**保存"，** 然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="0e4a1-179">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="0e4a1-180">您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上**。若要进行更改，请单击选项卡 ![ 上的" ](../../media/m365-cc-sc-edit-icon.png) 编辑"图标"编辑"。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-180">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="0e4a1-181">需要筛选旁路的其他方案</span><span class="sxs-lookup"><span data-stu-id="0e4a1-181">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="0e4a1-182">除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：</span><span class="sxs-lookup"><span data-stu-id="0e4a1-182">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="0e4a1-183">**第三方筛选器**：如果你的域的 MX记录没有指向Office 365 (邮件将路由到其他位置) ，默认情况下，安全 [](secure-by-default.md)*不可用*。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-183">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="0e4a1-184">若要绕过 Microsoft 筛选已由第三方筛选评估的邮件，请使用邮件流规则 (传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-184">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="0e4a1-185">有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="0e4a1-185">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="0e4a1-186">正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件，以报告被 [](admin-submission.md)错误地标记为对 Microsoft (误报错误的已知) 。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-186">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="0e4a1-187">与所有替代一样， **_我们强烈建议这些_** 允许是临时的。</span><span class="sxs-lookup"><span data-stu-id="0e4a1-187">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>
