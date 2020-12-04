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
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中配置连接筛选，以允许或阻止来自电子邮件服务器的电子邮件。
ms.openlocfilehash: a2a755516f029f5d72016e9ea8fcb87a997d5065
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572821"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="9fe43-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="9fe43-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9fe43-104">如果您是在 Exchange Online 中使用邮箱的 Microsoft 365 客户或独立 Exchange Online Protection (EOP) 不含 Exchange Online 邮箱的客户，请使用 EOP 中的连接筛选 (具体来说，默认的连接筛选器策略) 以根据其 IP 地址识别好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="9fe43-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="9fe43-105">默认连接筛选器策略的关键组件为：</span><span class="sxs-lookup"><span data-stu-id="9fe43-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="9fe43-106">**IP 允许列表**：跳过来自您通过 ip 地址或 ip 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-106">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="9fe43-107">对于来自这些来源的邮件，可能仍会出现垃圾邮件筛选的情况，请参阅本主题后面的 " [仍在筛选 IP 允许列表中的邮件"](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 部分中的 "来自此来源的邮件" 部分。</span><span class="sxs-lookup"><span data-stu-id="9fe43-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="9fe43-108">有关 IP 允许列表应适合您的整体安全发件人策略的详细信息，请参阅 [在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="9fe43-109">**Ip 阻止列表**：阻止来自您通过 ip 地址或 ip 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="9fe43-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="9fe43-110">传入的邮件将被拒绝，不会被标记为垃圾邮件，并且不会发生其他筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="9fe43-111">有关 IP 阻止列表应适合您的总体阻止发件人策略的详细信息，请参阅 [EOP 中的创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-111">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="9fe43-112">**安全列表**： *安全列表* 是 Microsoft 数据中心中不需要客户配置的动态允许列表。</span><span class="sxs-lookup"><span data-stu-id="9fe43-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="9fe43-113">Microsoft 会将这些受信任的电子邮件源标识为对各种第三方列表的订阅。</span><span class="sxs-lookup"><span data-stu-id="9fe43-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="9fe43-114">启用或禁用安全列表的使用;您不能在安全列表上配置源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="9fe43-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="9fe43-115">从安全列表上的电子邮件服务器传入的邮件中跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="9fe43-116">本主题介绍了如何在 Exchange Online 中使用邮箱在安全 & 合规中心或 PowerShell (Exchange Online PowerShell 中配置默认连接筛选器策略; 在 Exchange Online 中，可使用邮箱来配置 Microsoft 365 组织;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9fe43-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="9fe43-117">有关 EOP 如何使用连接筛选的详细信息，请参阅贵组织的整体反垃圾邮件设置的一部分。请参阅 [反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9fe43-118">IP 允许列表、安全列表和 IP 阻止列表是您在组织中允许或阻止电子邮件的总体策略中的一个部分。</span><span class="sxs-lookup"><span data-stu-id="9fe43-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="9fe43-119">有关详细信息，请参阅 [创建安全发件人列表](create-safe-sender-lists-in-office-365.md) 和 [创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9fe43-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9fe43-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9fe43-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="9fe43-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9fe43-122">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="9fe43-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="9fe43-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9fe43-124">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9fe43-125">您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="9fe43-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9fe43-126">若要修改默认连接筛选器策略，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="9fe43-126">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9fe43-127">若要对默认连接筛选器策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="9fe43-127">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9fe43-128">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="9fe43-129">**注意**：</span><span class="sxs-lookup"><span data-stu-id="9fe43-129">**Notes**:</span></span>

  - <span data-ttu-id="9fe43-130">将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="9fe43-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9fe43-131">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="9fe43-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="9fe43-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9fe43-133">若要查找要允许或阻止的电子邮件服务器 (发件人) 的源 IP 地址，可以检查邮件头中的 "连接 IP (**CIP**) 标头" 字段。</span><span class="sxs-lookup"><span data-stu-id="9fe43-133">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="9fe43-134">若要查看各种电子邮件客户端中的邮件头，请参阅 [在 Outlook 中查看 internet 邮件头](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-134">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="9fe43-135">IP 允许列表的优先级高于 IP 阻止列表 (两个列表上的地址不会被阻止) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-135">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="9fe43-136">每个 IP 允许列表和 IP 阻止列表都支持最多1273个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域间路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="9fe43-136">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="9fe43-137">使用安全 & 合规性中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9fe43-137">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="9fe43-138">在安全 & 合规性中心并转到 **威胁管理** \> **策略** \> **反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="9fe43-138">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="9fe43-139">在 "**反垃圾邮件设置**" 页上，单击 "展开图标"，然后单击 "编辑策略"，展开 "**连接筛选器策略** ![ ](../../media/scc-expand-icon.png) "。 **Edit policy**</span><span class="sxs-lookup"><span data-stu-id="9fe43-139">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="9fe43-140">在出现的 **默认** 浮出控件中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="9fe43-140">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="9fe43-141">**说明**：输入可选的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="9fe43-141">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="9fe43-142">**IP 允许列表**：单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="9fe43-142">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="9fe43-143">在出现的 **IP 允许列表** 浮出控件中，使用以下语法在 " **地址" 或 "地址范围** " 框中输入 IPV4 地址：</span><span class="sxs-lookup"><span data-stu-id="9fe43-143">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="9fe43-144">单个 IP：例如192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="9fe43-144">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="9fe43-145">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="9fe43-145">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="9fe43-146">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="9fe43-146">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="9fe43-147">有效的网络掩码值为/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="9fe43-147">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="9fe43-148">若要跳过 CIDR IP 掩码值/1 到/23 的垃圾邮件筛选，请参阅本主题后面的 " [跳过对 CIDR ip 的垃圾邮件筛选](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) "。在本主题后面的 "可用范围" 部分之外。</span><span class="sxs-lookup"><span data-stu-id="9fe43-148">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="9fe43-149">若要添加 IP 地址或地址范围，请单击 " **添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-149">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9fe43-150">若要删除条目，请选择 " **允许的 IP 地址** " 中的条目，然后单击 " **删除** ![ 删除" ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-150">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="9fe43-151">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="9fe43-151">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="9fe43-152">**IP 阻止列表**：单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="9fe43-152">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="9fe43-153">在出现的 " **IP 阻止列表**" 浮出控件中，按照 **ip 允许列表** 设置中的前面所述，在 "**地址" 或 "地址范围**" 框中输入单个 ip 地址、ip 地址范围或 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="9fe43-153">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="9fe43-154">若要添加 IP 地址或地址范围，请单击 " **添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-154">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9fe43-155">若要删除条目，请选择 " **阻止的 IP 地址** " 中的条目，然后单击 " **删除** ![ 删除" ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-155">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="9fe43-156">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="9fe43-156">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="9fe43-157">**打开安全列表**：启用或禁用安全列表的使用，以确定将跳过垃圾邮件筛选的已知、良好的发件人。</span><span class="sxs-lookup"><span data-stu-id="9fe43-157">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="9fe43-158">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="9fe43-158">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="9fe43-159">使用安全 & 合规性中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9fe43-159">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="9fe43-160">在安全 & 合规性中心并转到 **威胁管理** \> **策略** \> **反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="9fe43-160">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="9fe43-161">在 " **反垃圾邮件设置** " 页上，单击名为 " **连接筛选器策略**" 的默认策略旁边的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="9fe43-161">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="9fe43-162">策略设置显示在打开的下拉菜单中。</span><span class="sxs-lookup"><span data-stu-id="9fe43-162">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="9fe43-163">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="9fe43-163">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="9fe43-164">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="9fe43-164">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="9fe43-165">**注意**：</span><span class="sxs-lookup"><span data-stu-id="9fe43-165">**Notes**:</span></span>

- <span data-ttu-id="9fe43-166">有效的 IP 地址或地址范围值为：</span><span class="sxs-lookup"><span data-stu-id="9fe43-166">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="9fe43-167">单个 IP：例如192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="9fe43-167">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="9fe43-168">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="9fe43-168">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="9fe43-169">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="9fe43-169">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="9fe43-170">有效的网络掩码值为/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="9fe43-170">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="9fe43-171">若要使用您指定的值 *覆盖* 任何现有条目，请使用以下语法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-171">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="9fe43-172">若要在不影响其他现有条目的情况下 *添加或删除* IP 地址或地址范围，请使用以下语法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-172">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="9fe43-173">若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-173">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="9fe43-174">本示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="9fe43-174">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="9fe43-175">本示例将从 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="9fe43-175">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="9fe43-176">有关语法和参数的详细信息，请参阅 [set-hostedconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-176">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9fe43-177">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="9fe43-177">How do you know this worked?</span></span>

<span data-ttu-id="9fe43-178">若要验证是否已成功修改了默认连接筛选器策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="9fe43-178">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="9fe43-179">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略**" \> " **反垃圾邮件**" \> 单击 " **连接筛选器策略** " 旁的下拉 ("始终在) 上"，然后验证这些设置。</span><span class="sxs-lookup"><span data-stu-id="9fe43-179">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="9fe43-180">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="9fe43-180">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="9fe43-181">从 IP 允许列表中的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="9fe43-181">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="9fe43-182">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="9fe43-182">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="9fe43-183">以下各节标识了在配置 IP 允许列表时需要了解的其他项目。</span><span class="sxs-lookup"><span data-stu-id="9fe43-183">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="9fe43-184">跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="9fe43-184">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="9fe43-185">如本主题前面所述，您只能在 IP 允许列表中使用网络掩码为/24 到/32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="9fe43-185">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="9fe43-186">若要在/1 到/23 范围内跳过来自源电子邮件服务器的邮件的垃圾邮件筛选，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="9fe43-186">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="9fe43-187">但是，我们建议您尽可能不要这样做，因为如果 Microsoft 的专用或第三方的阻止列表中显示了/1 到/23 CIDR IP 范围中的 IP 地址，则邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="9fe43-187">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="9fe43-188">现在，您完全了解潜在问题，您可以创建具有以下)  (设置的邮件流规则，以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="9fe43-188">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="9fe43-189">规则条件： **如果** \> **发件人** \> **IP 地址在这些范围中的任何一个或完全匹配**，则应用此规则 \> 。请) 使用带 a/1 到/23 网络掩码的 CIDR IP (。</span><span class="sxs-lookup"><span data-stu-id="9fe43-189">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="9fe43-190">规则操作： **修改邮件属性** \> **设置垃圾邮件可信度级别 (SCL)** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="9fe43-190">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="9fe43-191">您可以审核规则、测试规则、在特定时间段内激活规则，以及进行其他选择。</span><span class="sxs-lookup"><span data-stu-id="9fe43-191">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="9fe43-192">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="9fe43-192">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="9fe43-193">有关详细信息，请参阅 [在 Exchange Online 中管理邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="9fe43-193">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="9fe43-194">跳过来自相同源的选择性电子邮件域的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="9fe43-194">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="9fe43-195">通常情况下，将 IP 地址或地址范围添加到 IP 允许列表意味着您信任来自该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="9fe43-195">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="9fe43-196">但如果该源发送来自多个域的电子邮件，而您想要跳过某些域的垃圾邮件筛选（而不是其他一些域），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="9fe43-196">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="9fe43-197">您不能仅使用 IP 允许列表来执行此操作，但可以结合使用 IP 允许列表和邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="9fe43-197">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="9fe43-198">例如，源电子邮件服务器192.168.1.25 从域 contoso.com、fabrikam.com 和 tailspintoys.com 发送电子邮件，但您只希望跳过来自 fabrikam.com 发件人的邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-198">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="9fe43-199">若要执行此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9fe43-199">To do this, use the following steps:</span></span>

1. <span data-ttu-id="9fe43-200">将192.168.1.25 添加到 IP 允许列表中。</span><span class="sxs-lookup"><span data-stu-id="9fe43-200">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="9fe43-201">将具有下列设置的邮件流规则配置 (至少) ：</span><span class="sxs-lookup"><span data-stu-id="9fe43-201">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="9fe43-202">规则条件： **如果** \> **发件人** \> **IP 地址位于这些范围中的任何一个或完全匹配** 192.168.1.25，则应用此规则 \> 。)  (与您在上一步中添加到 IP 允许列表中的 ip 地址或地址范围相同的 ip 地址或地址范围。</span><span class="sxs-lookup"><span data-stu-id="9fe43-202">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="9fe43-203">规则操作： **修改邮件属性** \> **设置垃圾邮件可信度级别 (SCL)** \> **0**。</span><span class="sxs-lookup"><span data-stu-id="9fe43-203">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="9fe43-204">规则异常： **"发件人**" \> **域为** \> fabrikam.com (仅要跳过垃圾邮件筛选) 的域。</span><span class="sxs-lookup"><span data-stu-id="9fe43-204">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="9fe43-205">来自 IP 允许列表中来源的邮件仍被筛选的情况</span><span class="sxs-lookup"><span data-stu-id="9fe43-205">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="9fe43-206">来自 IP 允许列表中的电子邮件服务器的邮件仍会在以下情况下受到垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="9fe43-206">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="9fe43-207">您的 IP 允许列表中的 IP 地址也是在 Microsoft 365 中 *任何* 租户的本地基于 IP 的入站连接器中配置的 (让我们调用此租户 a) ， **并且** 第一次遇到邮件的租户 a 和 EOP 服务器在 Microsoft 数据中心 *的同一个* Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="9fe43-207">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="9fe43-208">在这种情况下， **IPV： CAL** *将* 添加到邮件的 [反垃圾邮件邮件头](anti-spam-message-headers.md) ， (指示邮件绕过垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-208">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="9fe43-209">包含 IP 允许列表的租户以及首次遇到邮件的 EOP 服务器在 Microsoft 数据中心的 *不同* Active Directory 林中的情况。</span><span class="sxs-lookup"><span data-stu-id="9fe43-209">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="9fe43-210">在这种情况下， **IPV： CAL** *不会* 添加到邮件头中，因此邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="9fe43-210">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="9fe43-211">如果遇到上述任一情况，您都可以创建具有以下设置的邮件流规则 (至少) ，以确保来自有问题的 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="9fe43-211">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="9fe43-212">规则条件： **如果** \> **发件人** \> **IP 地址在任何这些范围中，或者完全匹配** \> (IP 地址或地址) ，则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="9fe43-212">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="9fe43-213">规则操作： **修改邮件属性** \> **设置垃圾邮件可信度级别 (SCL)** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="9fe43-213">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="9fe43-214">Microsoft 365 的新增功能？</span><span class="sxs-lookup"><span data-stu-id="9fe43-214">New to Microsoft 365?</span></span>

****

<span data-ttu-id="9fe43-215">![LinkedIn 学习 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增版到 Microsoft 365** 的简短图标？</span><span class="sxs-lookup"><span data-stu-id="9fe43-215">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="9fe43-216">探索通过 LinkedIn 学习获取的适用于 **Microsoft 365 管理员和 IT 专业人员** 的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="9fe43-216">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
