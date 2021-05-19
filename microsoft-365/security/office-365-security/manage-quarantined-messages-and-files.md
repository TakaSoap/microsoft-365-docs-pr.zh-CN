---
title: 以管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 EOP 管理中心中查看和管理所有用户Exchange Online Protection () 。 使用 Microsoft Defender for Office 365 的组织的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离Microsoft Teams。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 508866fd66e4cbd00f559446d4ce52a4be063c94
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539103"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="65a9b-104">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="65a9b-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="65a9b-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="65a9b-105">**Applies to**</span></span>
- [<span data-ttu-id="65a9b-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="65a9b-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="65a9b-107">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="65a9b-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="65a9b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65a9b-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="65a9b-109">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="65a9b-110">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="65a9b-111">管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="65a9b-112">只有管理员才能管理被隔离为恶意软件、高可信度网络钓鱼的邮件，或由于邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="65a9b-113">管理员还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="65a9b-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="65a9b-114">使用 Microsoft Defender for Office 365 的组织的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中查看、下载和删除隔离Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="65a9b-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="65a9b-115">在安全与合规中心或 PowerShell & PowerShell 中查看和管理隔离邮件， (Exchange Online Microsoft 365邮箱位于 Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65a9b-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="65a9b-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="65a9b-117">若要打开安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="65a9b-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="65a9b-118">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="65a9b-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="65a9b-119">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="65a9b-120">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="65a9b-121">在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="65a9b-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="65a9b-122">若要对所有用户的隔离邮件采取措施，你需要是组织管理、安全管理员或隔离管理员 **角色** <sup>\*</sup> 组的成员。</span><span class="sxs-lookup"><span data-stu-id="65a9b-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="65a9b-123">若要对所有用户的隔离邮件进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="65a9b-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="65a9b-124">有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="65a9b-125">**注意**：</span><span class="sxs-lookup"><span data-stu-id="65a9b-125">**Notes**:</span></span>

  - <span data-ttu-id="65a9b-126">在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。</span><span class="sxs-lookup"><span data-stu-id="65a9b-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="65a9b-127">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="65a9b-128">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="65a9b-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="65a9b-129"><sup>\*</sup>隔离管理员 **角色** 组的成员还需要是 Exchange Online 中清洁管理角色组的成员，才能在 [](/Exchange/permissions-exo/permissions-exo#role-groups)PowerShell 中执行Exchange Online过程。</span><span class="sxs-lookup"><span data-stu-id="65a9b-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="65a9b-130">隔离邮件在被自动删除之前将保留一段默认时间：</span><span class="sxs-lookup"><span data-stu-id="65a9b-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="65a9b-131">30 天内，由反垃圾邮件策略隔离的邮件 (垃圾邮件、网络钓鱼和批量电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="65a9b-132">这是默认值和最大值。</span><span class="sxs-lookup"><span data-stu-id="65a9b-132">This is the default and maximum value.</span></span> <span data-ttu-id="65a9b-133">若要配置 (此值) ，请参阅配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="65a9b-134">包含恶意软件的邮件的 15 天。</span><span class="sxs-lookup"><span data-stu-id="65a9b-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="65a9b-135">对于在 Defender for 保险箱 中由 SharePoint、OneDrive 和 Microsoft Teams 附件隔离Microsoft Teams 15 Office 365。</span><span class="sxs-lookup"><span data-stu-id="65a9b-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="65a9b-136">当邮件从隔离区过期时，你无法恢复它。</span><span class="sxs-lookup"><span data-stu-id="65a9b-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="65a9b-137">使用安全&中心管理隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="65a9b-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="65a9b-138">查看隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="65a9b-138">View quarantined email</span></span>

1. <span data-ttu-id="65a9b-139">在安全与&中心，转到"**威胁管理** \> **""审阅隔离** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="65a9b-139">In the Security & Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="65a9b-140">验证“**查看隔离项目**”是否设置为默认值“**电子邮件**”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="65a9b-141">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="65a9b-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="65a9b-142">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="65a9b-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="65a9b-143">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="65a9b-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="65a9b-144">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-145">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-146">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-147">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-148">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-149">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="65a9b-150">**Expires**</span></span>
   - <span data-ttu-id="65a9b-151">**收件人**</span><span class="sxs-lookup"><span data-stu-id="65a9b-151">**Recipient**</span></span>
   - <span data-ttu-id="65a9b-152">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="65a9b-152">**Message ID**</span></span>
   - <span data-ttu-id="65a9b-153">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="65a9b-153">**Policy name**</span></span>
   - <span data-ttu-id="65a9b-154">**大小**</span><span class="sxs-lookup"><span data-stu-id="65a9b-154">**Size**</span></span>
   - <span data-ttu-id="65a9b-155">**方向**</span><span class="sxs-lookup"><span data-stu-id="65a9b-155">**Direction**</span></span>

   <span data-ttu-id="65a9b-156">完成后，单击“保存”单击“设置为默认设置”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="65a9b-157">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="65a9b-158">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="65a9b-158">The available filters are:</span></span>

   - <span data-ttu-id="65a9b-159">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="65a9b-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="65a9b-160">**今天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-160">**Today**</span></span>
     - <span data-ttu-id="65a9b-161">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-161">**Next 2 days**</span></span>
     - <span data-ttu-id="65a9b-162">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-162">**Next 7 days**</span></span>
     - <span data-ttu-id="65a9b-163">**自定义**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="65a9b-164">**接收时间**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="65a9b-165">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="65a9b-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="65a9b-166">**策略**：邮件与邮件流规则条件匹配 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="65a9b-167">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-167">**Bulk**</span></span>
     - <span data-ttu-id="65a9b-168">**网络钓鱼**：垃圾邮件筛选器 **裁定是钓鱼** 电子邮件或防钓鱼保护隔离了邮件 ([欺骗](set-up-anti-phishing-policies.md#spoof-settings)[设置或模拟](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)保护) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="65a9b-169">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-169">**Malware**</span></span>
     - <span data-ttu-id="65a9b-170">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-170">**Spam**</span></span>
     - <span data-ttu-id="65a9b-171">**高可信度钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="65a9b-172">**策略类型**：按策略类型筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="65a9b-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="65a9b-173">**反恶意软件策略**</span><span class="sxs-lookup"><span data-stu-id="65a9b-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="65a9b-174">**保险箱附件策略**</span><span class="sxs-lookup"><span data-stu-id="65a9b-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="65a9b-175">**反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="65a9b-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="65a9b-176">**托管内容筛选器策略**（反垃圾邮件策略）</span><span class="sxs-lookup"><span data-stu-id="65a9b-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="65a9b-177">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="65a9b-177">**Transport rule**</span></span>

   - <span data-ttu-id="65a9b-178">**电子邮件收件人**：所有用户或仅发送给你的邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="65a9b-179">最终用户只能管理发送给他们的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="65a9b-180">若要清除筛选器，请单击“清除”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="65a9b-181">若要隐藏筛选器浮出控件，请再次单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="65a9b-182">使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="65a9b-183">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="65a9b-183">Wildcards aren't supported.</span></span> <span data-ttu-id="65a9b-184">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="65a9b-184">You can search by the following values:</span></span>

   - <span data-ttu-id="65a9b-185">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65a9b-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="65a9b-186">例如 [，使用邮件](message-trace-scc.md) 跟踪查找已发送给组织中用户的邮件，并确定邮件是隔离的而不是传递的。</span><span class="sxs-lookup"><span data-stu-id="65a9b-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="65a9b-187">请务必包括完整的邮件 ID 值，该值可能包含尖括号 \<\> () 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="65a9b-188">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="65a9b-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="65a9b-189">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="65a9b-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="65a9b-190">**策略名称**：使用邮件的完整策略名称。</span><span class="sxs-lookup"><span data-stu-id="65a9b-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="65a9b-191">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="65a9b-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="65a9b-192">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="65a9b-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="65a9b-193">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="65a9b-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="65a9b-194">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="65a9b-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="65a9b-195">**策略** 名称：负责隔离邮件的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="65a9b-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="65a9b-196">输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="65a9b-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="65a9b-197">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="65a9b-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="65a9b-198">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="65a9b-198">View quarantined message details</span></span>

<span data-ttu-id="65a9b-199">选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="65a9b-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="65a9b-200">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65a9b-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="65a9b-201">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="65a9b-201">**Sender address**</span></span>

- <span data-ttu-id="65a9b-202">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="65a9b-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="65a9b-203">**主题**</span><span class="sxs-lookup"><span data-stu-id="65a9b-203">**Subject**</span></span>

- <span data-ttu-id="65a9b-204">**隔离原因**：显示邮件被标识为垃圾邮件、批量邮件、网络钓鱼邮件、匹配邮件流规则 (**传输** 规则) 或标识为包含恶意软件 **。**</span><span class="sxs-lookup"><span data-stu-id="65a9b-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="65a9b-205">**收件人计数**</span><span class="sxs-lookup"><span data-stu-id="65a9b-205">**Recipient count**</span></span>

- <span data-ttu-id="65a9b-206">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="65a9b-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="65a9b-207">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="65a9b-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="65a9b-208">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="65a9b-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="65a9b-209">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="65a9b-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="65a9b-210">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="65a9b-210">Take action on quarantined email</span></span>

<span data-ttu-id="65a9b-211">选择邮件后，在"详细信息"飞出窗格中，您可以选择对邮件执行哪些操作： </span><span class="sxs-lookup"><span data-stu-id="65a9b-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="65a9b-212">**释放邮件**：在出现的飞出窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="65a9b-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="65a9b-213">**将邮件报告给 Microsoft 进行分析**：默认情况下选中此选项，将错误隔离的邮件报告给 Microsoft 作为误报。</span><span class="sxs-lookup"><span data-stu-id="65a9b-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="65a9b-214">如果邮件被隔离为垃圾邮件、批量邮件、网络钓鱼邮件或包含恶意软件，则还会将邮件报告给 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="65a9b-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="65a9b-215">根据分析，可能会调整服务范围内的垃圾邮件筛选规则以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="65a9b-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="65a9b-216">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="65a9b-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="65a9b-217">**将邮件释放给所有收件人**</span><span class="sxs-lookup"><span data-stu-id="65a9b-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="65a9b-218">**将邮件释放给特定收件人**</span><span class="sxs-lookup"><span data-stu-id="65a9b-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="65a9b-219">**将邮件释放给其他人**：请注意，不支持将恶意软件邮件释放给原始收件人外的其他人员。</span><span class="sxs-lookup"><span data-stu-id="65a9b-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="65a9b-220">完成后，单击“释放邮件”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="65a9b-221">有关释放邮件的注意事项：</span><span class="sxs-lookup"><span data-stu-id="65a9b-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="65a9b-222">不能将邮件释放给同一收件人多次。</span><span class="sxs-lookup"><span data-stu-id="65a9b-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="65a9b-223">只有尚未收到邮件的收件人将显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="65a9b-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="65a9b-224">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="65a9b-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="65a9b-225">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。</span><span class="sxs-lookup"><span data-stu-id="65a9b-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="65a9b-226">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：</span><span class="sxs-lookup"><span data-stu-id="65a9b-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="65a9b-227">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="65a9b-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="65a9b-228">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="65a9b-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="65a9b-229">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="65a9b-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="65a9b-230">**从隔离** 区删除：在出现的警告中单击"是"后，邮件将立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="65a9b-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="65a9b-231">**下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="65a9b-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="65a9b-232">**阻止发件人**：将发件人添加到邮箱上的"阻止发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="65a9b-232">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="65a9b-233">有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="65a9b-233">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="65a9b-234">**提交邮件**：在出现的飞出窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="65a9b-234">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="65a9b-235">**对象类型**： **电子邮件** (默认 **) 、URL** 或 **附件**。</span><span class="sxs-lookup"><span data-stu-id="65a9b-235">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="65a9b-236">提交 **格式**：网络消息 ID (默认为，"网络消息 **ID"** 框中的相应值为) 或 **file** (浏览到本地 .eml 或 .msg) 。 </span><span class="sxs-lookup"><span data-stu-id="65a9b-236">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="65a9b-237">请注意，如果您选择" **文件"，** 然后选择" **网络消息 ID"，** 初始值将消失。</span><span class="sxs-lookup"><span data-stu-id="65a9b-237">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="65a9b-238">**收件人：** 在租用邮件的原始收件人时键入 ，或单击"全 **选** "以标识所有收件人。</span><span class="sxs-lookup"><span data-stu-id="65a9b-238">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="65a9b-239">也可以单击"全 **选"，** 然后有选择地删除各个收件人。</span><span class="sxs-lookup"><span data-stu-id="65a9b-239">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="65a9b-240">**提交原因\*\*\*\*：不应被** 阻止 (默认) **或应该已被阻止**。</span><span class="sxs-lookup"><span data-stu-id="65a9b-240">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="65a9b-241">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="65a9b-241">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="65a9b-242">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="65a9b-242">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="65a9b-243">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="65a9b-243">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="65a9b-244">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65a9b-244">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="65a9b-245">**释放邮件**：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-245">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="65a9b-246">请考虑以下方案：john@gmail.com 向用户发送 faith@contoso.com john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="65a9b-246">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="65a9b-247">Gmail 将此邮件分为两个副本，这两个副本在 Microsoft 中都作为网络钓鱼路由到隔离邮箱。</span><span class="sxs-lookup"><span data-stu-id="65a9b-247">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="65a9b-248">管理员将这两条消息释放到 admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="65a9b-248">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="65a9b-249">将传递到达管理员邮箱的第一个释放的邮件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-249">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="65a9b-250">第二个释放的邮件被标识为重复传递并跳过。</span><span class="sxs-lookup"><span data-stu-id="65a9b-250">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="65a9b-251">如果邮件具有相同的邮件 ID 和接收时间，则邮件被标识为重复项。</span><span class="sxs-lookup"><span data-stu-id="65a9b-251">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="65a9b-252">**删除邮件**：在 **出现的警告中** 单击"是"后，将立即删除这些邮件，而不发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="65a9b-252">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="65a9b-253">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-253">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="65a9b-254">仅适用于 Office 365 的 Microsoft Defender：使用安全&安全与合规中心管理隔离的文件</span><span class="sxs-lookup"><span data-stu-id="65a9b-254">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="65a9b-255">本部分中隔离文件的过程仅适用于 Microsoft Defender for Office 365计划 1 和计划 2 订阅者。</span><span class="sxs-lookup"><span data-stu-id="65a9b-255">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="65a9b-256">在具有 Defender for Office 365 的组织中，管理员可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="65a9b-256">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="65a9b-257">若要启用对这些文件的保护，请参阅打开保险箱[附件SharePoint、OneDrive和Microsoft Teams。](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="65a9b-257">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="65a9b-258">查看隔离文件</span><span class="sxs-lookup"><span data-stu-id="65a9b-258">View quarantined files</span></span>

1. <span data-ttu-id="65a9b-259">在安全与&中心，转到"**威胁管理** \> **""审阅隔离** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="65a9b-259">In the Security & Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="65a9b-260">将 **隔离视图更改为** 值 **文件**。</span><span class="sxs-lookup"><span data-stu-id="65a9b-260">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="65a9b-261">可以通过单击可用列标题对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="65a9b-261">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="65a9b-262">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="65a9b-262">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="65a9b-263">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="65a9b-263">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="65a9b-264">默认列标有星号 <sup>\*</sup> () ：</span><span class="sxs-lookup"><span data-stu-id="65a9b-264">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="65a9b-265">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-265">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-266">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-266">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-267">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-267">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-268">**文件 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-268">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-269">**文件大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-269">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-270">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-270">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-271">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="65a9b-271">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="65a9b-272">**检测者**</span><span class="sxs-lookup"><span data-stu-id="65a9b-272">**Detected by**</span></span>
   - <span data-ttu-id="65a9b-273">**按时间修改**</span><span class="sxs-lookup"><span data-stu-id="65a9b-273">**Modified by time**</span></span>

4. <span data-ttu-id="65a9b-274">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="65a9b-274">To filter the results, click **Filter**.</span></span> <span data-ttu-id="65a9b-275">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="65a9b-275">The available filters are:</span></span>

   - <span data-ttu-id="65a9b-276">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="65a9b-276">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="65a9b-277">**今天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-277">**Today**</span></span>
     - <span data-ttu-id="65a9b-278">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-278">**Next 2 days**</span></span>
     - <span data-ttu-id="65a9b-279">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="65a9b-279">**Next 7 days**</span></span>
     - <span data-ttu-id="65a9b-280">自定义日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="65a9b-280">A custom date/time range.</span></span>
   - <span data-ttu-id="65a9b-281">**接收时间**</span><span class="sxs-lookup"><span data-stu-id="65a9b-281">**Received time**</span></span>
   - <span data-ttu-id="65a9b-282">**隔离原因**：唯一可用的值为 **Malware**。</span><span class="sxs-lookup"><span data-stu-id="65a9b-282">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="65a9b-283">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="65a9b-283">**Policy type**</span></span>

<span data-ttu-id="65a9b-284">找到特定的隔离文件后，选择该文件以查看其详细信息， (例如查看、释放、下载或删除邮件) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-284">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="65a9b-285">查看隔离文件详细信息</span><span class="sxs-lookup"><span data-stu-id="65a9b-285">View quarantined file details</span></span>

<span data-ttu-id="65a9b-286">在列表中选择文件时，"详细信息"飞出窗格中会显示 **以下文件详细信息** ：</span><span class="sxs-lookup"><span data-stu-id="65a9b-286">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="65a9b-287">**文件名**</span><span class="sxs-lookup"><span data-stu-id="65a9b-287">**File Name**</span></span>
- <span data-ttu-id="65a9b-288">**文件 URL：** 用于定义文件位置的 URL (例如，在 SharePoint Online) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-288">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="65a9b-289">**检测到的恶意内容** 文件的隔离日期/时间。</span><span class="sxs-lookup"><span data-stu-id="65a9b-289">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="65a9b-290">**Expires**：从隔离区删除文件的日期。</span><span class="sxs-lookup"><span data-stu-id="65a9b-290">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="65a9b-291">**检测者**：defender Office 365或 Microsoft 的反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="65a9b-291">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="65a9b-292">**释放?**</span><span class="sxs-lookup"><span data-stu-id="65a9b-292">**Released?**</span></span>
- <span data-ttu-id="65a9b-293">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="65a9b-293">**Malware Name**</span></span>
- <span data-ttu-id="65a9b-294">**文档 ID：** 文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65a9b-294">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="65a9b-295">**文件大小：** 以 KB 为单位 (KB) 。</span><span class="sxs-lookup"><span data-stu-id="65a9b-295">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="65a9b-296">**组织** 组织的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="65a9b-296">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="65a9b-297">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="65a9b-297">**Last modified**</span></span>
- <span data-ttu-id="65a9b-298">**修改者**：上次修改文件的用户。</span><span class="sxs-lookup"><span data-stu-id="65a9b-298">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="65a9b-299">安全哈希 **算法 256 位 (SHA-256) 值**：可以使用此哈希值在其他信誉存储或环境中的其他位置标识文件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-299">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="65a9b-300">对隔离文件采取措施</span><span class="sxs-lookup"><span data-stu-id="65a9b-300">Take action on quarantined files</span></span>

<span data-ttu-id="65a9b-301">在列表中选择文件时，可以在"详细信息"飞出窗格中对文件执行以下操作： </span><span class="sxs-lookup"><span data-stu-id="65a9b-301">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="65a9b-302">**发布文件**： (默认) 将报告文件取消选中 **到 Microsoft** 进行分析，然后单击"发布 **文件"。**</span><span class="sxs-lookup"><span data-stu-id="65a9b-302">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="65a9b-303">**下载文件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-303">**Download file**</span></span>
- <span data-ttu-id="65a9b-304">**从隔离区中删除文件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-304">**Remove file from quarantine**</span></span>

<span data-ttu-id="65a9b-305">如果不释放或删除文件，将在默认隔离保留期过期后删除这些文件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-305">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="65a9b-306">对多个隔离文件的操作</span><span class="sxs-lookup"><span data-stu-id="65a9b-306">Actions on multiple quarantined files</span></span>

<span data-ttu-id="65a9b-307">在列表中选择多个隔离文件 (最多 100) 时，将显示"批量操作"飞出窗格，您可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65a9b-307">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="65a9b-308">**发布文件**</span><span class="sxs-lookup"><span data-stu-id="65a9b-308">**Release files**</span></span>
- <span data-ttu-id="65a9b-309">**删除文件**：在 **出现的警告中** 单击"是"后，将立即删除文件。</span><span class="sxs-lookup"><span data-stu-id="65a9b-309">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="65a9b-310">使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="65a9b-310">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="65a9b-311">用于查看和管理隔离邮件和文件的 cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="65a9b-311">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="65a9b-312">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="65a9b-312">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="65a9b-313">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="65a9b-313">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="65a9b-314">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="65a9b-314">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="65a9b-315">[Preview-QuarantineMessage：](/powershell/module/exchange/preview-quarantinemessage)请注意，此 cmdlet 仅适用于邮件，而不是来自 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams 的隔离Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="65a9b-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="65a9b-316">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="65a9b-316">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
