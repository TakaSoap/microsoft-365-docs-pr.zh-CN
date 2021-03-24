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
ms.openlocfilehash: 2b940aadb4ff5f2c4676ac2411ea3e95a25c7855
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055733"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="a0f57-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="a0f57-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a0f57-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a0f57-104">**Applies to**</span></span>
- [<span data-ttu-id="a0f57-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a0f57-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a0f57-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a0f57-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a0f57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0f57-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="a0f57-108">如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，请使用 EOP (中的连接筛选，特别是默认连接筛选器策略) 通过 IP 地址标识好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="a0f57-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="a0f57-109">默认连接筛选器策略的主要组件包括：</span><span class="sxs-lookup"><span data-stu-id="a0f57-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="a0f57-110">**IP 允许列表**：跳过对来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="a0f57-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="a0f57-111">有关这些来源的邮件仍可能发生垃圾邮件筛选的方案，请参阅本文稍后介绍的从 [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 允许列表来源筛选邮件的方案部分。</span><span class="sxs-lookup"><span data-stu-id="a0f57-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="a0f57-112">有关 IP 允许列表如何适合整体安全发件人策略的信息，请参阅在 EOP 中创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="a0f57-113">**IP 阻止列表**：阻止来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="a0f57-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="a0f57-114">传入的邮件被拒绝，不会标记为垃圾邮件，并且不会进行其他筛选。</span><span class="sxs-lookup"><span data-stu-id="a0f57-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="a0f57-115">有关 IP 阻止列表如何适合整体阻止的发件人策略，请参阅在 EOP 中创建 [阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="a0f57-116">\**安全列表\*\*\*：安全列表是* Microsoft 数据中心中的动态允许列表，无需客户配置。</span><span class="sxs-lookup"><span data-stu-id="a0f57-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="a0f57-117">Microsoft 从订阅到各种第三方列表标识这些受信任的电子邮件源。</span><span class="sxs-lookup"><span data-stu-id="a0f57-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="a0f57-118">启用或禁用安全列表的使用;无法配置安全列表上的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="a0f57-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="a0f57-119">对来自安全列表上的电子邮件服务器的传入邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="a0f57-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="a0f57-120">本主题介绍如何在安全 & 合规中心或在 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置默认连接筛选器策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-120">This topic describes how to configure the default connection filter policy in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="a0f57-121">有关 EOP 如何使用连接筛选是组织整体反垃圾邮件设置的一部分，请参阅 [反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a0f57-122">IP 允许列表、安全列表和 IP 阻止列表是允许或阻止组织中电子邮件的总体策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="a0f57-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="a0f57-123">有关详细信息，请参阅创建[安全发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a0f57-124">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a0f57-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a0f57-125">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="a0f57-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a0f57-126">若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="a0f57-126">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="a0f57-127">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a0f57-128">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a0f57-129">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="a0f57-129">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a0f57-130">若要修改默认连接筛选器策略，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="a0f57-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a0f57-131">若要对默认连接筛选器策略进行只读访问，您需要是全局读取 **者** 角色组或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a0f57-132">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-132">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="a0f57-133">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a0f57-133">**Notes**:</span></span>

  - <span data-ttu-id="a0f57-134">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="a0f57-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a0f57-135">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="a0f57-136">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a0f57-136">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a0f57-137">若要查找要允许或阻止的电子邮件服务器的源 IP 地址 (发件人) ，可以检查邮件头中的连接 IP (**CIP**) 头字段。</span><span class="sxs-lookup"><span data-stu-id="a0f57-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="a0f57-138">若要查看各种电子邮件客户端中的邮件头，请参阅在 [Outlook 中查看 Internet 邮件头](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="a0f57-139">IP 允许列表优先于 IP 阻止列表 (两个列表上的地址不会) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="a0f57-140">IP 允许列表和 IP 阻止列表最多支持 1273 个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域际路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="a0f57-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="a0f57-141">使用安全&合规中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="a0f57-141">Use the Security & Compliance Center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="a0f57-142">在安全&中心，转到"**威胁管理** \> **策略** \> **""反垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-142">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="a0f57-143">在"**反垃圾邮件设置"页上**，展开"**连接筛选器** 策略"，方法是单击"展开 ![ "图标， ](../../media/scc-expand-icon.png) 然后单击"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-143">On the **Anti-spam settings** page, expand **Connection filter policy** by clicking ![Expand icon](../../media/scc-expand-icon.png), and then click **Edit policy**.</span></span>

3. <span data-ttu-id="a0f57-144">在出现的 **"** 默认"飞出中，配置以下任一设置：</span><span class="sxs-lookup"><span data-stu-id="a0f57-144">In the **Default** flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="a0f57-145">**说明**：输入可选的描述性文本。</span><span class="sxs-lookup"><span data-stu-id="a0f57-145">**Description**: Enter optional descriptive text.</span></span>

   - <span data-ttu-id="a0f57-146">**IP 允许列表：单击**"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-146">**IP Allow List**: Click **Edit**.</span></span> <span data-ttu-id="a0f57-147">在出现的 **"IP 允许列表**"飞出框中，使用以下语法在"地址或地址范围"框中输入 IPV4 地址：</span><span class="sxs-lookup"><span data-stu-id="a0f57-147">In the **IP Allow List** flyout that appears, enter an IPV4 address in the **Address or address range** box using the following syntax:</span></span>

     - <span data-ttu-id="a0f57-148">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="a0f57-148">Single IP: For example, 192.168.1.1.</span></span>

     - <span data-ttu-id="a0f57-149">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="a0f57-149">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

     - <span data-ttu-id="a0f57-150">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="a0f57-150">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="a0f57-151">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="a0f57-151">Valid network mask values are /24 through /32.</span></span> <span data-ttu-id="a0f57-152">若要将 CIDR IP 掩码值 /1 的垃圾邮件筛选跳过为 /23，请参阅本文稍后在可用范围外跳过 [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 的垃圾邮件筛选部分。</span><span class="sxs-lookup"><span data-stu-id="a0f57-152">To skip spam filtering for CIDR IP mask values /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

     <span data-ttu-id="a0f57-153">若要添加 IP 地址或地址范围，请单击" **添加添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="a0f57-153">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="a0f57-154">若要删除条目，请选择"允许的 **IP** 地址"中的条目，然后单击" **删除""删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="a0f57-154">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="a0f57-155">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a0f57-155">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="a0f57-156">**IP 阻止列表：** 单击"**编辑"。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-156">**IP Block List**: Click **Edit**.</span></span> <span data-ttu-id="a0f57-157">在出现的 **"IP 阻止列表**"飞出框中，在"地址或地址范围"框中输入单个 IP、IP 范围或 CIDR IP，如 **前面"IP 允许列表"设置** 中所述。 </span><span class="sxs-lookup"><span data-stu-id="a0f57-157">In the **IP Block List** flyout that appears, enter a single IP, IP range, or CIDR IP in the **Address or address range** box as previously described in the **IP Allow List** setting.</span></span>

     <span data-ttu-id="a0f57-158">若要添加 IP 地址或地址范围，请单击" **添加添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。</span><span class="sxs-lookup"><span data-stu-id="a0f57-158">To add the IP address or address range, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="a0f57-159">若要删除条目，请选择"阻止的 **IP** 地址"中的条目，然后单击" **删除""删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="a0f57-159">To remove an entry, select the entry in **Blocked IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="a0f57-160">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a0f57-160">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="a0f57-161">**打开安全列表**：启用或禁用安全列表，以标识将跳过垃圾邮件筛选的已知、良好的发件人。</span><span class="sxs-lookup"><span data-stu-id="a0f57-161">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span>

4. <span data-ttu-id="a0f57-162">完成后，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="a0f57-162">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="a0f57-163">使用安全&中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="a0f57-163">Use the Security & Compliance Center to view the default connection filter policy</span></span>

1. <span data-ttu-id="a0f57-164">在安全&中心，转到"**威胁管理** \> **策略** \> **""反垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-164">In the Security & Compliance Center and go to **Threat management** \> **Policy** \> **Anti-Spam**.</span></span>

2. <span data-ttu-id="a0f57-165">在 **"反垃圾邮件设置"** 页上，单击名为"连接筛选器策略"的默认策略 **旁边的下拉列表**。</span><span class="sxs-lookup"><span data-stu-id="a0f57-165">On the **Anti-spam settings** page, click the drop down next to the default policy named **Connection filter policy**.</span></span>

3. <span data-ttu-id="a0f57-166">策略设置显示在打开的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="a0f57-166">The policy settings are displayed in the drop down that opens.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="a0f57-167">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="a0f57-167">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="a0f57-168">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0f57-168">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="a0f57-169">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a0f57-169">**Notes**:</span></span>

- <span data-ttu-id="a0f57-170">有效的 IP 地址或地址范围值为：</span><span class="sxs-lookup"><span data-stu-id="a0f57-170">Valid IP address or address range values are:</span></span>

  - <span data-ttu-id="a0f57-171">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="a0f57-171">Single IP: For example, 192.168.1.1.</span></span>

  - <span data-ttu-id="a0f57-172">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="a0f57-172">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>

  - <span data-ttu-id="a0f57-173">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="a0f57-173">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="a0f57-174">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="a0f57-174">Valid network mask values are /24 through /32.</span></span>

- <span data-ttu-id="a0f57-175">若要 *使用* 指定的值覆盖任何现有条目，请使用以下语法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-175">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>

- <span data-ttu-id="a0f57-176">若要 *添加或删除* IP 地址或地址范围而不影响其他现有条目，请使用以下语法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-176">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>

- <span data-ttu-id="a0f57-177">若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-177">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="a0f57-178">此示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="a0f57-178">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="a0f57-179">此示例在 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="a0f57-179">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="a0f57-180">有关语法和参数的详细信息，请参阅 [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-180">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a0f57-181">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="a0f57-181">How do you know this worked?</span></span>

<span data-ttu-id="a0f57-182">若要验证是否成功修改了默认连接筛选器策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="a0f57-182">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="a0f57-183">在安全&合规中心，转到"威胁管理策略""反垃圾邮件"，单击"连接筛选器策略""始终打开 (旁边的下拉列表) 验证 \>  \>  \> 设置。 </span><span class="sxs-lookup"><span data-stu-id="a0f57-183">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-Spam** \> click the drop down next to **Connection filter policy (always ON**), and verify the settings.</span></span>

- <span data-ttu-id="a0f57-184">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="a0f57-184">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="a0f57-185">从 IP 允许列表上的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="a0f57-185">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="a0f57-186">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="a0f57-186">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="a0f57-187">以下各节确定了配置 IP 允许列表时您需要了解的其他项目。</span><span class="sxs-lookup"><span data-stu-id="a0f57-187">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="a0f57-188">跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="a0f57-188">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="a0f57-189">如本文前面所述，只能在 IP 允许列表中使用网络掩码为 /24 到 /32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="a0f57-189">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="a0f57-190">若要跳过对来自 /1 到 /23 范围内源电子邮件服务器的邮件的垃圾邮件筛选，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-190">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a0f57-191">但是，我们建议你尽可能不要这样做，因为如果 /1 到 /23 CIDR IP 范围中的 IP 地址出现在任何 Microsoft 专有或第三方阻止列表中，邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="a0f57-191">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="a0f57-192">现在，您完全意识到潜在问题，您至少可以使用以下设置 (创建邮件流规则) 以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="a0f57-192">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="a0f57-193">规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与输入 CIDR IP (\>  \>  \> /1 到 /23 网络掩码完全匹配，则应用此规则) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-193">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>

- <span data-ttu-id="a0f57-194">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="a0f57-194">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="a0f57-195">您可以在特定时段内审核规则、测试规则、激活规则以及其他选择。</span><span class="sxs-lookup"><span data-stu-id="a0f57-195">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="a0f57-196">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="a0f57-196">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="a0f57-197">有关详细信息，请参阅管理 [Exchange Online 中的邮件流规则](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="a0f57-197">For more information, see [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="a0f57-198">跳过来自同一来源的选择性电子邮件域的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="a0f57-198">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="a0f57-199">通常，将 IP 地址或地址范围添加到 IP 允许列表意味着信任来自该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="a0f57-199">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="a0f57-200">但是，如果该源从多个域发送电子邮件，并且您希望跳过其中某些域（而非其他域）的垃圾邮件筛选，那又如何呢？</span><span class="sxs-lookup"><span data-stu-id="a0f57-200">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="a0f57-201">不能单独使用 IP 允许列表来这样做，但可以将 IP 允许列表与邮件流规则结合使用。</span><span class="sxs-lookup"><span data-stu-id="a0f57-201">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="a0f57-202">例如，源电子邮件服务器 192.168.1.25 从 contoso.com、fabrikam.com 和 tailspintoys.com 域发送电子邮件，但您只想跳过对 fabrikam.com 中发件人的邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="a0f57-202">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="a0f57-203">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a0f57-203">To do this, use the following steps:</span></span>

1. <span data-ttu-id="a0f57-204">将 192.168.1.25 添加到 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="a0f57-204">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="a0f57-205">配置邮件流规则，至少 (以下) ：</span><span class="sxs-lookup"><span data-stu-id="a0f57-205">Configure a mail flow rule with the following settings (at a minimum):</span></span>

   - <span data-ttu-id="a0f57-206">规则 **条件：** 如果发件人 IP 地址位于上述任一范围内或完全匹配 \>  \> 192.168.1.25 (则应用此规则，该 IP 地址或地址范围与在上一步骤) 中添加到 IP 允许列表的 IP 地址或地址范围完全匹配。 \></span><span class="sxs-lookup"><span data-stu-id="a0f57-206">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>

   - <span data-ttu-id="a0f57-207">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL)** \> **0。**</span><span class="sxs-lookup"><span data-stu-id="a0f57-207">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>

   - <span data-ttu-id="a0f57-208">规则例外 **：发件人** 域 fabrikam.com (要跳过垃圾邮件筛选的一个或多个 \>  \>) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-208">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="a0f57-209">仍筛选来自 IP 允许列表中的源的邮件的方案</span><span class="sxs-lookup"><span data-stu-id="a0f57-209">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="a0f57-210">在下列情况下，来自 IP 允许列表中电子邮件服务器的邮件仍受垃圾邮件筛选限制：</span><span class="sxs-lookup"><span data-stu-id="a0f57-210">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="a0f57-211">IP 允许列表中的 IP 地址也配置在 Microsoft 365 (任何租户中基于IP 的入站连接器中 (让我们调用此租户 A) ，租户 A 和首次遇到邮件的 EOP 服务器正好位于 Microsoft 数据中心中的同一 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="a0f57-211">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="a0f57-212">在此方案中 **，IPV：CAL** 将添加到邮件的反垃圾邮件邮件头 [ (](anti-spam-message-headers.md)指示邮件绕过了垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="a0f57-212">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="a0f57-213">包含 IP 允许列表的租户和首次遇到邮件的 EOP 服务器都发生在 Microsoft 数据中心的不同 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="a0f57-213">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="a0f57-214">在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="a0f57-214">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="a0f57-215">如果遇到上述任一情况，则至少可以使用以下设置 (创建邮件流规则) 以确保来自有问题的 IP 地址的邮件跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="a0f57-215">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="a0f57-216">规则条件 **：如果** 发件人 IP 地址位于以下任一范围内或与 IP 地址 (完全匹配，则应用此 \>  \>  \>) 。</span><span class="sxs-lookup"><span data-stu-id="a0f57-216">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="a0f57-217">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="a0f57-217">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="a0f57-218">是 Microsoft 365 的新增功能？</span><span class="sxs-lookup"><span data-stu-id="a0f57-218">New to Microsoft 365?</span></span>

****

<span data-ttu-id="a0f57-219">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 的简短图标**</span><span class="sxs-lookup"><span data-stu-id="a0f57-219">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="a0f57-220">发现 LinkedIn Learning 为 **Microsoft 365** 管理员和 IT 专业人员提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="a0f57-220">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>