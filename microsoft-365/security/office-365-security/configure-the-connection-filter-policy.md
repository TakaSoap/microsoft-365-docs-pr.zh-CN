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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 配置连接筛选以允许或阻止来自电子邮件服务器的电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6ec8b4adcdda692ee561f7d50bacf0511642269
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290041"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="34b2b-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="34b2b-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34b2b-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="34b2b-104">**Applies to**</span></span>
- [<span data-ttu-id="34b2b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34b2b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34b2b-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="34b2b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="34b2b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34b2b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


<span data-ttu-id="34b2b-108">如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者是没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，请使用 EOP (中的连接筛选，特别是默认连接筛选器策略) 通过 IP 地址标识好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="34b2b-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="34b2b-109">默认连接筛选器策略的关键组件是：</span><span class="sxs-lookup"><span data-stu-id="34b2b-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="34b2b-110">**IP 允许列表**：跳过通过 IP 地址或 IP 地址范围指定的源电子邮件服务器中所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="34b2b-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="34b2b-111">有关这些源中的邮件仍可能发生垃圾邮件筛选的方案，请参阅本文稍后部分中的" [来自 IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 允许列表中的源的邮件仍然经过筛选的方案"部分。</span><span class="sxs-lookup"><span data-stu-id="34b2b-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="34b2b-112">有关 IP 允许列表如何适合整体安全发件人策略的信息，请参阅[EOP 中的"创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="34b2b-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="34b2b-113">**IP 阻止列表**：阻止来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="34b2b-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="34b2b-114">传入的邮件被拒绝，不会标记为垃圾邮件，并且不会发生其他筛选。</span><span class="sxs-lookup"><span data-stu-id="34b2b-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="34b2b-115">有关 IP 阻止列表如何适合整个阻止发件人策略的信息，请参阅 EOP 中的"创建[阻止发件人列表"。](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="34b2b-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="34b2b-116">**安全列表**： *安全列表是* Microsoft 数据中心中的动态允许列表，不需要客户配置。</span><span class="sxs-lookup"><span data-stu-id="34b2b-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="34b2b-117">Microsoft 从订阅到各种第三方列表标识这些受信任的电子邮件源。</span><span class="sxs-lookup"><span data-stu-id="34b2b-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="34b2b-118">启用或禁用安全列表的使用;无法配置安全列表中的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="34b2b-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="34b2b-119">从安全列表上的电子邮件服务器传入的邮件上跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="34b2b-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="34b2b-120">本主题介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置默认连接筛选器策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-120">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="34b2b-121">有关 EOP 如何使用连接筛选是组织整体反垃圾邮件设置的一部分，请参阅["反垃圾邮件保护"。](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="34b2b-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34b2b-122">IP 允许列表、安全列表和 IP 阻止列表是允许或阻止组织中电子邮件的总体策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="34b2b-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="34b2b-123">有关详细信息，请参阅["创建安全发件人列表"和](create-safe-sender-lists-in-office-365.md)["创建阻止的发件人列表"。](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="34b2b-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="34b2b-124">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="34b2b-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="34b2b-125">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="34b2b-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="34b2b-126">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="34b2b-126">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="34b2b-127">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="34b2b-128">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="34b2b-129">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="34b2b-129">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="34b2b-130">若要修改默认连接筛选器策略，您必须是组织管理或 **安全管理员** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="34b2b-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="34b2b-131">若要对默认连接筛选器策略进行只读访问，你需要是全局阅读器或安全读者 **角色组** 的成员。</span><span class="sxs-lookup"><span data-stu-id="34b2b-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="34b2b-132">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="34b2b-133">**注意**：</span><span class="sxs-lookup"><span data-stu-id="34b2b-133">**Notes**:</span></span>

  - <span data-ttu-id="34b2b-134">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="34b2b-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="34b2b-135">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="34b2b-136">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="34b2b-136">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="34b2b-137">若要查找要允许或阻止的电子邮件服务器 (发件人) 的源 IP 地址，可以检查邮件头中的连接 IP (**CIP**) 头字段。</span><span class="sxs-lookup"><span data-stu-id="34b2b-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="34b2b-138">若要查看各种电子邮件客户端中的邮件头，请参阅 Outlook 中的["查看 Internet 邮件头"。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)</span><span class="sxs-lookup"><span data-stu-id="34b2b-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="34b2b-139">IP 允许列表优先于 IP 阻止列表 (两个列表上的地址不会) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="34b2b-140">IP 允许列表和 IP 阻止列表最多支持 1273 个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域间路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="34b2b-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="34b2b-141">使用安全&合规中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b2b-141">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="34b2b-142">在安全&合规中心，转到 **"威胁管理** \> **策略** \> **反垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-142">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="34b2b-143">在 **"反垃圾邮件设置"页上**，通过单击"展开"图标展开"连接筛选器策略"， ![ ](../../media/scc-expand-icon.png) 然后单击"**编辑策略"。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-143">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="34b2b-144">在 **出现的"** 默认"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="34b2b-144">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="34b2b-145">**说明**：输入可选的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="34b2b-145">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="34b2b-146">**IP 允许列表**：单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-146">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="34b2b-147">在 **出现的 IP 允许列表** 飞出框中，使用以下语法在地址 **或地址** 范围框中输入 IPV4 地址：</span><span class="sxs-lookup"><span data-stu-id="34b2b-147">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="34b2b-148">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="34b2b-148">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="34b2b-149">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="34b2b-149">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="34b2b-150">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="34b2b-150">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="34b2b-151">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="34b2b-151">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="34b2b-152">若要将 CIDR IP 掩码值 /1 的垃圾邮件筛选跳过到 /23，请参阅本文稍后部分之外的 [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="34b2b-152">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

     <span data-ttu-id="34b2b-153">若要添加 IP 地址或地址范围，请单击 **"添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="34b2b-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="34b2b-154">若要删除条目，请选择"允许的 **IP** 地址"中的条目，然后单击" **删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="34b2b-154">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="34b2b-155">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34b2b-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="34b2b-156">**IP 阻止列表**：单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-156">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="34b2b-157">在 **出现的 IP 阻止列表** 飞出框中，在"地址或地址范围"框中输入单个 IP、IP 范围或 CIDR IP，如 **前面 IP** 允许列表设置中所述。 </span><span class="sxs-lookup"><span data-stu-id="34b2b-157">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="34b2b-158">若要添加 IP 地址或地址范围，请单击 **"添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="34b2b-158">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="34b2b-159">若要删除条目，请选择"阻止的 **IP** 地址"中的条目，然后单击" **删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="34b2b-159">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="34b2b-160">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34b2b-160">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="34b2b-161">**打开安全列表**：启用或禁用安全列表，以标识将跳过垃圾邮件筛选的已知良好发件人。</span><span class="sxs-lookup"><span data-stu-id="34b2b-161">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="34b2b-162">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="34b2b-162">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="34b2b-163">使用安全&合规中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b2b-163">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="34b2b-164">在安全&合规中心，转到 **"威胁管理** \> **策略** \> **反垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-164">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="34b2b-165">在 **"反垃圾邮件设置** "页上，单击名为"连接筛选器策略"的默认策略 **旁边的下拉列表**。</span><span class="sxs-lookup"><span data-stu-id="34b2b-165">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="34b2b-166">策略设置显示在打开的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="34b2b-166">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="34b2b-167">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b2b-167">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="34b2b-168">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="34b2b-168">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="34b2b-169">**注意**：</span><span class="sxs-lookup"><span data-stu-id="34b2b-169">**Notes**:</span></span>

- <span data-ttu-id="34b2b-170">有效的 IP 地址或地址范围值为：</span><span class="sxs-lookup"><span data-stu-id="34b2b-170">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="34b2b-171">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="34b2b-171">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="34b2b-172">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="34b2b-172">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="34b2b-173">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="34b2b-173">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="34b2b-174">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="34b2b-174">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="34b2b-175">若要 *用* 您指定的值覆盖任何现有条目，请使用以下 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 语法：</span><span class="sxs-lookup"><span data-stu-id="34b2b-175">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="34b2b-176">若要 *在不影响* 其他现有条目的情况下添加或删除 IP 地址或地址范围，请使用以下 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 语法：</span><span class="sxs-lookup"><span data-stu-id="34b2b-176">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="34b2b-177">若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-177">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="34b2b-178">此示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="34b2b-178">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="34b2b-179">此示例从 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="34b2b-179">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="34b2b-180">有关语法和参数的详细信息，请参阅 [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-180">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="34b2b-181">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="34b2b-181">How do you know this worked?</span></span>

<span data-ttu-id="34b2b-182">若要验证是否成功修改了默认连接筛选器策略，请执行下列任何步骤：</span><span class="sxs-lookup"><span data-stu-id="34b2b-182">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="34b2b-183">在安全&合规中心，转到"威胁管理策略反垃圾邮件"，单击"连接筛选器策略 ("旁边的下拉列表 \>  \>  \> **) 验证** 设置。</span><span class="sxs-lookup"><span data-stu-id="34b2b-183">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="34b2b-184">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="34b2b-184">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="34b2b-185">从 IP 允许列表上的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="34b2b-185">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="34b2b-186">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="34b2b-186">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="34b2b-187">以下各节确定了配置 IP 允许列表时需要知道的其他项目。</span><span class="sxs-lookup"><span data-stu-id="34b2b-187">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="34b2b-188">跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="34b2b-188">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="34b2b-189">如本文前面所述，只能在 IP 允许列表中使用具有网络掩码 /24 到 /32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="34b2b-189">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="34b2b-190">若要跳过对来自 /1 范围内源电子邮件服务器的邮件进行垃圾邮件筛选到 /23 范围，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-190">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="34b2b-191">但是，我们建议你尽可能不要这样做，因为如果 /1 到 /23 CIDR IP 范围中的 IP 地址出现在任何 Microsoft 专有或第三方阻止列表中，邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="34b2b-191">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="34b2b-192">现在，已完全了解潜在问题，您至少可以使用以下设置 (创建一个邮件流规则) 以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="34b2b-192">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="34b2b-193">规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与输入的 CIDR IP 完全匹配 (则应用此规则，并输入 \>  \>  \> /1 到 /23 网络掩码) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-193">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="34b2b-194">规则操作 **：修改邮件属性** 设置垃圾邮件可信度 \> **(SCL)** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="34b2b-194">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="34b2b-195">可以审核规则、测试规则、激活特定时间段的规则和其他选择。</span><span class="sxs-lookup"><span data-stu-id="34b2b-195">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="34b2b-196">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="34b2b-196">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="34b2b-197">有关详细信息，请参阅管理 [Exchange Online 中的邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="34b2b-197">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="34b2b-198">跳过来自同一源的选择性电子邮件域的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="34b2b-198">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="34b2b-199">通常，将 IP 地址或地址范围添加到 IP 允许列表意味着信任来自该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="34b2b-199">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="34b2b-200">但是，如果该源从多个域发送电子邮件，并且您希望跳过其中一些域（而非其他域）的垃圾邮件筛选，那又如何呢？</span><span class="sxs-lookup"><span data-stu-id="34b2b-200">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="34b2b-201">不能单独使用 IP 允许列表来这样做，但可以将 IP 允许列表与邮件流规则结合使用。</span><span class="sxs-lookup"><span data-stu-id="34b2b-201">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="34b2b-202">例如，源电子邮件服务器 192.168.1.25 从 contoso.com、fabrikam.com 和 tailspintoys.com 域发送电子邮件，但您只想跳过对 fabrikam.com 中发件人的邮件进行垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="34b2b-202">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="34b2b-203">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="34b2b-203">To do this, use the following steps:</span></span>

1. <span data-ttu-id="34b2b-204">将 192.168.1.25 添加到 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="34b2b-204">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="34b2b-205">配置邮件流规则，并至少 (以下) ：</span><span class="sxs-lookup"><span data-stu-id="34b2b-205">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="34b2b-206">规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与 \>  \> 192.168.1.25 (与在上一步骤) 中添加到 IP 允许列表的相同 IP 地址或地址范围匹配，则应用 \> 此规则。</span><span class="sxs-lookup"><span data-stu-id="34b2b-206">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="34b2b-207">规则操作 **：修改邮件属性** \> **将垃圾邮件可信度设置为 (SCL)** \> **0。**</span><span class="sxs-lookup"><span data-stu-id="34b2b-207">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="34b2b-208">规则例外： **发件人** \> **域fabrikam.com (** 要跳过垃圾邮件筛选的域或 \>) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-208">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="34b2b-209">仍筛选来自 IP 允许列表中的源的邮件的方案</span><span class="sxs-lookup"><span data-stu-id="34b2b-209">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="34b2b-210">在下列情况下，来自 IP 允许列表中的电子邮件服务器的邮件仍受垃圾邮件筛选限制：</span><span class="sxs-lookup"><span data-stu-id="34b2b-210">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="34b2b-211">IP 允许列表中的 IP 地址也在 Microsoft 365 (任何租户中的基于IP 的本地入站连接器中配置 (让我们调用此租户 A) ，第一次遇到邮件的租户 A 和 EOP 服务器正好位于 Microsoft 数据中心中的同一 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="34b2b-211">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="34b2b-212">在此方案中 **，IPV：CAL** 将添加到邮件的反垃圾邮件邮件头 [ (](anti-spam-message-headers.md)指示邮件绕过了垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="34b2b-212">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="34b2b-213">包含 IP 允许列表的租户和首次遇到邮件的 EOP 服务器都发生在 Microsoft 数据中心的不同 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="34b2b-213">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="34b2b-214">在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="34b2b-214">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="34b2b-215">如果遇到上述任一情况，可以创建至少 (设置的邮件流规则) 以确保有问题的 IP 地址中的邮件跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="34b2b-215">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="34b2b-216">规则条件：**如果** 发件人 IP 地址位于以下任一范围内或与你的 IP 地址 (完全匹配，则应用此 \>  \>  \>) 。</span><span class="sxs-lookup"><span data-stu-id="34b2b-216">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="34b2b-217">规则操作 **：修改邮件属性** 设置垃圾邮件可信度 \> **(SCL)** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="34b2b-217">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="34b2b-218">是 Microsoft 365 的新增功能？</span><span class="sxs-lookup"><span data-stu-id="34b2b-218">New to Microsoft 365?</span></span>

****

<span data-ttu-id="34b2b-219">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **到 Microsoft 365** 的简短图标</span><span class="sxs-lookup"><span data-stu-id="34b2b-219">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="34b2b-220">发现 LinkedIn Learning 为 **Microsoft 365** 管理员和 IT 专业人员提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="34b2b-220">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
