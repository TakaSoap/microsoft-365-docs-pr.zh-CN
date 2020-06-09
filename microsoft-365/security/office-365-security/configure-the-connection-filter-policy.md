---
title: 配置默认连接筛选器策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online Protection （EOP）中配置连接筛选，以允许或阻止来自电子邮件服务器的电子邮件。
ms.openlocfilehash: 14758161f827cf231a8f3a0415748c7a2dd5981f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616586"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="bf001-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="bf001-103">Configure connection filtering</span></span>

<span data-ttu-id="bf001-104">如果您是 Exchange Online 邮箱或独立 Exchange Online Protection （EOP）客户（没有 Exchange Online 邮箱）的 Microsoft 365 客户，则可以使用 EOP 中的连接筛选（具体来说是默认的连接筛选器策略），以根据其 IP 地址识别好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="bf001-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="bf001-105">默认连接筛选器策略的关键组件为：</span><span class="sxs-lookup"><span data-stu-id="bf001-105">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="bf001-106">**IP 允许列表**：跳过来自您通过 ip 地址或 ip 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-106">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="bf001-107">对于来自这些来源的邮件，可能仍会出现垃圾邮件筛选的情况，请参阅本主题后面的 "[仍在筛选 IP 允许列表中的邮件"](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered)部分中的 "来自此来源的邮件" 部分。</span><span class="sxs-lookup"><span data-stu-id="bf001-107">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this topic.</span></span> <span data-ttu-id="bf001-108">有关 IP 允许列表应适合您的整体安全发件人策略的详细信息，请参阅[在 EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bf001-108">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="bf001-109">**Ip 阻止列表**：阻止来自您通过 ip 地址或 ip 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="bf001-109">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="bf001-110">传入的邮件将被拒绝，不会被标记为垃圾邮件，并且不会发生其他筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-110">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="bf001-111">有关 IP 阻止列表应适合您的总体阻止发件人策略的详细信息，请参阅[EOP 中的创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bf001-111">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="bf001-112">**安全列表**：*安全列表*是 Microsoft 数据中心中不需要客户配置的动态允许列表。</span><span class="sxs-lookup"><span data-stu-id="bf001-112">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="bf001-113">Microsoft 会将这些受信任的电子邮件源标识为对各种第三方列表的订阅。</span><span class="sxs-lookup"><span data-stu-id="bf001-113">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="bf001-114">启用或禁用安全列表的使用;您不能在安全列表上配置源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="bf001-114">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="bf001-115">从安全列表上的电子邮件服务器传入的邮件中跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-115">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="bf001-116">本主题介绍如何在安全 & 合规性中心或 PowerShell （Exchange Online PowerShell for Microsoft 365 组织中使用邮箱在 Exchange Online 中配置默认连接筛选器策略; 独立 EOP PowerShell for 组织，无 Exchange Online 邮箱）。</span><span class="sxs-lookup"><span data-stu-id="bf001-116">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="bf001-117">有关 EOP 如何使用连接筛选的详细信息，请参阅贵组织的整体反垃圾邮件设置的一部分。请参阅[反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="bf001-117">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bf001-118">IP 允许列表、安全列表和 IP 阻止列表是您在组织中允许或阻止电子邮件的总体策略中的一个部分。</span><span class="sxs-lookup"><span data-stu-id="bf001-118">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="bf001-119">有关详细信息，请参阅[创建安全发件人列表](create-safe-sender-lists-in-office-365.md)和[创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="bf001-119">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bf001-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bf001-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bf001-121">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="bf001-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bf001-122">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="bf001-122">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="bf001-123">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bf001-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bf001-124">若要连接到独立的 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bf001-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bf001-125">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="bf001-125">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="bf001-126">若要修改默认连接筛选器策略，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="bf001-126">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="bf001-127">若要对默认连接筛选器策略进行只读访问，您需要是**安全读者**角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="bf001-127">For read-only access to the default connection filter policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="bf001-128">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bf001-128">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="bf001-129">若要查找您想要允许或阻止的电子邮件服务器（发件人）的源 IP 地址，可以检查邮件头中的连接 IP （**CIP**）头字段。</span><span class="sxs-lookup"><span data-stu-id="bf001-129">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="bf001-130">若要查看各种电子邮件客户端中的邮件头，请参阅[在 Outlook 中查看 internet 邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="bf001-130">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="bf001-131">IP 允许列表的优先级高于 IP 阻止列表（两个列表中的地址不被阻止）。</span><span class="sxs-lookup"><span data-stu-id="bf001-131">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="bf001-132">每个 IP 允许列表和 IP 阻止列表都支持最多1273个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域间路由（CIDR） IP。</span><span class="sxs-lookup"><span data-stu-id="bf001-132">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="bf001-133">使用安全 & 合规性中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="bf001-133">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="bf001-134">在安全 & 合规性中心并转到**威胁管理** \> **策略** \> **反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="bf001-134">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="bf001-135">在 "**反垃圾邮件设置**" 页上，单击 "展开图标"，然后单击 "编辑策略"，展开 "**连接筛选器策略** ![ ](../../media/scc-expand-icon.png) "。 **Edit policy**</span><span class="sxs-lookup"><span data-stu-id="bf001-135">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="bf001-136">在出现的**默认**浮出控件中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="bf001-136">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="bf001-137">**说明**：输入可选的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="bf001-137">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="bf001-138">**IP 允许列表**：单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bf001-138">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="bf001-139">在出现的**IP 允许列表**浮出控件中，使用以下语法在 "**地址" 或 "地址范围**" 框中输入 IPV4 地址：</span><span class="sxs-lookup"><span data-stu-id="bf001-139">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="bf001-140">单个 IP：例如192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="bf001-140">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="bf001-141">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="bf001-141">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="bf001-142">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="bf001-142">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="bf001-143">有效的网络掩码值为/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="bf001-143">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="bf001-144">若要跳过 CIDR IP 掩码值/1 到/23 的垃圾邮件筛选，请参阅本主题后面的 "[跳过对 CIDR ip 的垃圾邮件筛选](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range)"。在本主题后面的 "可用范围" 部分之外。</span><span class="sxs-lookup"><span data-stu-id="bf001-144">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this topic.</span></span>

     <span data-ttu-id="bf001-145">若要添加 IP 地址或地址范围，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bf001-145">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="bf001-146">若要删除条目，请选择 "**允许的 IP 地址**" 中的条目，然后单击 "**删除** ![ 删除" ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bf001-146">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="bf001-147">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf001-147">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="bf001-148">**IP 阻止列表**：单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="bf001-148">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="bf001-149">在出现的 " **IP 阻止列表**" 浮出控件中，按照**ip 允许列表**设置中的前面所述，在 "**地址" 或 "地址范围**" 框中输入单个 ip 地址、ip 地址范围或 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="bf001-149">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="bf001-150">若要添加 IP 地址或地址范围，请单击 "**添加** ![ 添加图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bf001-150">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="bf001-151">若要删除条目，请选择 "**阻止的 IP 地址**" 中的条目，然后单击 "**删除** ![ 删除" ](../../media/scc-remove-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="bf001-151">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="bf001-152">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf001-152">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="bf001-153">**打开安全列表**：启用或禁用安全列表的使用，以确定将跳过垃圾邮件筛选的已知、良好的发件人。</span><span class="sxs-lookup"><span data-stu-id="bf001-153">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="bf001-154">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bf001-154">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="bf001-155">使用安全 & 合规性中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="bf001-155">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="bf001-156">在安全 & 合规性中心并转到**威胁管理** \> **策略** \> **反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="bf001-156">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="bf001-157">在 "**反垃圾邮件设置**" 页上，单击名为 "**连接筛选器策略**" 的默认策略旁边的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="bf001-157">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="bf001-158">策略设置显示在打开的下拉菜单中。</span><span class="sxs-lookup"><span data-stu-id="bf001-158">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="bf001-159">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="bf001-159">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="bf001-160">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bf001-160">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="bf001-161">**注意**：</span><span class="sxs-lookup"><span data-stu-id="bf001-161">**Notes**:</span></span>

- <span data-ttu-id="bf001-162">有效的 IP 地址或地址范围值为：</span><span class="sxs-lookup"><span data-stu-id="bf001-162">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="bf001-163">单个 IP：例如192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="bf001-163">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="bf001-164">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="bf001-164">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="bf001-165">CIDR IP：例如 192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="bf001-165">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="bf001-166">有效的网络掩码值为/24 到/32。</span><span class="sxs-lookup"><span data-stu-id="bf001-166">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="bf001-167">若要使用您指定的值*覆盖*任何现有条目，请使用以下语法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="bf001-167">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="bf001-168">若要在不影响其他现有条目的情况下*添加或删除*IP 地址或地址范围，请使用以下语法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="bf001-168">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="bf001-169">若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="bf001-169">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="bf001-170">本示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="bf001-170">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="bf001-171">本示例将从 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="bf001-171">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="bf001-172">有关语法和参数的详细信息，请参阅[set-hostedconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bf001-172">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bf001-173">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="bf001-173">How do you know this worked?</span></span>

<span data-ttu-id="bf001-174">若要验证是否已成功修改了默认连接筛选器策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="bf001-174">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="bf001-175">在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **反垃圾邮件**"。 \> 单击 "**连接筛选器策略（始终打开**）" 旁边的下拉箭头，并验证设置。</span><span class="sxs-lookup"><span data-stu-id="bf001-175">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="bf001-176">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="bf001-176">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="bf001-177">从 IP 允许列表中的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="bf001-177">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="bf001-178">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="bf001-178">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="bf001-179">以下各节标识了在配置 IP 允许列表时需要了解的其他项目。</span><span class="sxs-lookup"><span data-stu-id="bf001-179">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="bf001-180">跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="bf001-180">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="bf001-181">如本主题前面所述，您只能在 IP 允许列表中使用网络掩码为/24 到/32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="bf001-181">As described earlier in this topic, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="bf001-182">若要在/1 到/23 范围内跳过来自源电子邮件服务器的邮件的垃圾邮件筛选，您需要使用 Exchange 邮件流规则（也称为传输规则）。</span><span class="sxs-lookup"><span data-stu-id="bf001-182">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="bf001-183">但是，我们建议您尽可能不要这样做，因为如果 Microsoft 的专用或第三方的阻止列表中显示了/1 到/23 CIDR IP 范围中的 IP 地址，则邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="bf001-183">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="bf001-184">现在，您完全了解潜在问题，您可以创建具有以下设置的邮件流规则（至少），以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="bf001-184">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="bf001-185">规则条件：**如果** \> **发件人** \> **IP 地址在这些范围中的任何范围或完全匹配** \> （请输入带 a/1 to/23 网络掩码的 CIDR IP），则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="bf001-185">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="bf001-186">规则操作：**修改邮件属性** \> **设置垃圾邮件信任级别（SCL）** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="bf001-186">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="bf001-187">您可以审核规则、测试规则、在特定时间段内激活规则，以及进行其他选择。</span><span class="sxs-lookup"><span data-stu-id="bf001-187">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="bf001-188">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="bf001-188">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="bf001-189">有关详细信息，请参阅[在 Exchange Online 中管理邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="bf001-189">For more information, see [Manage mail flow rules in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="bf001-190">跳过来自相同源的选择性电子邮件域的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="bf001-190">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="bf001-191">通常情况下，将 IP 地址或地址范围添加到 IP 允许列表意味着您信任来自该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="bf001-191">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="bf001-192">但如果该源发送来自多个域的电子邮件，而您想要跳过某些域的垃圾邮件筛选（而不是其他一些域），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="bf001-192">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="bf001-193">您不能仅使用 IP 允许列表来执行此操作，但可以结合使用 IP 允许列表和邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="bf001-193">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="bf001-194">例如，源电子邮件服务器192.168.1.25 从域 contoso.com、fabrikam.com 和 tailspintoys.com 发送电子邮件，但您只希望跳过来自 fabrikam.com 发件人的邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-194">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="bf001-195">若要执行此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bf001-195">To do this, use the following steps:</span></span>

1. <span data-ttu-id="bf001-196">将192.168.1.25 添加到 IP 允许列表中。</span><span class="sxs-lookup"><span data-stu-id="bf001-196">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="bf001-197">使用以下设置配置邮件流规则（至少）：</span><span class="sxs-lookup"><span data-stu-id="bf001-197">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="bf001-198">规则条件：**如果** \> **发件人** \> **IP 地址位于这些范围中的任何范围或完全匹配** \> 192.168.1.25 （在上一步中添加到 ip 允许列表中的相同 IP 地址或地址范围），则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="bf001-198">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="bf001-199">规则操作：**修改邮件属性** \> **设置垃圾邮件可信度（SCL）** \> **0**。</span><span class="sxs-lookup"><span data-stu-id="bf001-199">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="bf001-200">规则异常： **"发件人**" \> **域为** \> fabrikam.com （仅要跳过垃圾邮件筛选的域或域）。</span><span class="sxs-lookup"><span data-stu-id="bf001-200">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="bf001-201">来自 IP 允许列表中来源的邮件仍被筛选的情况</span><span class="sxs-lookup"><span data-stu-id="bf001-201">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="bf001-202">来自 IP 允许列表中的电子邮件服务器的邮件仍会在以下情况下受到垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="bf001-202">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="bf001-203">您的 IP 允许列表中的 IP 地址也在 Microsoft 365 中*任何*租户的本地基于 IP 的入站连接器中进行配置（我们可调用此租户 a）**和**租户 A 以及第一次遇到邮件的 EOP 服务器在 microsoft 数据中心中*的同*一个 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="bf001-203">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="bf001-204">在这种情况下， **IPV： CAL** *将*添加到邮件的[反垃圾邮件邮件头](anti-spam-message-headers.md)（指示邮件绕过垃圾邮件筛选），但邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-204">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="bf001-205">包含 IP 允许列表的租户以及首次遇到邮件的 EOP 服务器在 Microsoft 数据中心的*不同*Active Directory 林中的情况。</span><span class="sxs-lookup"><span data-stu-id="bf001-205">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="bf001-206">在这种情况下， **IPV： CAL** *不会*添加到邮件头中，因此邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="bf001-206">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="bf001-207">如果遇到上述任一情况，您都可以创建具有以下设置的邮件流规则（至少），以确保来自有问题的 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="bf001-207">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="bf001-208">规则条件：**如果** \> **发件人** \> **IP 地址为任意一种范围或完全匹配** \> （IP 地址或地址），则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="bf001-208">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="bf001-209">规则操作：**修改邮件属性** \> **设置垃圾邮件信任级别（SCL）** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="bf001-209">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="bf001-210">Microsoft 365 的新增功能？</span><span class="sxs-lookup"><span data-stu-id="bf001-210">New to Microsoft 365?</span></span>

||
|:-----|
|<span data-ttu-id="bf001-211">![LinkedIn 学习 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增版到 Microsoft 365**的简短图标？</span><span class="sxs-lookup"><span data-stu-id="bf001-211">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="bf001-212">探索通过 LinkedIn 学习为你提供的**管理员和 IT 专业人员**的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="bf001-212">Discover free video courses for **Admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
