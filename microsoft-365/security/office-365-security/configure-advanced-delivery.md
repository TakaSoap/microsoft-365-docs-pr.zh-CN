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
ms.openlocfilehash: 0e4e230fdca7fe29fc1c7a1bc68085454ba883b9
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624785"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="20276-103">配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="20276-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="20276-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="20276-104">**Applies to**</span></span>
- [<span data-ttu-id="20276-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="20276-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="20276-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="20276-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="20276-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20276-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="20276-108">本文介绍的功能在预览版中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="20276-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="20276-109">若要在默认情况下保证[](secure-by-default.md)组织安全，Exchange Online Protection (EOP) 不允许对导致恶意软件或高可信度钓鱼裁定的邮件的安全列表或筛选绕过。</span><span class="sxs-lookup"><span data-stu-id="20276-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that result in malware or high confidence phishing verdicts.</span></span> <span data-ttu-id="20276-110">但是，有一些特定方案需要传递未筛选的邮件。</span><span class="sxs-lookup"><span data-stu-id="20276-110">But there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="20276-111">例如：</span><span class="sxs-lookup"><span data-stu-id="20276-111">For example:</span></span>

- <span data-ttu-id="20276-112">**第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="20276-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="20276-113">**SecOps (安全**) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。</span><span class="sxs-lookup"><span data-stu-id="20276-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="20276-114">在邮件 _中，可以使用_ Microsoft 365策略来阻止筛选这些特定方案中的邮件 <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="20276-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered<sup>\*</sup>.</span></span> <span data-ttu-id="20276-115">高级传递策略可确保不筛选这些方案中的邮件：</span><span class="sxs-lookup"><span data-stu-id="20276-115">The advanced delivery policy ensures that messages in these scenarios are not filtered:</span></span>

- <span data-ttu-id="20276-116">EOP 和 Microsoft Defender 中的筛选器Office 365这些邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20276-116">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="20276-117">[零时差清除 (垃圾邮件 ](zero-hour-auto-purge.md)) 对此类邮件不执行任何操作。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20276-117">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing takes no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="20276-118">[对于这些方案](alerts.md) ，不会触发默认系统警报。</span><span class="sxs-lookup"><span data-stu-id="20276-118">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="20276-119">[AIR 和 Defender for Office 365](office-365-air.md)将忽略这些消息。</span><span class="sxs-lookup"><span data-stu-id="20276-119">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="20276-120">专用于第三方网络钓鱼模拟：</span><span class="sxs-lookup"><span data-stu-id="20276-120">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="20276-121">[管理员提交](admin-submission.md) 生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。</span><span class="sxs-lookup"><span data-stu-id="20276-121">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="20276-122">不会触发警报和 AIR。</span><span class="sxs-lookup"><span data-stu-id="20276-122">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="20276-123">[保险箱 Defender for Office 365](safe-links.md)中的链接不会阻止或触发这些邮件中专门标识的 URL。</span><span class="sxs-lookup"><span data-stu-id="20276-123">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="20276-124">[保险箱 Defender for Office 365](safe-attachments.md)中的附件不会触发这些邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="20276-124">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="20276-125"><sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。</span><span class="sxs-lookup"><span data-stu-id="20276-125"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="20276-126">由高级传递策略标识的邮件不是安全威胁，因此邮件标记为系统替代。</span><span class="sxs-lookup"><span data-stu-id="20276-126">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="20276-127">管理员可以在下列体验中筛选和分析这些系统替代：</span><span class="sxs-lookup"><span data-stu-id="20276-127">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="20276-128">Defender for Office 365 计划 2 中的威胁资源管理器/实时检测</span><span class="sxs-lookup"><span data-stu-id="20276-128">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="20276-129">威胁[资源管理器/实时](mdo-email-entity-page.md)检测中的电子邮件实体页面</span><span class="sxs-lookup"><span data-stu-id="20276-129">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="20276-130">[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="20276-130">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="20276-131">Microsoft Defender for Endpoint 中的高级搜寻</span><span class="sxs-lookup"><span data-stu-id="20276-131">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="20276-132">市场活动视图</span><span class="sxs-lookup"><span data-stu-id="20276-132">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20276-133">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="20276-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20276-134">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="20276-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20276-135">若要直接转到高级传递 **页面，** 请打开 <https://protection.office.com/advanceddelivery> 。</span><span class="sxs-lookup"><span data-stu-id="20276-135">To go directly to the **Advanced delivery** page, open <https://protection.office.com/advanceddelivery>.</span></span>

- <span data-ttu-id="20276-136">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="20276-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="20276-137">若要在高级传递策略中创建、修改或删除配置的设置，您需要是安全与合规中心中安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组 **的成员**。 **&** </span><span class="sxs-lookup"><span data-stu-id="20276-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Security & Compliance Center** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>  
  - <span data-ttu-id="20276-138">若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="20276-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="20276-139">有关详细信息，请参阅安全与[合规&中的权限](permissions-in-the-security-and-compliance-center.md)和[Exchange Online。](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="20276-139">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="20276-140">使用安全&中心在高级传递策略中配置第三方网络钓鱼模拟</span><span class="sxs-lookup"><span data-stu-id="20276-140">Use the Security & Compliance Center to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="20276-141">在安全与&中心，转到"**威胁管理** 策略高级 \>  \> **传递"。**</span><span class="sxs-lookup"><span data-stu-id="20276-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="20276-142">在"**高级传递"** 页上，选择"**网络钓鱼模拟**"选项卡，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="20276-142">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="20276-143">在 **打开的第三方网络钓鱼** 模拟飞出上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="20276-143">On the **Third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="20276-144">**发送域**：至少需要一个电子邮件地址 (，例如 contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="20276-144">**Sending domain**: At least one email address domain is required (for example, contoso.com).</span></span> <span data-ttu-id="20276-145">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="20276-145">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="20276-146">**发送 IP：** 至少需要一个有效的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="20276-146">**Sending IP**: At least one valid IPv4 address is required.</span></span> <span data-ttu-id="20276-147">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="20276-147">You can add up to 10 entries.</span></span> <span data-ttu-id="20276-148">有效值为：</span><span class="sxs-lookup"><span data-stu-id="20276-148">Valid values are:</span></span>
     - <span data-ttu-id="20276-149">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="20276-149">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="20276-150">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="20276-150">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="20276-151">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="20276-151">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="20276-152">**要允许的** 模拟 URL：（可选）输入属于网络钓鱼模拟活动的特定 URL，不应被阻止或触发。</span><span class="sxs-lookup"><span data-stu-id="20276-152">**Simulation URLs to allow**: Optionally, enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated.</span></span> <span data-ttu-id="20276-153">您最多可以添加 10 个条目。</span><span class="sxs-lookup"><span data-stu-id="20276-153">You can add up to 10 entries.</span></span>

4. <span data-ttu-id="20276-154">完成后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="20276-154">When you're finished, click **Save.**</span></span>

<span data-ttu-id="20276-155">您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上** 。若要进行更改，请单击选项卡 **上的** "编辑"。</span><span class="sxs-lookup"><span data-stu-id="20276-155">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="20276-156">使用安全&中心在高级传递策略中配置 SecOps 邮箱</span><span class="sxs-lookup"><span data-stu-id="20276-156">Use the Security & Compliance Center to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="20276-157">在安全与&中心，转到"**威胁管理策略**"" \>  \> **高级传递"。**</span><span class="sxs-lookup"><span data-stu-id="20276-157">In the Security & Compliance Center, go to **Threat Management** \> **Policy** \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="20276-158">在"**高级传递"** 页上，选择 **"SecOps 邮箱"** 选项卡，然后单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="20276-158">On the **Advanced delivery** page, select the **SecOps mailbox** tab, and then click **Edit**.</span></span>

3. <span data-ttu-id="20276-159">在打开 **的 SecOps** 邮箱飞出区中，输入要Exchange Online SecOps 邮箱的现有邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="20276-159">On the **SecOps mailbox** flyout that opens, enter the email addresses of existing Exchange Online mailboxes that you want to designate as SecOps mailboxes.</span></span> <span data-ttu-id="20276-160">不允许通讯组。</span><span class="sxs-lookup"><span data-stu-id="20276-160">Distribution groups are not allowed.</span></span>

4. <span data-ttu-id="20276-161">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="20276-161">When you're finished, click **Save**.</span></span>

<span data-ttu-id="20276-162">您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击选项卡 **上的** "编辑"。</span><span class="sxs-lookup"><span data-stu-id="20276-162">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="20276-163">需要筛选旁路的其他方案</span><span class="sxs-lookup"><span data-stu-id="20276-163">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="20276-164">除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：</span><span class="sxs-lookup"><span data-stu-id="20276-164">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="20276-165">**第三方筛选器**：如果你的域的 MX记录没有指向Office 365 (邮件将路由到其他位置) ，默认情况下，安全 [](secure-by-default.md)*不可用*。</span><span class="sxs-lookup"><span data-stu-id="20276-165">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span>

  <span data-ttu-id="20276-166">若要绕过 Microsoft 筛选已由第三方筛选评估的邮件，请使用邮件流规则 (也称为传输规则) ，请参阅使用邮件流规则设置邮件[中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)</span><span class="sxs-lookup"><span data-stu-id="20276-166">To bypass Microsoft filtering for messages that have already been evaluated by third-party filtering, use mail flow rules (also known as transport rules), see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="20276-167">正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件，以报告被 [](admin-submission.md)错误地标记为对 Microsoft (误报错误的已知) 。</span><span class="sxs-lookup"><span data-stu-id="20276-167">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="20276-168">与所有替代一样， **_强烈建议临时进行_** 这些替代。</span><span class="sxs-lookup"><span data-stu-id="20276-168">As with all overrides, it is **_highly recommended_** that these allowances be made temporarily.</span></span>
