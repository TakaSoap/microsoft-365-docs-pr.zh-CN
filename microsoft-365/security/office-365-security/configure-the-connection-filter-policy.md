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
description: 管理员可以了解如何在 EOP Exchange Online Protection (配置) 以允许或阻止来自电子邮件服务器的电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5eb24377dd9f9ac304e1df7b2902d29e4a738b9
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821957"
---
# <a name="configure-connection-filtering"></a><span data-ttu-id="8ce3f-103">配置连接筛选</span><span class="sxs-lookup"><span data-stu-id="8ce3f-103">Configure connection filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8ce3f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="8ce3f-104">**Applies to**</span></span>
- [<span data-ttu-id="8ce3f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8ce3f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8ce3f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="8ce3f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8ce3f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ce3f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


<span data-ttu-id="8ce3f-108">如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，请使用 EOP (中的连接筛选，特别是默认连接筛选器策略) 通过 IP 地址标识好或坏的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, you use connection filtering in EOP (specifically, the default connection filter policy) to identify good or bad source email servers by their IP addresses.</span></span> <span data-ttu-id="8ce3f-109">默认连接筛选器策略的关键组件包括：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-109">The key components of the default connection filter policy are:</span></span>

- <span data-ttu-id="8ce3f-110">**IP 允许列表**：跳过对来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-110">**IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="8ce3f-111">有关这些来源的邮件仍可能发生垃圾邮件筛选的方案，请参阅本文稍后介绍的从 [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 允许列表来源筛选邮件的方案部分。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-111">For scenarios where spam filtering might still occur on messages from these sources, see the [Scenarios where messages from sources in the IP Allow List are still filtered](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) section later in this article.</span></span> <span data-ttu-id="8ce3f-112">有关 IP 允许列表如何适合整体安全发件人策略的信息，请参阅在 EOP 中创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-112">For more information about how the IP Allow List should fit into your overall safe senders strategy, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="8ce3f-113">**IP 阻止列表**：阻止来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-113">**IP Block List**: Block all incoming messages from the source email servers that you specify by IP address or IP address range.</span></span> <span data-ttu-id="8ce3f-114">传入的邮件被拒绝，不会标记为垃圾邮件，并且不会进行其他筛选。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-114">The incoming messages are rejected, are not marked as spam, and no additional filtering occurs.</span></span> <span data-ttu-id="8ce3f-115">有关 IP 阻止列表如何适合整体阻止的发件人策略，请参阅在 EOP 中创建 [阻止发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-115">For more information about how the IP Block List should fit into your overall blocked senders strategy, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

- <span data-ttu-id="8ce3f-116">**保险箱列表**：安全 *列表是* Microsoft 数据中心中的动态允许列表，无需客户配置。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-116">**Safe list**: The *safe list* is a dynamic allow list in the Microsoft datacenter that requires no customer configuration.</span></span> <span data-ttu-id="8ce3f-117">Microsoft 从订阅到各种第三方列表标识这些受信任的电子邮件源。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-117">Microsoft identifies these trusted email sources from subscriptions to various third-party lists.</span></span> <span data-ttu-id="8ce3f-118">启用或禁用安全列表的使用;无法配置安全列表上的源电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-118">You enable or disable the use of the safe list; you can't configure the source email servers on the safe list.</span></span> <span data-ttu-id="8ce3f-119">对来自安全列表上的电子邮件服务器的传入邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-119">Spam filtering is skipped on incoming messages from the email servers on the safe list.</span></span>

<span data-ttu-id="8ce3f-120">本文介绍如何在 Microsoft 365 安全中心或 PowerShell (Exchange Online PowerShell 中为 Microsoft 365 组织配置默认连接筛选器策略，Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-120">This article describes how to configure the default connection filter policy in the Microsoft 365 security center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span> <span data-ttu-id="8ce3f-121">有关 EOP 如何使用连接筛选是组织整体反垃圾邮件设置的一部分，请参阅 [反垃圾邮件保护](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-121">For more information about how EOP uses connection filtering is part of your organization's overall anti-spam settings, see see [Anti-spam protection](anti-spam-protection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8ce3f-122">IP 允许列表、安全列表和 IP 阻止列表是允许或阻止组织中电子邮件的总体策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-122">The IP Allow List, safe list, and the IP Block List are one part of your overall strategy to allow or block email in your organization.</span></span> <span data-ttu-id="8ce3f-123">有关详细信息，请参阅创建[安全发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-123">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md) and [Create blocked sender lists](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8ce3f-124">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8ce3f-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8ce3f-125">在 <https://security.microsoft.com> 打开安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-125">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="8ce3f-126">若要直接转到“**反垃圾邮件策略**”页面，请使用 <https://security.microsoft.com/antispam>。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-126">To go directly to the **Anti-spam policies** page, use <https://security.microsoft.com/antispam>.</span></span>

- <span data-ttu-id="8ce3f-127">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8ce3f-128">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-128">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8ce3f-129">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-129">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8ce3f-130">若要修改默认连接筛选器策略，您必须是组织管理或 **安全管理员角色组** 的成员。 </span><span class="sxs-lookup"><span data-stu-id="8ce3f-130">To modify the default connection filter policy, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8ce3f-131">若要对默认连接筛选器策略进行只读访问，您需要是全局读取 **者** 角色组或安全读者 **角色组的成员** 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-131">For read-only access to the default connection filter policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8ce3f-132">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-132">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8ce3f-133">**注意**：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-133">**Notes**:</span></span>

  - <span data-ttu-id="8ce3f-134">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-134">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8ce3f-135">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-135">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8ce3f-136">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-136">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="8ce3f-137">若要查找要允许或阻止的电子邮件服务器的源 IP 地址 (发件人) ，可以检查邮件头中的连接 IP (**CIP**) 头字段。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-137">To find the source IP addresses of the email servers (senders) that you want to allow or block, you can check the connecting IP (**CIP**) header field in the message header.</span></span> <span data-ttu-id="8ce3f-138">若要查看各种电子邮件客户端中的邮件头，请参阅在电子邮件客户端中查看[Outlook。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)</span><span class="sxs-lookup"><span data-stu-id="8ce3f-138">To view a message header in various email clients, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

- <span data-ttu-id="8ce3f-139">IP 允许列表优先于 IP 阻止列表 (两个列表上的地址不会) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-139">The IP Allow List takes precedence over the IP Block List (an address on both lists is not blocked).</span></span>

- <span data-ttu-id="8ce3f-140">IP 允许列表和 IP 阻止列表最多支持 1273 个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域际路由 (CIDR) IP。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-140">The IP Allow List and the IP Block List each support a maximum of 1273 entries, where an entry is a single IP address, an IP address range, or a Classless InterDomain Routing (CIDR) IP.</span></span>

## <a name="use-the-security-center-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="8ce3f-141">使用安全中心修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="8ce3f-141">Use the security center to modify the default connection filter policy</span></span>

1. <span data-ttu-id="8ce3f-142">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-142">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8ce3f-143">在" **反垃圾邮件策略** "页上，单击 (，从 **) 选择"** 连接筛选器策略""默认策略"。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-143">On the **Anti-spam policies** page, select **Connection filter policy (Default)** from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="8ce3f-144">在出现的策略详细信息飞出中，配置以下任意设置：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-144">In the policy details flyout that appears, configure any of the following settings:</span></span>

   - <span data-ttu-id="8ce3f-145">**"** 说明"部分：单击 **"编辑名称和说明"。**</span><span class="sxs-lookup"><span data-stu-id="8ce3f-145">**Description** section: Click **Edit name and description**.</span></span> <span data-ttu-id="8ce3f-146">在出现的 **"编辑名称和说明** "飞出控件中，在"说明"框中输入可选 **描述** 性文本。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-146">In the **Edit name and description** flyout that appears, enter optional descriptive text in the **Description** box.</span></span>

     <span data-ttu-id="8ce3f-147">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-147">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8ce3f-148">**"连接筛选"部分**：单击 **"编辑连接筛选器策略"。**</span><span class="sxs-lookup"><span data-stu-id="8ce3f-148">**Connection filtering section**: Click **Edit connection filter policy**.</span></span> <span data-ttu-id="8ce3f-149">在出现的"飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-149">In the flyout that appears, configure the following settings:</span></span>

     - <span data-ttu-id="8ce3f-150">**始终允许来自以下 IP 地址或地址范围的邮件**：这是 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-150">**Always allow messages from the following IP addresses or address range**: This is the IP Allow list.</span></span> <span data-ttu-id="8ce3f-151">在框中单击，输入值，然后按 Enter 或选择显示在框下方的完整值。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-151">Click in the box, enter a value, and then press Enter or select the complete value that's displayed below the box.</span></span> <span data-ttu-id="8ce3f-152">有效值包括</span><span class="sxs-lookup"><span data-stu-id="8ce3f-152">Valid values are</span></span>
       - <span data-ttu-id="8ce3f-153">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-153">Single IP: For example, 192.168.1.1.</span></span>
       - <span data-ttu-id="8ce3f-154">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-154">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
       - <span data-ttu-id="8ce3f-155">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-155">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="8ce3f-156">有效的子网掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-156">Valid subnet mask values are /24 through /32.</span></span> <span data-ttu-id="8ce3f-157">若要跳过对 /1 到 /23 的垃圾邮件筛选，请参阅本文稍后在可用范围外跳过 [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 的垃圾邮件筛选部分。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-157">To skip spam filtering for /1 to /23, see the [Skip spam filtering for a CIDR IP outside of the available range](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) section later in this article.</span></span>

       <span data-ttu-id="8ce3f-158">根据需要重复执行此步骤（次数不限）。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-158">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="8ce3f-159">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="8ce3f-159">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="8ce3f-161">“删除”。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-161">next to the value.</span></span>

     <span data-ttu-id="8ce3f-162">若要添加 IP 地址或地址范围，请在框中单击并键入 itclick **添加添加** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-162">To add the IP address or address range, click in the box and type itclick **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="8ce3f-163">若要删除条目，请选择"允许的 **IP** 地址"中的条目，然后单击" **删除""删除** ![ ](../../media/scc-remove-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-163">To remove an entry, select the entry in **Allowed IP Address** and then click **Remove** ![Remove](../../media/scc-remove-icon.png).</span></span> <span data-ttu-id="8ce3f-164">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-164">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8ce3f-165">**始终阻止来自以下 IP 地址或地址范围的邮件**：这是 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-165">**Always block messages from the following IP addresses or address range**: This is the IP Block List.</span></span> <span data-ttu-id="8ce3f-166">在框中输入单个 IP、IP 范围或 CIDR IP，如前面"始终允许来自以下 **IP** 地址或地址范围的邮件"设置中所述。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-166">Enter a single IP, IP range, or CIDR IP in the box as previously described in the **Always allow messages from the following IP addresses or address range** setting.</span></span>

   - <span data-ttu-id="8ce3f-167">**打开安全列表**：启用或禁用安全列表，以标识将跳过垃圾邮件筛选的已知、良好的发件人。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-167">**Turn on safe list**: Enable or disable the use of the safe list to identify known, good senders that will skip spam filtering.</span></span> <span data-ttu-id="8ce3f-168">若要使用安全列表，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-168">To use the safe list, select the check box.</span></span>

   <span data-ttu-id="8ce3f-169">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-169">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="8ce3f-170">返回策略详细信息浮出控件，单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-170">Back on the policy details flyout, click **Close**.</span></span>

## <a name="use-the-security-center-to-view-the-default-connection-filter-policy"></a><span data-ttu-id="8ce3f-171">使用安全中心查看默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="8ce3f-171">Use the security center to view the default connection filter policy</span></span>

1. <span data-ttu-id="8ce3f-172">在安全中心，转到 **“电子邮件和协作”** \> **“策略和规则”** \> **“威胁策略”** \> **“策略”** 部分 \> **“反垃圾邮件”**。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-172">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8ce3f-173">在 **"反垃圾邮件策略"** 页上，策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-173">On the **Anti-spam policies** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="8ce3f-174">**名称**：此值为 **连接筛选器策略 (默认**) 默认连接筛选器策略的默认值。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-174">**Name**: This value is **Connection filter policy (Default)** for the default connection filter policy.</span></span>
   - <span data-ttu-id="8ce3f-175">**状态**：对于默认 **连接** 筛选器策略，此值为 Always on。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-175">**Status**: This value is **Always on** for the default connection filter policy.</span></span>
   - <span data-ttu-id="8ce3f-176">**优先级**：对于默认 **连接** 筛选器策略，此值为"最低"。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-176">**Priority**: This value is **Lowest** for the default connection filter policy.</span></span>
   - <span data-ttu-id="8ce3f-177">**类型**：对于默认连接筛选器策略，此值为空。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-177">**Type**: This value is blank for the default connection filter policy.</span></span>

3. <span data-ttu-id="8ce3f-178">选择默认连接筛选器策略时，策略设置会显示在一个飞出区中。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-178">When you select the default connection filter policy, the policy settings are displayed in a flyout.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a><span data-ttu-id="8ce3f-179">使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="8ce3f-179">Use Exchange Online PowerShell or standalone EOP PowerShell to modify the default connection filter policy</span></span>

<span data-ttu-id="8ce3f-180">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-180">Use the following syntax:</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

<span data-ttu-id="8ce3f-181">**注意**：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-181">**Notes**:</span></span>

- <span data-ttu-id="8ce3f-182">有效的 IP 地址或地址范围值为：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-182">Valid IP address or address range values are:</span></span>
  - <span data-ttu-id="8ce3f-183">单个 IP：例如，192.168.1.1。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-183">Single IP: For example, 192.168.1.1.</span></span>
  - <span data-ttu-id="8ce3f-184">IP 范围：例如，192.168.0.1-192.168.0.254。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-184">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
  - <span data-ttu-id="8ce3f-185">CIDR IP：例如，192.168.0.1/25。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-185">CIDR IP: For example, 192.168.0.1/25.</span></span> <span data-ttu-id="8ce3f-186">有效的网络掩码值为 /24 到 /32。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-186">Valid network mask values are /24 through /32.</span></span>
- <span data-ttu-id="8ce3f-187">若要 *使用* 指定的值覆盖任何现有条目，请使用以下语法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-187">To *overwrite* any existing entries with the values you specify, use the following syntax: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`.</span></span>
- <span data-ttu-id="8ce3f-188">若要 *添加或删除* IP 地址或地址范围而不影响其他现有条目，请使用以下语法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-188">To *add or remove* IP addresses or address ranges without affecting other existing entries, use the following syntax: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`.</span></span>
- <span data-ttu-id="8ce3f-189">若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-189">To empty the IP Allow List or IP Block List, use the value `$null`.</span></span>

<span data-ttu-id="8ce3f-190">此示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-190">This example configures the IP Allow List and the IP Block List with the specified IP addresses and address ranges.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

<span data-ttu-id="8ce3f-191">此示例在 IP 允许列表中添加和删除指定的 IP 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-191">This example adds and removes the specified IP addresses and address ranges from the IP Allow List.</span></span>

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

<span data-ttu-id="8ce3f-192">有关语法和参数的详细信息，请参阅 [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-192">For detailed syntax and parameter information, see [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8ce3f-193">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="8ce3f-193">How do you know this worked?</span></span>

<span data-ttu-id="8ce3f-194">若要验证是否成功修改了默认连接筛选器策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-194">To verify that you've successfully modified the default connection filter policy, do any of the following steps:</span></span>

- <span data-ttu-id="8ce3f-195">在安全中心，单击策略 **名称，** 从列表中转到"电子邮件 & 协作策略 & 规则威胁策略策略"部分"反垃圾邮件"选择"连接筛选器策略 (默认 \>  \>  \>  \>  \> **) "，** 然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-195">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-spam** \> select **Connection filter policy (Default)** from the list by clicking on the name of the policy, and verify the settings.</span></span>

- <span data-ttu-id="8ce3f-196">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-196">In Exchange Online PowerShell or standalone EOP PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- <span data-ttu-id="8ce3f-197">从 IP 允许列表上的条目发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-197">Send a test message from an entry on the IP Allow List.</span></span>

## <a name="additional-considerations-for-the-ip-allow-list"></a><span data-ttu-id="8ce3f-198">IP 允许列表的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="8ce3f-198">Additional considerations for the IP Allow List</span></span>

<span data-ttu-id="8ce3f-199">以下各节确定了配置 IP 允许列表时您需要了解的其他项目。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-199">The following sections identify additional items that you need to know about when you configure the IP Allow List.</span></span>

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a><span data-ttu-id="8ce3f-200">跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="8ce3f-200">Skip spam filtering for a CIDR IP outside of the available range</span></span>

<span data-ttu-id="8ce3f-201">如本文前面所述，只能在 IP 允许列表中使用网络掩码为 /24 到 /32 的 CIDR IP。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-201">As described earlier in this article, you can only use a CIDR IP with the network mask /24 to /32 in the IP Allow List.</span></span> <span data-ttu-id="8ce3f-202">若要跳过对来自 /1 到 /23 范围内源电子邮件服务器的邮件的垃圾邮件筛选，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-202">To skip spam filtering on messages from source email servers in the /1 to /23 range, you need to use Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="8ce3f-203">但是，我们建议你尽可能不要这样做，因为如果 /1 到 /23 CIDR IP 范围中的 IP 地址出现在任何 Microsoft 专有或第三方阻止列表中，邮件将被阻止。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-203">But, we recommend that you don't do this if at all possible, because the messages will be blocked if an IP address in the /1 to /23 CIDR IP range appears on any of Microsoft's proprietary or third-party block lists.</span></span>

<span data-ttu-id="8ce3f-204">现在，您完全意识到潜在问题，您至少可以使用以下设置 (创建邮件流规则) 以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-204">Now that you're fully aware of the potential issues, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from these IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="8ce3f-205">规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与输入 CIDR IP (\>  \>  \> /1 到 /23 网络掩码完全匹配，则应用此规则) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-205">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (enter your CIDR IP with a /1 to /23 network mask).</span></span>
- <span data-ttu-id="8ce3f-206">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-206">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="8ce3f-207">您可以在特定时段内审核规则、测试规则、激活规则以及其他选择。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-207">You can audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="8ce3f-208">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-208">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="8ce3f-209">有关详细信息，请参阅管理[邮件流规则Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="8ce3f-209">For more information, see [Manage mail flow rules in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span>

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a><span data-ttu-id="8ce3f-210">跳过来自同一来源的选择性电子邮件域的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="8ce3f-210">Skip spam filtering on selective email domains from the same source</span></span>

<span data-ttu-id="8ce3f-211">通常，将 IP 地址或地址范围添加到 IP 允许列表意味着信任来自该电子邮件源的所有传入邮件。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-211">Typically, adding an IP address or address range to the IP Allow List means you trust all incoming messages from that email source.</span></span> <span data-ttu-id="8ce3f-212">但是，如果该源从多个域发送电子邮件，并且您希望跳过其中某些域（而非其他域）的垃圾邮件筛选，那又如何呢？</span><span class="sxs-lookup"><span data-stu-id="8ce3f-212">But what if that source sends email from multiple domains, and you want to skip spam filtering for some of those domains, but not others?</span></span> <span data-ttu-id="8ce3f-213">不能单独使用 IP 允许列表来这样做，但可以将 IP 允许列表与邮件流规则结合使用。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-213">You can't use the IP Allow List alone to do this, but you can use the IP Allow List in combination with a mail flow rule.</span></span>

<span data-ttu-id="8ce3f-214">例如，源电子邮件服务器 192.168.1.25 从 contoso.com、fabrikam.com 和 tailspintoys.com 域发送电子邮件，但您只想跳过对 fabrikam.com 中发件人的邮件的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-214">For example, the source email server 192.168.1.25 sends email from the domains contoso.com, fabrikam.com, and tailspintoys.com, but you only want to skip spam filtering for messages from senders in fabrikam.com.</span></span> <span data-ttu-id="8ce3f-215">为此，请使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-215">To do this, use the following steps:</span></span>

1. <span data-ttu-id="8ce3f-216">将 192.168.1.25 添加到 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-216">Add 192.168.1.25 to the IP Allow List.</span></span>

2. <span data-ttu-id="8ce3f-217">配置邮件流规则，至少 (以下) ：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-217">Configure a mail flow rule with the following settings (at a minimum):</span></span>
   - <span data-ttu-id="8ce3f-218">规则 **条件：** 如果发件人 IP 地址位于上述任一范围内或完全匹配 \>  \> 192.168.1.25 (则应用此规则，该 IP 地址或地址范围与在上一步骤) 中添加到 IP 允许列表的 IP 地址或地址范围完全匹配。 \></span><span class="sxs-lookup"><span data-stu-id="8ce3f-218">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (the same IP address or address range that you added to the IP Allow List in the previous step).</span></span>
   - <span data-ttu-id="8ce3f-219">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL)** \> **0。**</span><span class="sxs-lookup"><span data-stu-id="8ce3f-219">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **0**.</span></span>
   - <span data-ttu-id="8ce3f-220">规则例外 **：发件人** 域 fabrikam.com (要跳过垃圾邮件筛选的一个或多个 \>  \>) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-220">Rule exception: **The sender** \> **domain is** \> fabrikam.com (only the domain or domains that you want to skip spam filtering).</span></span>

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a><span data-ttu-id="8ce3f-221">仍筛选来自 IP 允许列表中的源的邮件的方案</span><span class="sxs-lookup"><span data-stu-id="8ce3f-221">Scenarios where messages from sources in the IP Allow List are still filtered</span></span>

<span data-ttu-id="8ce3f-222">在下列情况下，来自 IP 允许列表中电子邮件服务器的邮件仍受垃圾邮件筛选限制：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-222">Messages from an email server in your IP Allow List are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="8ce3f-223">IP 允许列表中的 IP 地址也在 Microsoft 365 (中任何租户的基于 IP 的入站内部部署连接器中配置，让我们调用此租户 A) ，租户 A 和首次遇到邮件的 EOP 服务器正好位于 Microsoft 数据中心中的同一 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-223">An IP address in your IP Allow List is also configured in an on-premises, IP-based inbound connector in *any* tenant in Microsoft 365 (let's call this Tenant A), **and** Tenant A and the EOP server that first encounters the message both happen to be in *the same* Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="8ce3f-224">在此方案中 **，IPV：CAL** 将添加到邮件的反垃圾邮件邮件头 [ (](anti-spam-message-headers.md)指示邮件绕过了垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-224">In this scenario, **IPV:CAL** *is* added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="8ce3f-225">包含 IP 允许列表的租户和首次遇到邮件的 EOP 服务器都发生在 Microsoft 数据中心的不同 *Active* Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-225">Your tenant that contains the IP Allow List and the EOP server that first encounters the message both happen to be in *different* Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="8ce3f-226">在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍受垃圾邮件筛选限制。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-226">In this scenario, **IPV:CAL** *is not* added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="8ce3f-227">如果遇到上述任一情况，则至少可以使用以下设置 (创建邮件流规则) 以确保来自有问题的 IP 地址的邮件跳过垃圾邮件筛选：</span><span class="sxs-lookup"><span data-stu-id="8ce3f-227">If you encounter either of these scenarios, you can create a mail flow rule with the following settings (at a minimum) to ensure that messages from the problematic IP addresses will skip spam filtering:</span></span>

- <span data-ttu-id="8ce3f-228">规则条件 **：如果** 发件人 IP 地址位于以下任一范围内或与 IP 地址 (完全匹配，则应用此 \>  \>  \>) 。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-228">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>
- <span data-ttu-id="8ce3f-229">规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-229">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

## <a name="new-to-microsoft-365"></a><span data-ttu-id="8ce3f-230">是新Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="8ce3f-230">New to Microsoft 365?</span></span>

****

<span data-ttu-id="8ce3f-231">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="8ce3f-231">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="8ce3f-232">发现 LinkedIn Learning Microsoft 365为管理员 **和 IT** 专业人员提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="8ce3f-232">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
