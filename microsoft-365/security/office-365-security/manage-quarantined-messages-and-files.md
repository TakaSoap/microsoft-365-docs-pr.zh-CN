---
title: 以 Office 365 中的管理员身份管理隔离的邮件和文件
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: 管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。 只有管理员可以管理被隔离为恶意软件的邮件、高可信度的网络钓鱼或邮件流规则（传输规则）的结果。
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857068"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="78718-104">以 Office 365 中的管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="78718-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="78718-105">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中，隔离会在 Office 365 组织中保留可能有害或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="78718-106">有关详细信息，请参阅[Office 365 中的隔离](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="78718-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="78718-107">管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="78718-108">只有管理员可以管理被隔离为恶意软件的邮件、高可信度的网络钓鱼或邮件流规则（也称为传输规则）的结果。</span><span class="sxs-lookup"><span data-stu-id="78718-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="78718-109">管理员还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="78718-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="78718-110">具有 Office 365 高级威胁防护（ATP）的组织中的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft 团队中查看、下载和删除隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="78718-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="78718-111">您可以查看和管理安全 & 合规性中心或 PowerShell 中的隔离邮件（Office 365 客户的 Exchange Online PowerShell;适用于独立 EOP 客户的 Exchange Online Protection PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="78718-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="78718-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="78718-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="78718-113">若要打开 Office 365 安全 & 合规性中心，请<https://protection.office.com>转到。</span><span class="sxs-lookup"><span data-stu-id="78718-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="78718-114">若要直接打开隔离页面，请转<https://protection.office.com/quarantine>到。</span><span class="sxs-lookup"><span data-stu-id="78718-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="78718-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="78718-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="78718-116">若要连接到 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="78718-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="78718-117">您需要先分配权限，然后才能以管理员身份管理隔离。权限由 Security & 合规中心中的**隔离**角色控制。</span><span class="sxs-lookup"><span data-stu-id="78718-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="78718-118">默认情况下，将此角色分配给安全 & 合规中心中的 "**组织管理**" （全局管理员）、"**隔离管理员**" 和 "**安全管理员**" 角色组。</span><span class="sxs-lookup"><span data-stu-id="78718-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="78718-119">有关详细信息，请参阅[Office 365 Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="78718-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="78718-120">在被自动删除之前，隔离的邮件将保留默认的一段时间：</span><span class="sxs-lookup"><span data-stu-id="78718-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="78718-121">由反垃圾邮件策略（垃圾邮件、网络钓鱼和批量电子邮件）隔离的邮件：30天。</span><span class="sxs-lookup"><span data-stu-id="78718-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="78718-122">这是默认值和最大值。</span><span class="sxs-lookup"><span data-stu-id="78718-122">This is the default and maximum value.</span></span> <span data-ttu-id="78718-123">若要配置此值，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="78718-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="78718-124">邮件流规则隔离的邮件（规则操作将**邮件传递到托管隔离**）：30天。</span><span class="sxs-lookup"><span data-stu-id="78718-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="78718-125">您不能更改此值。</span><span class="sxs-lookup"><span data-stu-id="78718-125">You can't change this value.</span></span>

  - <span data-ttu-id="78718-126">包含恶意软件的邮件：15天。</span><span class="sxs-lookup"><span data-stu-id="78718-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="78718-127">当邮件从隔离区中过期时，将无法对其进行恢复。</span><span class="sxs-lookup"><span data-stu-id="78718-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="78718-128">使用安全 & 合规性中心管理隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="78718-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="78718-129">查看隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="78718-129">View quarantined email</span></span>

1. <span data-ttu-id="78718-130">在 "安全与合规中心" 中，转到 "**威胁管理** \> **检查** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="78718-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="78718-131">验证 "**隔离视图**" 是否已设置为默认值 "**电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="78718-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="78718-132">您可以通过单击可用的列标题对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="78718-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="78718-133">单击 "**修改列**" 以显示最多七列。</span><span class="sxs-lookup"><span data-stu-id="78718-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="78718-134">默认值用星号（<sup>\*</sup>）标记：</span><span class="sxs-lookup"><span data-stu-id="78718-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="78718-135">**收到**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-136">**给**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-137">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-138">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-139">**以后?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-140">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-141">**不久**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-142">**收件人**</span><span class="sxs-lookup"><span data-stu-id="78718-142">**Recipient**</span></span>

   - <span data-ttu-id="78718-143">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="78718-143">**Message ID**</span></span>

   - <span data-ttu-id="78718-144">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="78718-144">**Policy name**</span></span>

   - <span data-ttu-id="78718-145">**Size**</span><span class="sxs-lookup"><span data-stu-id="78718-145">**Size**</span></span>

   - <span data-ttu-id="78718-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="78718-146">**Direction**</span></span>

   <span data-ttu-id="78718-147">完成后，请单击 "**保存**"，或单击 "**设为默认值**"。</span><span class="sxs-lookup"><span data-stu-id="78718-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="78718-148">若要筛选结果，请单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="78718-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="78718-149">可用的筛选器包括：</span><span class="sxs-lookup"><span data-stu-id="78718-149">The available filters are:</span></span>

   - <span data-ttu-id="78718-150">**过期时间**：根据隔离过期的邮件筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="78718-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="78718-151">**如今**</span><span class="sxs-lookup"><span data-stu-id="78718-151">**Today**</span></span>

     - <span data-ttu-id="78718-152">**接下来2天**</span><span class="sxs-lookup"><span data-stu-id="78718-152">**Next 2 days**</span></span>

     - <span data-ttu-id="78718-153">**接下来7天**</span><span class="sxs-lookup"><span data-stu-id="78718-153">**Next 7 days**</span></span>

     - <span data-ttu-id="78718-154">**Custom**：输入**开始日期**和**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="78718-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="78718-155">**接收时间**：输入**开始日期**和**结束日期**。</span><span class="sxs-lookup"><span data-stu-id="78718-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="78718-156">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="78718-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="78718-157">**Policy**：邮件符合邮件流规则的条件（也称为传输规则）。</span><span class="sxs-lookup"><span data-stu-id="78718-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="78718-158">**批量邮件**</span><span class="sxs-lookup"><span data-stu-id="78718-158">**Bulk**</span></span>

     - <span data-ttu-id="78718-159">**诈骗**</span><span class="sxs-lookup"><span data-stu-id="78718-159">**Phish**</span></span>

     - <span data-ttu-id="78718-160">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="78718-160">**Malware**</span></span>

     - <span data-ttu-id="78718-161">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="78718-161">**Spam**</span></span>

     - <span data-ttu-id="78718-162">**高可信度网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="78718-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="78718-163">**电子邮件收件人**：所有用户或仅发送给你的邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="78718-164">最终用户只能管理发送给他们的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="78718-165">若要清除筛选器，请单击 "**清除**"。</span><span class="sxs-lookup"><span data-stu-id="78718-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="78718-166">若要隐藏筛选器浮出控件，请再次单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="78718-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="78718-167">使用 "**排序结果依据**" （默认情况下为 "**邮件 ID** " 按钮）和相应的值来查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="78718-168">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="78718-168">Wildcards aren't supported.</span></span> <span data-ttu-id="78718-169">您可以按以下值进行搜索：</span><span class="sxs-lookup"><span data-stu-id="78718-169">You can search by the following values:</span></span>

   - <span data-ttu-id="78718-170">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="78718-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="78718-171">例如，使用[邮件跟踪](message-trace-scc.md)查找发送到组织中的用户的邮件，并确定邮件已被隔离而不是传递。</span><span class="sxs-lookup"><span data-stu-id="78718-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="78718-172">确保包含完整的邮件 ID 值，其中可能包含尖括号（\<\>）。</span><span class="sxs-lookup"><span data-stu-id="78718-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="78718-173">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="78718-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="78718-174">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="78718-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="78718-175">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="78718-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="78718-176">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="78718-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="78718-177">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="78718-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="78718-178">输入搜索条件后，单击!["刷新按钮](../media/scc-quarantine-refresh.png) **刷新**" 以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="78718-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="78718-179">找到特定的隔离邮件后，选择该邮件以查看其详细信息，并对其执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="78718-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="78718-180">导出邮件结果</span><span class="sxs-lookup"><span data-stu-id="78718-180">Export message results</span></span>

1. <span data-ttu-id="78718-181">选择你感兴趣的邮件，然后单击 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="78718-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="78718-182">在确认消息中单击 **"是"** ，警告您让浏览器窗口处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="78718-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="78718-183">当您的导出准备就绪后，您可以命名并选择 .csv 文件的下载位置。</span><span class="sxs-lookup"><span data-stu-id="78718-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="78718-184">查看隔离的邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="78718-184">View quarantined message details</span></span>

<span data-ttu-id="78718-185">当您在列表中选择一封电子邮件时，**详细信息**弹出窗格中将显示以下消息详细信息：</span><span class="sxs-lookup"><span data-stu-id="78718-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="78718-186">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="78718-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="78718-187">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="78718-187">**Sender address**</span></span>

- <span data-ttu-id="78718-188">**已接收**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="78718-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="78718-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="78718-189">**Subject**</span></span>

- <span data-ttu-id="78718-190">**隔离原因**：显示邮件是被标识为**垃圾**邮件、**批量**、**网络钓鱼**、与邮件流规则匹配（**传输规则**），还是被标识为包含**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="78718-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="78718-191">**收件人**：如果邮件包含多个收件人，则需要单击 "**预览邮件**" 或 "**查看邮件头**" 以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="78718-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="78718-192">**过期**：将自动和永久从隔离区中删除邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="78718-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="78718-193">**释放位置**：邮件已释放到其中的所有电子邮件地址（如有）。</span><span class="sxs-lookup"><span data-stu-id="78718-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="78718-194">**尚未发布到**：尚未发布邮件的所有电子邮件地址（如果有）。</span><span class="sxs-lookup"><span data-stu-id="78718-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="78718-195">对隔离的电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="78718-195">Take action on quarantined email</span></span>

<span data-ttu-id="78718-196">选择一封邮件后，您有几种方法可用于处理 "**详细信息**" 弹出窗格中的邮件：</span><span class="sxs-lookup"><span data-stu-id="78718-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="78718-197">**释放邮件**：在出现的弹出窗口中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="78718-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="78718-198">**将邮件报告给 Microsoft 进行分析**：默认情况下，此选项处于选中状态，并将错误隔离的邮件以误报的形式报告给 microsoft。</span><span class="sxs-lookup"><span data-stu-id="78718-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="78718-199">如果邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件，则还会向 Microsoft 垃圾邮件分析团队报告该邮件。</span><span class="sxs-lookup"><span data-stu-id="78718-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="78718-200">根据分析的不同，可能会调整服务范围内的垃圾邮件筛选器规则，以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="78718-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="78718-201">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="78718-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="78718-202">**将邮件释放给所有收件人**</span><span class="sxs-lookup"><span data-stu-id="78718-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="78718-203">**将邮件释放给特定收件人**</span><span class="sxs-lookup"><span data-stu-id="78718-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="78718-204">**向其他人发布邮件**</span><span class="sxs-lookup"><span data-stu-id="78718-204">**Release messages to other people**</span></span>

  <span data-ttu-id="78718-205">完成后，请单击 "**释放邮件**"。</span><span class="sxs-lookup"><span data-stu-id="78718-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="78718-206">有关释放邮件的说明：</span><span class="sxs-lookup"><span data-stu-id="78718-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="78718-207">不能多次将邮件释放到同一收件人。</span><span class="sxs-lookup"><span data-stu-id="78718-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="78718-208">只有未收到邮件的收件人才会显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="78718-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="78718-209">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="78718-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="78718-210">若要深入分析标头字段和值，请将邮件头文本复制到剪贴板，然后选择 " **Microsoft 邮件头分析器**" 以转到远程连接分析器（右键单击并选择 "**在新选项卡中打开**"，如果您不想让 Office 365 完成此任务）。</span><span class="sxs-lookup"><span data-stu-id="78718-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="78718-211">将邮件头粘贴到 "邮件头分析器" 部分中的页面上，然后选择 "**分析邮件头**"：</span><span class="sxs-lookup"><span data-stu-id="78718-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="78718-212">**预览邮件**：在出现的弹出窗口中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="78718-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="78718-213">**源视图**：显示已禁用所有链接的邮件正文的 HTML 版本。</span><span class="sxs-lookup"><span data-stu-id="78718-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="78718-214">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="78718-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="78718-215">**从隔离区中删除**：在显示的警告中单击 **"是"** 后，会立即删除邮件，而不会将其发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="78718-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="78718-216">**下载邮件**：在出现的弹出窗口中，选择 "**我了解下载此邮件的风险"** 以以 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="78718-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="78718-217">**提交邮件**：在出现的弹出窗口中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="78718-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="78718-218">**对象类型**：**电子邮件**（默认）、 **URL**或**附件**。</span><span class="sxs-lookup"><span data-stu-id="78718-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="78718-219">**提交格式**：**网络邮件 id** （默认值，在**网络邮件 id**框中对应的值）或**文件**（浏览到本地 .eml 或 .msg 文件）。</span><span class="sxs-lookup"><span data-stu-id="78718-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="78718-220">请注意，如果选择 "**文件**"，然后选择 "**网络邮件 ID**"，则初始值将不再存在。</span><span class="sxs-lookup"><span data-stu-id="78718-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="78718-221">**收件人**：键入邮件的原始收件人，或单击 "**全选**" 以标识所有收件人。</span><span class="sxs-lookup"><span data-stu-id="78718-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="78718-222">也可以单击 "**全选**"，然后有选择地删除各个收件人。</span><span class="sxs-lookup"><span data-stu-id="78718-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="78718-223">**提交原因**：**不应被阻止**（默认），也不应被**阻止**。</span><span class="sxs-lookup"><span data-stu-id="78718-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="78718-224">完成后，请单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="78718-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="78718-225">如果不释放或删除邮件，则在默认的隔离保留期过期后将被删除。</span><span class="sxs-lookup"><span data-stu-id="78718-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="78718-226">对多个隔离的电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="78718-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="78718-227">当您在列表中选择多个隔离邮件（最多为100）时，将显示 "**批量操作**" 浮出控件窗格，您可在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78718-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="78718-228">**释放邮件**：这些选项与您在释放单个邮件时相同，只是不能选择 "**将邮件释放给特定收件人**"。您只能选择 "**将邮件释放给所有收件人**" 或 "**向其他人发布邮件**"。</span><span class="sxs-lookup"><span data-stu-id="78718-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="78718-229">**删除邮件**：在显示的警告中单击 **"是"** 后，将立即删除邮件，而不会将其发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="78718-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="78718-230">完成后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="78718-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="78718-231">仅 ATP：使用安全 & 合规中心管理隔离的文件</span><span class="sxs-lookup"><span data-stu-id="78718-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="78718-232">本节中隔离文件的过程仅适用于 ATP 计划1和计划2订阅者。</span><span class="sxs-lookup"><span data-stu-id="78718-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="78718-233">在具有 ATP 的组织中，管理员可以在 SharePoint Online、OneDrive for Business 和 Microsoft 团队中管理隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="78718-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="78718-234">查看隔离的文件</span><span class="sxs-lookup"><span data-stu-id="78718-234">View quarantined files</span></span>

1. <span data-ttu-id="78718-235">在 "安全与合规中心" 中，转到 "**威胁管理** \> **检查** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="78718-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="78718-236">将已**隔离的视图**更改为默认值**文件**。</span><span class="sxs-lookup"><span data-stu-id="78718-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="78718-237">您可以通过单击可用的列标题对字段进行排序。</span><span class="sxs-lookup"><span data-stu-id="78718-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="78718-238">您可以通过单击可用的列标题对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="78718-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="78718-239">单击 "**修改列**" 以显示最多七列。</span><span class="sxs-lookup"><span data-stu-id="78718-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="78718-240">默认列用星号（<sup>\*</sup>）标记：</span><span class="sxs-lookup"><span data-stu-id="78718-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="78718-241">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-242">**您的位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-243">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-244">**文件 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-245">**文件大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-246">**不久**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-247">**以后?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="78718-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="78718-248">**检测人**</span><span class="sxs-lookup"><span data-stu-id="78718-248">**Detected by**</span></span>

   - <span data-ttu-id="78718-249">**修改时间**</span><span class="sxs-lookup"><span data-stu-id="78718-249">**Modified by time**</span></span>

4. <span data-ttu-id="78718-250">若要筛选结果，请单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="78718-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="78718-251">可用的筛选器包括：</span><span class="sxs-lookup"><span data-stu-id="78718-251">The available filters are:</span></span>

   - <span data-ttu-id="78718-252">**过期时间**：根据隔离过期的邮件筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="78718-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="78718-253">**如今**</span><span class="sxs-lookup"><span data-stu-id="78718-253">**Today**</span></span>

     - <span data-ttu-id="78718-254">**接下来2天**</span><span class="sxs-lookup"><span data-stu-id="78718-254">**Next 2 days**</span></span>

     - <span data-ttu-id="78718-255">**接下来7天**</span><span class="sxs-lookup"><span data-stu-id="78718-255">**Next 7 days**</span></span>

     - <span data-ttu-id="78718-256">自定义日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="78718-256">A custom date/time range.</span></span>

   - <span data-ttu-id="78718-257">**接收时间**</span><span class="sxs-lookup"><span data-stu-id="78718-257">**Received time**</span></span>

   - <span data-ttu-id="78718-258">**隔离原因**：唯一的可用值是**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="78718-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="78718-259">找到特定的隔离文件后，选择该文件查看其详细信息，并对其执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="78718-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="78718-260">导出文件结果</span><span class="sxs-lookup"><span data-stu-id="78718-260">Export file results</span></span>

1. <span data-ttu-id="78718-261">选择您感兴趣的文件，然后单击 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="78718-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="78718-262">在确认消息中单击 **"是"** ，警告您让浏览器窗口处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="78718-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="78718-263">当您的导出准备就绪后，您可以命名并选择 .csv 文件的下载位置。</span><span class="sxs-lookup"><span data-stu-id="78718-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="78718-264">查看隔离的文件详细信息</span><span class="sxs-lookup"><span data-stu-id="78718-264">View quarantined file details</span></span>

<span data-ttu-id="78718-265">当您选择列表中的某个文件时，**详细信息**弹出窗格中将显示以下文件详细信息：</span><span class="sxs-lookup"><span data-stu-id="78718-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="78718-266">**文件名**</span><span class="sxs-lookup"><span data-stu-id="78718-266">**File Name**</span></span>

- <span data-ttu-id="78718-267">**文件 url**：定义文件位置的 url （例如，在 SharePoint Online 中）。</span><span class="sxs-lookup"><span data-stu-id="78718-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="78718-268">**在上检测到的恶意内容**文件被隔离的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="78718-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="78718-269">**过期**时间：将从隔离区中删除文件的日期。</span><span class="sxs-lookup"><span data-stu-id="78718-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="78718-270">**检测依据**： ATP （高级威胁防护）或 Microsoft 反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="78718-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="78718-271">**以后?**</span><span class="sxs-lookup"><span data-stu-id="78718-271">**Released?**</span></span>

- <span data-ttu-id="78718-272">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="78718-272">**Malware Name**</span></span>

- <span data-ttu-id="78718-273">**文档 ID**：文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="78718-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="78718-274">**文件大小**：以千字节（kb）为单位。</span><span class="sxs-lookup"><span data-stu-id="78718-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="78718-275">**组织**您的组织的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="78718-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="78718-276">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="78718-276">**Last modified**</span></span>

- <span data-ttu-id="78718-277">**修改者**：上次修改文件的用户。</span><span class="sxs-lookup"><span data-stu-id="78718-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="78718-278">**安全哈希算法 256-位（SHA-256）值**：您可以使用此哈希值来标识其他信誉存储区中的文件或环境中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="78718-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="78718-279">对隔离的文件执行操作</span><span class="sxs-lookup"><span data-stu-id="78718-279">Take action on quarantined files</span></span>

<span data-ttu-id="78718-280">选择列表中的文件时，可以对 "**详细信息**" 弹出窗口中的文件执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78718-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="78718-281">**释放文件**：选择（默认）或**将报告文件取消选择 Microsoft 进行分析**，然后单击 "**释放文件**"。</span><span class="sxs-lookup"><span data-stu-id="78718-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="78718-282">**下载文件**</span><span class="sxs-lookup"><span data-stu-id="78718-282">**Download file**</span></span>

- <span data-ttu-id="78718-283">**从隔离区中删除文件**</span><span class="sxs-lookup"><span data-stu-id="78718-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="78718-284">如果不释放或删除这些文件，则在默认的隔离保留期过期后，这些文件将被删除。</span><span class="sxs-lookup"><span data-stu-id="78718-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="78718-285">对多个隔离文件执行的操作</span><span class="sxs-lookup"><span data-stu-id="78718-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="78718-286">当您在列表中选择多个隔离文件（最多为100）时，将显示 "**批量操作**" 浮出控件窗格，您可在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78718-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="78718-287">**释放文件**</span><span class="sxs-lookup"><span data-stu-id="78718-287">**Release files**</span></span>

- <span data-ttu-id="78718-288">**删除文件**：在显示的警告中单击 **"是"** 后，会立即删除文件。</span><span class="sxs-lookup"><span data-stu-id="78718-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="78718-289">完成后，单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="78718-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="78718-290">使用 Exchange Online PowerShell 或独立 Exchange Online Protection PowerShell 查看和管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="78718-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="78718-291">用于查看和管理隔离区中的邮件和文件的 cmdlet 为：</span><span class="sxs-lookup"><span data-stu-id="78718-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="78718-292">删除-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="78718-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="78718-293">Export-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="78718-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="78718-294">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="78718-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="78718-295">[Preview-get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)：请注意，此 cmdlet 仅适用于邮件，而不适用于 SharePoint Online、OneDrive for Business 或团队的 ATP 中的恶意软件文件。</span><span class="sxs-lookup"><span data-stu-id="78718-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="78718-296">发布-Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="78718-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
