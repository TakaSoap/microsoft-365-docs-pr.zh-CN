---
title: 以管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
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
description: 管理员可以了解如何在 Exchange Online Protection 和 EOP (中查看和管理) 。 使用 Microsoft Defender for Office 365 的组织中管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离文件。
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659982"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="e8881-104">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="e8881-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e8881-105">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e8881-106">有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e8881-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e8881-107">管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e8881-108">只有管理员才能管理作为恶意软件、高可信度网络钓鱼或邮件流规则隔离的邮件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e8881-109">管理员还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="e8881-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e8881-110">使用 Microsoft Defender for Office 365 的组织中管理员还可以查看、下载和删除 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的隔离文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e8881-111">您可以在安全 &与合规中心或 PowerShell (Exchange Online PowerShell 中查看和管理隔离邮件，这些组织在 Exchange Online 中拥有邮箱的 Microsoft 365 组织;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8881-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e8881-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8881-113">若要打开安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="e8881-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e8881-114">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="e8881-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e8881-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e8881-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e8881-116">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e8881-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e8881-117">必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：</span><span class="sxs-lookup"><span data-stu-id="e8881-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e8881-118">若要对所有用户的隔离邮件采取措施，你需要是组织管理、**安全** 管理员或 **隔离管理员** 角色 <sup>\*</sup> 组的成员。</span><span class="sxs-lookup"><span data-stu-id="e8881-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="e8881-119">若要对所有用户的隔离邮件进行只读访问，您需要是全局读者或安全读者 **角色组的成员**。 </span><span class="sxs-lookup"><span data-stu-id="e8881-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e8881-120">有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e8881-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e8881-121">**注意**：</span><span class="sxs-lookup"><span data-stu-id="e8881-121">**Notes**:</span></span>

  - <span data-ttu-id="e8881-122">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="e8881-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e8881-123">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="e8881-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e8881-124">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="e8881-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="e8881-125"><sup>\*</sup>隔离 **管理员角色** 组的成员还需要是 Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中清洁管理角色组的成员，才能在 Exchange Online PowerShell 中执行隔离过程。</span><span class="sxs-lookup"><span data-stu-id="e8881-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="e8881-126">在自动删除隔离邮件之前，这些邮件会保留一段默认时间：</span><span class="sxs-lookup"><span data-stu-id="e8881-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="e8881-127">由反垃圾邮件策略隔离的邮件的 30 (垃圾邮件、网络钓鱼和批量电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="e8881-128">这是默认值和最大值。</span><span class="sxs-lookup"><span data-stu-id="e8881-128">This is the default and maximum value.</span></span> <span data-ttu-id="e8881-129">若要将 (此值) ，请参阅["配置反垃圾邮件策略"。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e8881-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e8881-130">包含恶意软件的邮件的 15 天。</span><span class="sxs-lookup"><span data-stu-id="e8881-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="e8881-131">对于由 ATP 在 Office 365 的 Defender 中隔离的 SharePoint、OneDrive 和 Microsoft Teams 的文件，为 15 天。</span><span class="sxs-lookup"><span data-stu-id="e8881-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="e8881-132">当邮件从隔离区过期时，你无法恢复它。</span><span class="sxs-lookup"><span data-stu-id="e8881-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e8881-133">使用安全&合规中心管理隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="e8881-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e8881-134">查看隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="e8881-134">View quarantined email</span></span>

1. <span data-ttu-id="e8881-135">在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“隔离”。</span><span class="sxs-lookup"><span data-stu-id="e8881-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e8881-136">验证 **隔离视图** 是否设置为默认值 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="e8881-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e8881-137">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="e8881-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e8881-138">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="e8881-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e8881-139">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="e8881-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e8881-140">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-141">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-142">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-143">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-144">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-145">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-146">**Expires**</span><span class="sxs-lookup"><span data-stu-id="e8881-146">**Expires**</span></span>
   - <span data-ttu-id="e8881-147">**收件人**</span><span class="sxs-lookup"><span data-stu-id="e8881-147">**Recipient**</span></span>
   - <span data-ttu-id="e8881-148">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="e8881-148">**Message ID**</span></span>
   - <span data-ttu-id="e8881-149">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="e8881-149">**Policy name**</span></span>
   - <span data-ttu-id="e8881-150">**大小**</span><span class="sxs-lookup"><span data-stu-id="e8881-150">**Size**</span></span>
   - <span data-ttu-id="e8881-151">**方向**</span><span class="sxs-lookup"><span data-stu-id="e8881-151">**Direction**</span></span>

   <span data-ttu-id="e8881-152">完成后，单击“保存”单击“设置为默认设置”。</span><span class="sxs-lookup"><span data-stu-id="e8881-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e8881-153">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="e8881-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e8881-154">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="e8881-154">The available filters are:</span></span>

   - <span data-ttu-id="e8881-155">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="e8881-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e8881-156">**今天**</span><span class="sxs-lookup"><span data-stu-id="e8881-156">**Today**</span></span>
     - <span data-ttu-id="e8881-157">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="e8881-157">**Next 2 days**</span></span>
     - <span data-ttu-id="e8881-158">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="e8881-158">**Next 7 days**</span></span>
     - <span data-ttu-id="e8881-159">**自定义**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="e8881-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e8881-160">**接收时间**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="e8881-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e8881-161">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="e8881-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="e8881-162">**策略**：邮件符合邮件流规则的条件 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="e8881-163">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="e8881-163">**Bulk**</span></span>
     - <span data-ttu-id="e8881-164">**网络钓鱼**：垃圾邮件筛选器裁定是 **网络钓鱼电子邮件** 或防钓鱼保护隔离了邮件 ([欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)或模拟 [保护) 。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e8881-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="e8881-165">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e8881-165">**Malware**</span></span>
     - <span data-ttu-id="e8881-166">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="e8881-166">**Spam**</span></span>
     - <span data-ttu-id="e8881-167">**高可信度网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="e8881-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e8881-168">**策略类型**：按策略类型筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="e8881-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="e8881-169">**反恶意软件策略**</span><span class="sxs-lookup"><span data-stu-id="e8881-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="e8881-170">**安全附件策略**</span><span class="sxs-lookup"><span data-stu-id="e8881-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="e8881-171">**反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="e8881-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="e8881-172">**托管内容筛选器策略**（反垃圾邮件策略）</span><span class="sxs-lookup"><span data-stu-id="e8881-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="e8881-173">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="e8881-173">**Transport rule**</span></span>

   - <span data-ttu-id="e8881-174">**电子邮件收件人**：所有用户或仅发送给您的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e8881-175">最终用户只能管理发送给他们的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e8881-176">若要清除筛选器，请单击“清除”。</span><span class="sxs-lookup"><span data-stu-id="e8881-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e8881-177">若要隐藏筛选器浮出控件，请再次单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="e8881-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e8881-178">使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e8881-179">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="e8881-179">Wildcards aren't supported.</span></span> <span data-ttu-id="e8881-180">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="e8881-180">You can search by the following values:</span></span>

   - <span data-ttu-id="e8881-181">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e8881-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="e8881-182">例如 [，使用邮件](message-trace-scc.md) 跟踪来查找发送给您组织中用户的邮件，并确定邮件是隔离的，而不是传递的。</span><span class="sxs-lookup"><span data-stu-id="e8881-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e8881-183">请务必包括完整的邮件 ID 值，其中可能包含尖括号 \<\> () 。</span><span class="sxs-lookup"><span data-stu-id="e8881-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e8881-184">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="e8881-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e8881-185">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e8881-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e8881-186">**策略名称**：使用邮件的完整策略名称。</span><span class="sxs-lookup"><span data-stu-id="e8881-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="e8881-187">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e8881-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e8881-188">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e8881-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e8881-189">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="e8881-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e8881-190">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e8881-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e8881-191">**策略名称**：负责隔离邮件的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="e8881-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="e8881-192">输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="e8881-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e8881-193">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="e8881-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e8881-194">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="e8881-194">View quarantined message details</span></span>

<span data-ttu-id="e8881-195">选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="e8881-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e8881-196">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e8881-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e8881-197">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="e8881-197">**Sender address**</span></span>

- <span data-ttu-id="e8881-198">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="e8881-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e8881-199">**主题**</span><span class="sxs-lookup"><span data-stu-id="e8881-199">**Subject**</span></span>

- <span data-ttu-id="e8881-200">**隔离原因**： 显示邮件被标识为垃圾邮件 **、\*\*\*\*批量邮件\*\*\*\*、** 钓鱼邮件 、 匹配邮件流规则 (**传输** 规则) 或标识为包含 **恶意软件。**</span><span class="sxs-lookup"><span data-stu-id="e8881-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e8881-201">**收件人计数**</span><span class="sxs-lookup"><span data-stu-id="e8881-201">**Recipient count**</span></span>

- <span data-ttu-id="e8881-202">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="e8881-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e8881-203">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="e8881-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e8881-204">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="e8881-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e8881-205">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="e8881-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e8881-206">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="e8881-206">Take action on quarantined email</span></span>

<span data-ttu-id="e8881-207">选择邮件后，您可以在"详细信息"飞出窗格中选择对邮件执行哪些操作的选项： </span><span class="sxs-lookup"><span data-stu-id="e8881-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e8881-208">**释放消息**：在出现的飞出窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="e8881-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e8881-209">**将邮件报告给 Microsoft 进行分析**：默认情况下选中此选项，将错误隔离的邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="e8881-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e8881-210">如果邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件，邮件也会报告给 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="e8881-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e8881-211">根据分析，可能会调整服务范围内的垃圾邮件筛选规则以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="e8881-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e8881-212">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e8881-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="e8881-213">**将邮件释放到所有收件人**</span><span class="sxs-lookup"><span data-stu-id="e8881-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="e8881-214">**将邮件释放到特定收件人**</span><span class="sxs-lookup"><span data-stu-id="e8881-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="e8881-215">**将邮件释放给其他人**：请注意，不支持将恶意软件邮件释放给原始收件人外的其他人员。</span><span class="sxs-lookup"><span data-stu-id="e8881-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="e8881-216">完成后，单击“释放邮件”。</span><span class="sxs-lookup"><span data-stu-id="e8881-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e8881-217">有关释放邮件的注释：</span><span class="sxs-lookup"><span data-stu-id="e8881-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e8881-218">不能多次向同一收件人释放邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="e8881-219">只有尚未收到邮件的收件人将显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="e8881-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e8881-220">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="e8881-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e8881-221">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。</span><span class="sxs-lookup"><span data-stu-id="e8881-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e8881-222">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：</span><span class="sxs-lookup"><span data-stu-id="e8881-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e8881-223">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e8881-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e8881-224">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="e8881-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="e8881-225">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="e8881-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e8881-226">**从隔离** 区删除：在出现的警告中单击"是"后，将立即删除该邮件，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="e8881-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e8881-227">**下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="e8881-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e8881-228">**提交邮件**：在出现的飞出窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="e8881-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e8881-229">**对象类型**： **电子邮件** (默认 **) 、URL** 或 **附件**。</span><span class="sxs-lookup"><span data-stu-id="e8881-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e8881-230">提交 **格式**：网络 (**ID** 为默认值，"网络消息 **ID"** 框中的相应值 **) 或文件** (浏览到本地 .eml 或 .msg 文件) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e8881-231">请注意， **如果选择"文件** "，然后选择 **"网络消息 ID"，** 则初始值将消失。</span><span class="sxs-lookup"><span data-stu-id="e8881-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="e8881-232">**收件人：** 在租用邮件的一个原始收件人时键入， **或单击"** 全选"以标识所有收件人。</span><span class="sxs-lookup"><span data-stu-id="e8881-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e8881-233">还可以单击"全 **选"，** 然后有选择地删除各个收件人。</span><span class="sxs-lookup"><span data-stu-id="e8881-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e8881-234">**提交原因\*\*\*\*：不应被** 阻止 (默认) **应已被阻止**。</span><span class="sxs-lookup"><span data-stu-id="e8881-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e8881-235">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="e8881-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e8881-236">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="e8881-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e8881-237">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="e8881-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e8881-238">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8881-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e8881-239">**释放邮件**：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。</span><span class="sxs-lookup"><span data-stu-id="e8881-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e8881-240">请考虑以下方案：john@gmail.com向用户发送faith@contoso.com john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e8881-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="e8881-241">Gmail 将此邮件分为两个副本，这两个副本在 Microsoft 中均作为网络钓鱼路由到隔离区。</span><span class="sxs-lookup"><span data-stu-id="e8881-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="e8881-242">管理员将这两条消息都释放到admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e8881-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="e8881-243">将传递到达管理邮箱的第一个释放的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="e8881-244">第二个释放的邮件标识为重复传递并跳过。</span><span class="sxs-lookup"><span data-stu-id="e8881-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="e8881-245">如果邮件具有相同的邮件 ID 和接收时间，则邮件被标识为重复邮件。</span><span class="sxs-lookup"><span data-stu-id="e8881-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="e8881-246">**删除邮件**：在出现的警告中单击"是"后，将立即删除这些邮件，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="e8881-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e8881-247">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="e8881-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e8881-248">仅适用于 Office 365 的 Microsoft Defender：使用安全与&中心管理隔离的文件</span><span class="sxs-lookup"><span data-stu-id="e8881-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e8881-249">本部分中隔离文件的过程仅适用于 Microsoft Defender for Office 365 计划 1 和计划 2 订阅者。</span><span class="sxs-lookup"><span data-stu-id="e8881-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e8881-250">在具有 Defender for Office 365 的组织中，管理员可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中管理隔离文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="e8881-251">若要为这些文件启用保护，请参阅启用[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP。](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e8881-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e8881-252">查看隔离文件</span><span class="sxs-lookup"><span data-stu-id="e8881-252">View quarantined files</span></span>

1. <span data-ttu-id="e8881-253">在安全与合规中心内，依次转到“威胁管理”\>“审阅”\>“隔离”。</span><span class="sxs-lookup"><span data-stu-id="e8881-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e8881-254">将 **隔离视图更改为** 值 **文件**。</span><span class="sxs-lookup"><span data-stu-id="e8881-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="e8881-255">可以通过单击可用列标题对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="e8881-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e8881-256">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="e8881-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e8881-257">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="e8881-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e8881-258">默认列标有星号 <sup>\*</sup> () ：</span><span class="sxs-lookup"><span data-stu-id="e8881-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e8881-259">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-260">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-261">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-262">**文件 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-263">**文件大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-264">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-265">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e8881-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e8881-266">**检测者**</span><span class="sxs-lookup"><span data-stu-id="e8881-266">**Detected by**</span></span>
   - <span data-ttu-id="e8881-267">**按时间修改**</span><span class="sxs-lookup"><span data-stu-id="e8881-267">**Modified by time**</span></span>

4. <span data-ttu-id="e8881-268">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="e8881-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e8881-269">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="e8881-269">The available filters are:</span></span>

   - <span data-ttu-id="e8881-270">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="e8881-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e8881-271">**今天**</span><span class="sxs-lookup"><span data-stu-id="e8881-271">**Today**</span></span>
     - <span data-ttu-id="e8881-272">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="e8881-272">**Next 2 days**</span></span>
     - <span data-ttu-id="e8881-273">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="e8881-273">**Next 7 days**</span></span>
     - <span data-ttu-id="e8881-274">自定义日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="e8881-274">A custom date/time range.</span></span>
   - <span data-ttu-id="e8881-275">**接收时间**</span><span class="sxs-lookup"><span data-stu-id="e8881-275">**Received time**</span></span>
   - <span data-ttu-id="e8881-276">**隔离原因**：唯一可用的值是 **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="e8881-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="e8881-277">**策略类型**</span><span class="sxs-lookup"><span data-stu-id="e8881-277">**Policy type**</span></span>

<span data-ttu-id="e8881-278">找到特定的隔离文件后，选择该文件以查看有关该文件的详细信息， (例如查看、释放、下载或删除邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e8881-279">查看隔离文件详细信息</span><span class="sxs-lookup"><span data-stu-id="e8881-279">View quarantined file details</span></span>

<span data-ttu-id="e8881-280">在列表中选择文件时，"详细信息"飞出窗格中会显示 **以下文件详细信息** ：</span><span class="sxs-lookup"><span data-stu-id="e8881-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e8881-281">**文件名**</span><span class="sxs-lookup"><span data-stu-id="e8881-281">**File Name**</span></span>
- <span data-ttu-id="e8881-282">**文件 URL：** 用于定义文件位置的 URL (例如，在 SharePoint Online) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="e8881-283">**检测到的恶意内容** 文件被隔离的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="e8881-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="e8881-284">**过期**： 文件将从隔离区中删除的日期。</span><span class="sxs-lookup"><span data-stu-id="e8881-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="e8881-285">**检测者**：Defender for Office 365 或 Microsoft 的反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="e8881-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="e8881-286">**释放?**</span><span class="sxs-lookup"><span data-stu-id="e8881-286">**Released?**</span></span>
- <span data-ttu-id="e8881-287">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="e8881-287">**Malware Name**</span></span>
- <span data-ttu-id="e8881-288">**文档 ID：** 文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e8881-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="e8881-289">**文件大小：** 以 KB 为单位 (KB) 。</span><span class="sxs-lookup"><span data-stu-id="e8881-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="e8881-290">**组织** 组织的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e8881-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="e8881-291">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="e8881-291">**Last modified**</span></span>
- <span data-ttu-id="e8881-292">**修改者**：上次修改文件的用户。</span><span class="sxs-lookup"><span data-stu-id="e8881-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="e8881-293">安全哈希算法 **256 位 (SHA-256) 值**：可以使用此哈希值来标识其他信誉存储或环境中其他位置的文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e8881-294">对隔离文件采取操作</span><span class="sxs-lookup"><span data-stu-id="e8881-294">Take action on quarantined files</span></span>

<span data-ttu-id="e8881-295">在列表中选择文件时，可以在"详细信息"飞出窗格中对该文件执行以下操作： </span><span class="sxs-lookup"><span data-stu-id="e8881-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e8881-296">**发布文件**： (默认) 将报告文件取消选择 **给 Microsoft** 进行分析，然后单击"发布 **文件"。**</span><span class="sxs-lookup"><span data-stu-id="e8881-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="e8881-297">**下载文件**</span><span class="sxs-lookup"><span data-stu-id="e8881-297">**Download file**</span></span>
- <span data-ttu-id="e8881-298">**从隔离区删除文件**</span><span class="sxs-lookup"><span data-stu-id="e8881-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="e8881-299">如果未释放或删除文件，将在默认隔离保留期过期后删除这些文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e8881-300">对多个隔离文件的操作</span><span class="sxs-lookup"><span data-stu-id="e8881-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e8881-301">当您在列表中选择多个隔离 (最多 100) 时，将显示批量操作飞出窗格，您可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8881-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e8881-302">**发布文件**</span><span class="sxs-lookup"><span data-stu-id="e8881-302">**Release files**</span></span>
- <span data-ttu-id="e8881-303">**删除文件**：在 **出现的警告中** 单击"是"后，将立即删除文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e8881-304">使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="e8881-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e8881-305">用于查看和管理隔离邮件和文件的 cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="e8881-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e8881-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e8881-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="e8881-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e8881-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="e8881-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e8881-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="e8881-309">[Preview-QuarantineMessage：](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)请注意，此 cmdlet 仅适用于邮件，而不是来自 ATP for SharePoint Online、OneDrive for Business 或 Teams 的恶意软件文件。</span><span class="sxs-lookup"><span data-stu-id="e8881-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e8881-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e8881-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
