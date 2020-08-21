---
title: 配置默认连接筛选器策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online (Protection 或 EOP) 配置连接筛选，以允许或阻止来自电子邮件服务器的电子邮件。
ms.openlocfilehash: 45213ff36c7efc76a83a2c520e0369211ffecf53
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827841"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="9c339-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="9c339-103">Configure connection filtering</span></span>

<span data-ttu-id="9c339-104">如果你是具有 Exchange Online 邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，则在 EOP (中，可在专用连接筛选策略) 通过他们的 IP 地址识别出正常或不好的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="9c339-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="9c339-105">默认连接筛选器策略的关键组件有：</span><span class="sxs-lookup"><span data-stu-id="9c339-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="9c339-106">**IP 允许列表**：跳过对从您按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9c339-106">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="9c339-107">有关垃圾邮件筛选可能仍然发生在这些源发邮件上的情况，请参阅 [本主题后面](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 的"来自 IP 允许列表中来源的邮件仍需进行筛选的方案"部分。</span><span class="sxs-lookup"><span data-stu-id="9c339-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="9c339-108">有关 IP 允许列表应如何适应总体安全发件人策略的详细信息，请参阅 Create safe sender [lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9c339-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="9c339-109">**IP 阻止列表**：阻止来自您按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="9c339-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="9c339-110">传入的邮件将被拒绝，不会标记为垃圾邮件，且无需其他筛选。</span><span class="sxs-lookup"><span data-stu-id="9c339-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="9c339-111">有关如何将 IP 阻止列表放入其中的总体阻止发件人策略的详细信息，请参阅[EOP 中的"创建阻止发件人列表"。](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9c339-111">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="9c339-112">**安全列表**： *安全列表是* Microsoft 数据中心中的动态允许列表，不要求任何客户配置。</span><span class="sxs-lookup"><span data-stu-id="9c339-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="9c339-113">Microsoft 从订阅到各种第三方列表的地址识别这些受信任的电子邮件来源。</span><span class="sxs-lookup"><span data-stu-id="9c339-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="9c339-114">可启用或禁用安全列表的使用;您不能在安全列表中配置源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="9c339-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="9c339-115">安全列表上电子邮件服务器中的传入邮件上的垃圾邮件筛选跳过。</span><span class="sxs-lookup"><span data-stu-id="9c339-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="9c339-116">本主题介绍如何在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 (Exchange Online PowerShell 中配置默认连接筛选器策略;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="9c339-117">有关 EOP 使用连接筛选是整个反垃圾邮件设置的一部分的详细信息，请参阅"[反垃圾邮件保护"。](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="9c339-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9c339-118">IP 允许列表、安全列表和 IP 阻止列表是你总体策略的一部分，用于允许或阻止贵组织的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9c339-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="9c339-119">有关详细信息，请参阅创建安全[发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9c339-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9c339-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9c339-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9c339-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="9c339-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9c339-122">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="9c339-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="9c339-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9c339-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9c339-124">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9c339-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9c339-125">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="9c339-125">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="9c339-126">若要修改默认连接筛选器策略，你必须是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="9c339-126">To modify the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9c339-127">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="9c339-127">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9c339-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="9c339-128">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="9c339-129">对于对默认连接筛选器策略的只读访问权限，你需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="9c339-129">For read-only access to the default connection filter policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="9c339-130">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="9c339-130">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="9c339-131">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="9c339-131">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="9c339-132">要查找电子邮件服务器的源 IP 地址 (要允许或阻止的发件人) 信息，可以检查邮件头中的"IP (**CIP**) 邮件头"字段。</span><span class="sxs-lookup"><span data-stu-id="9c339-132">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="9c339-133">若要查看各种电子邮件客户端中的邮件头，请参阅["在 Outlook 中查看 Internet 邮件头"。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)</span><span class="sxs-lookup"><span data-stu-id="9c339-133">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="9c339-134">IP 允许列表优先于包含两个列表 (列表上的地址的 IP) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-134">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="9c339-135">IP 允许列表和 IP 阻止列表支持最多 1273 个条目，每个条目为单 IP 地址、IP 地址范围或无类别域际路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="9c339-135">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="9c339-136">使用安全&安全中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9c339-136">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="9c339-137">在安全合 &中心内，转到威 **胁** \> **管理** \> **策略反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="9c339-137">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="9c339-138">在"**反垃圾邮件设置"** 页上，单击 **"展开'图标"，** 然后单击"编辑 ![ 策略"，展开 ](../../media/scc-expand-icon.png) "连接**筛选策略"。**</span><span class="sxs-lookup"><span data-stu-id="9c339-138">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="9c339-139">在 **随** 后出现的默认浮出控件中，配置以下任意设置：</span><span class="sxs-lookup"><span data-stu-id="9c339-139">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="9c339-140">**描述**：输入可选描述性文本。</span><span class="sxs-lookup"><span data-stu-id="9c339-140">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="9c339-141">**IP 允许列表：** 单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="9c339-141">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="9c339-142">在出现 **的 IP 允许** 列表浮出控件中，使用以下语法在地址或 **地址范围框中输入** IPV4 地址：</span><span class="sxs-lookup"><span data-stu-id="9c339-142">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="9c339-143">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="9c339-143">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="9c339-144">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="9c339-144">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="9c339-145">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="9c339-145">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="9c339-146">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="9c339-146">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="9c339-147">若要跳过对 CIDR IP 掩码值/1 到 /23 的垃圾邮件筛选，请参阅 [本主题稍后将为 CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9c339-147">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="9c339-148">若要添加 IP 地址或地址范围，**Add**请单击添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-148">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9c339-149">若要删除某个条目，请在允许 IP 地址 **中选择该条目，** 然后单击 **"删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="9c339-149">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="9c339-150">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c339-150">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="9c339-151">**IP 阻止列表：** 单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="9c339-151">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="9c339-152">如**前文中的"IP**允许列表"设置中所述，在"地址范围"框中输入单个 IP、IP**范围或**CIDR IP。 **IP Allow List**</span><span class="sxs-lookup"><span data-stu-id="9c339-152">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="9c339-153">若要添加 IP 地址或地址范围，**Add**请单击添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9c339-154">若要删除某个条目，请在"阻止的 IP 地址 **"中选择该条目，** 然后单击"删除**Remove** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="9c339-154">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="9c339-155">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c339-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="9c339-156">**打开安全列表**：允许或禁止使用安全列表识别已知的良好发件人，这将导致垃圾邮件筛选跳过。</span><span class="sxs-lookup"><span data-stu-id="9c339-156">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="9c339-157">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c339-157">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="9c339-158">使用安全与&合规中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9c339-158">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="9c339-159">在安全合 &中心内，转到威 **胁** \> **管理** \> **策略反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="9c339-159">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="9c339-160">在" **反垃圾邮件设置"** 页面上，单击名为"连接筛选策略"的默认策略旁 **边的下拉列表**。</span><span class="sxs-lookup"><span data-stu-id="9c339-160">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="9c339-161">策略设置显示在打开的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="9c339-161">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="9c339-162">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9c339-162">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="9c339-163">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9c339-163">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="9c339-164">**注意**：</span><span class="sxs-lookup"><span data-stu-id="9c339-164">**Notes**:</span></span>

- <span data-ttu-id="9c339-165">有效的 IP 地址或地址范围的值包括：</span><span class="sxs-lookup"><span data-stu-id="9c339-165">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="9c339-166">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="9c339-166">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="9c339-167">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="9c339-167">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="9c339-168">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="9c339-168">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="9c339-169">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="9c339-169">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="9c339-170">若要 *用指定的* 值覆盖任何现有条目，请使用以下语法 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` ：</span><span class="sxs-lookup"><span data-stu-id="9c339-170">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="9c339-171">若要 *在不影响* 其他现有条目的情况下添加或删除 IP 地址或地址范围，请使用以下语法 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` ：</span><span class="sxs-lookup"><span data-stu-id="9c339-171">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="9c339-172">若要清空 IP 允许列表或 IP 阻止列表，请使用该值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="9c339-172">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="9c339-173">本示例将使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="9c339-173">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="9c339-174">本示例在 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="9c339-174">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="9c339-175">若要详细了解语法和参数，请参阅["Set-HostedConnectionFilterPolicy"。](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="9c339-175">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9c339-176">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="9c339-176">How do you know this worked?</span></span>

<span data-ttu-id="9c339-177">若要验证是否已成功修改默认连接筛选器策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="9c339-177">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="9c339-178">在安全与合规&中心内，转到 **"威胁管理** \> **策略** \> **反垃圾邮件** \> "，单击 **"连接筛选器策略"和" (始终启用") "** 旁边的下拉列表，然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="9c339-178">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="9c339-179">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令以确认设置：</span><span class="sxs-lookup"><span data-stu-id="9c339-179">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="9c339-180">从 IP 允许列表上的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="9c339-180">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="9c339-181">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="9c339-181">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="9c339-182">下列各节确定了在配置 IP 允许列表时需要了解的其他项目。</span><span class="sxs-lookup"><span data-stu-id="9c339-182">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="9c339-183">跳过可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="9c339-183">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="9c339-184">如本主题前面所述，您只能使用 CIDR IP 和 IP 允许列表中的网络掩码 /24 至 /32。</span><span class="sxs-lookup"><span data-stu-id="9c339-184">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="9c339-185">要跳过从 /1 到 /23 范围内源电子邮件服务器的邮件进行垃圾邮件筛选，需要使用 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-185">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="9c339-186">但是，建议您在所有可能时都不要这样做，因为如果 /1 到 /23 CIDR IP 范围内的 IP 地址在 Microsoft 的任何专有或第三方阻止列表中出现，这些邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="9c339-186">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="9c339-187">至此，已完全认识到潜在的问题，可以使用下列设置 (最少) 创建邮件流规则，以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="9c339-187">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="9c339-188">规则条件 **：如果发件人 IP 地址处于这些**范围内或准确匹配的 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (输入你的 CIDR IP 与 /1 到 /23 网络掩码，则应用此) 规则。</span><span class="sxs-lookup"><span data-stu-id="9c339-188">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="9c339-189">规则操作： **修改邮件** \> \*\*属性" 将垃圾邮件可信度设为s， (SCL) \*\* \> **筛选**。</span><span class="sxs-lookup"><span data-stu-id="9c339-189">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="9c339-190">您可以在特定时间内审核规则、测试规则及激活规则，其他操作会进行审核。</span><span class="sxs-lookup"><span data-stu-id="9c339-190">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="9c339-191">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="9c339-191">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="9c339-192">有关详细信息，请参阅 [在 Exchange Online 中管理邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="9c339-192">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="9c339-193">在来自同一源的选择性电子邮件域上跳过垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="9c339-193">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="9c339-194">通常，向 IP 允许列表添加 IP 地址或地址范围意味着您信任该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="9c339-194">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="9c339-195">但是，如果该源发送来自多个域的电子邮件，并且你希望跳过某些域的垃圾邮件筛选而非其他域，该怎办一点？</span><span class="sxs-lookup"><span data-stu-id="9c339-195">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="9c339-196">您无法将 IP 允许列表与邮件流规则结合使用，但可以结合使用 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="9c339-196">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="9c339-197">例如，源电子邮件服务器 192.168.1.25 发送来自域 contoso.com、fabrikam.com 和 tailspintoys.com 的电子邮件，但您只希望跳过对来自 fabrikam.com 中发件人的邮件进行垃圾邮件筛选的fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="9c339-197">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="9c339-198">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9c339-198">To do this, use the following steps:</span></span>

1. <span data-ttu-id="9c339-199">向 IP 允许列表添加 192.168.1.25。</span><span class="sxs-lookup"><span data-stu-id="9c339-199">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="9c339-200">使用以下设置配置邮件流规则 (此设置) ：</span><span class="sxs-lookup"><span data-stu-id="9c339-200">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="9c339-201">规则条件 **：如果发件人 IP 地址处于这些**范围内，或准确匹配 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (与在上一步) 中的 IP 允许列表中添加的 IP 地址或地址范围相同，则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="9c339-201">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="9c339-202">规则操作：**修改邮件** \> \*\*属性" 设置垃圾邮件可信度 (SCL) \*\* \> **0。**</span><span class="sxs-lookup"><span data-stu-id="9c339-202">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="9c339-203">规则例外 **：发件人** \> **域仅** \> fabrikam.com (您想要跳过垃圾邮件筛选的一个或多个域，) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-203">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="9c339-204">仍将筛选来自 IP 允许列表中的源的邮件的情况</span><span class="sxs-lookup"><span data-stu-id="9c339-204">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="9c339-205">在下列情况下，IP 允许列表中的电子邮件服务器的邮件仍受垃圾邮件筛选约对的约名制约：</span><span class="sxs-lookup"><span data-stu-id="9c339-205">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="9c339-206">IP 允许列表中的 IP 地址也配置为本地的 IP 允许列表中的 IP 地址，可通过*any*Microsoft 365 (中的任何租户的基于 IP 的入站连接器呼叫此租户 A) 、**先遇到**此邮件的租户 A 和 EOP 服务器出现在 Microsoft 数据中心*的同一*个 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="9c339-206">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="9c339-207">在这种情况下 \**，IPV：CAL\*\*\*已添加到*邮件[的反垃圾邮件邮件头](anti-spam-message-headers.md) (以指示邮件绕过垃圾邮件筛选) ，但是邮件仍然受垃圾邮件筛选的约义。</span><span class="sxs-lookup"><span data-stu-id="9c339-207">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="9c339-208">包含 IP 允许列表的租户和先遇到邮件的 EOP 服务器都发生在 Microsoft *数据* 中心的不同 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="9c339-208">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="9c339-209">在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍需进行垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9c339-209">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="9c339-210">如果遇到上述任一情况，可以使用以下设置 (至少 创建邮件流规则) ，以确保有问题的 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="9c339-210">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="9c339-211">规则条件 **：如果发件人**IP 地址处于这些范围内或完全匹配的 (\> **The sender** \> **IP address is in any of these ranges or exactly matches** \> IP 地址或地址表达式，则应用此) 。</span><span class="sxs-lookup"><span data-stu-id="9c339-211">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="9c339-212">规则操作： **修改邮件** \> \*\*属性" 将垃圾邮件可信度设为s， (SCL) \*\* \> **筛选**。</span><span class="sxs-lookup"><span data-stu-id="9c339-212">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="9c339-213">不新增了 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="9c339-213">New to Microsoft 365?</span></span>

|<!-- a -->|
|---|
|<span data-ttu-id="9c339-214">![LinkedIn Learning New 到 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 简短图标？**</span><span class="sxs-lookup"><span data-stu-id="9c339-214">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="9c339-215">发现 LinkedIn Learning **向管理员**和 IT 专业人提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="9c339-215">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
|
