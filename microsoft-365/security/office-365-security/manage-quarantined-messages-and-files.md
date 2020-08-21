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
description: 管理员可以了解如何查看和管理所有用户的已在 Exchange Online Protection 邮箱运行 () 。 组织中使用 Office 365 高级威胁防护 (Office 365 ATP) 的管理员也可以管理 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的隔离文件。
ms.openlocfilehash: 5da67f15a933694c1aef059ff18945122e3ee2e8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827059"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="3fbb7-104">在 EOP 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="3fbb7-105">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="3fbb7-106">有关详细信息，请参阅 [EOP 中隔离的电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="3fbb7-107">管理员可以查看、释放和删除所有用户的所有类型的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="3fbb7-108">只有管理员可以管理被隔离为恶意软件或高可信度钓鱼的邮件，或者当邮件流规则或也称为传输规则 () 而产生的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3fbb7-109">管理员还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="3fbb7-110">组织中使用 Office 365 预防威胁防护 (Office 365 ATP) 的管理员还可以在 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中查看、下载和删除已隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="3fbb7-111">您可以在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (Exchange Online PowerShell 中查看和管理隔离的邮件;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3fbb7-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3fbb7-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3fbb7-113">若要打开安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="3fbb7-114">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="3fbb7-115">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3fbb7-116">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3fbb7-117">你需要授予权限，才能以管理员身份管理隔离邮箱。这些权限由安全与合规中心 **内的** 隔离&角色控制。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="3fbb7-118">默认情况下，会在安全与合规中心 (**组织**管理) **Quarantine Administrator** (全局管理员委派委派、隔离管理员**Security Administrator**&安全管理员角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="3fbb7-119">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3fbb7-120">隔离的邮件在被自动删除之前会默认保留一段时间：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="3fbb7-121">反垃圾邮件策略隔离的邮件会 (垃圾邮件、网络钓鱼和批量电子邮件功能) ： 30 天。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="3fbb7-122">此为默认值和最大值。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-122">This is the default and maximum value.</span></span> <span data-ttu-id="3fbb7-123">要配置此值，请参阅["配置反垃圾邮件策略"。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3fbb7-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="3fbb7-124">包含恶意软件的邮件：15 天。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="3fbb7-125">当邮件从隔离到期时，您无法恢复它。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="3fbb7-126">使用安全&与合规中心管理隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="3fbb7-127">查看隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-127">View quarantined email</span></span>

1. <span data-ttu-id="3fbb7-128">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“隔离”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="3fbb7-129">验证 **是否将"查看隔离"** 设置为默认值 **电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="3fbb7-130">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="3fbb7-131">单击“修改列”\*\*\*\* 最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="3fbb7-132">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="3fbb7-133">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-134">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-135">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-136">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-137">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-138">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-139">**收件人**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-139">**Recipient**</span></span>

   - <span data-ttu-id="3fbb7-140">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-140">**Message ID**</span></span>

   - <span data-ttu-id="3fbb7-141">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-141">**Policy name**</span></span>

   - <span data-ttu-id="3fbb7-142">**大小**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-142">**Size**</span></span>

   - <span data-ttu-id="3fbb7-143">**方向**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-143">**Direction**</span></span>

   <span data-ttu-id="3fbb7-144">完成后，单击“保存”\*\*\*\* 单击“设置为默认设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="3fbb7-145">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="3fbb7-146">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-146">The available filters are:</span></span>

   - <span data-ttu-id="3fbb7-147">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="3fbb7-148">**今天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-148">**Today**</span></span>

     - <span data-ttu-id="3fbb7-149">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-149">**Next 2 days**</span></span>

     - <span data-ttu-id="3fbb7-150">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-150">**Next 7 days**</span></span>

     - <span data-ttu-id="3fbb7-151">**自定义**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3fbb7-152">**接收时间**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3fbb7-153">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="3fbb7-154">**策略**：该邮件符合邮件流规则条件， (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="3fbb7-155">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-155">**Bulk**</span></span>

     - <span data-ttu-id="3fbb7-156">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-156">**Phish**</span></span>

     - <span data-ttu-id="3fbb7-157">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-157">**Malware**</span></span>

     - <span data-ttu-id="3fbb7-158">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-158">**Spam**</span></span>

     - <span data-ttu-id="3fbb7-159">**高可信度钓鱼邮件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="3fbb7-160">**电子邮件收件人**：所有用户或仅发送给您的邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="3fbb7-161">最终用户只能管理发送给他们的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="3fbb7-162">若要清除筛选器，请单击“清除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="3fbb7-163">若要隐藏筛选器浮出控件，请再次单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="3fbb7-164">使用“结果排序依据”\*\*\*\*（默认为“邮件 ID”\*\*\*\* 按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="3fbb7-165">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-165">Wildcards aren't supported.</span></span> <span data-ttu-id="3fbb7-166">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-166">You can search by the following values:</span></span>

   - <span data-ttu-id="3fbb7-167">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="3fbb7-168">例如，您使用 [邮件](message-trace-scc.md) 跟踪来查找发送给组织内用户的邮件，且您确定邮件已隔离而不是传递。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="3fbb7-169">请务必包含完整邮件 ID 值，该值可能包含包含用于发送此 \<\> () 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="3fbb7-170">例如：`<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="3fbb7-171">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="3fbb7-172">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="3fbb7-173">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="3fbb7-174">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="3fbb7-175">输入搜索条件后，单击“刷新”\*\*\*\* ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="3fbb7-176">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="3fbb7-177">导出邮件结果</span><span class="sxs-lookup"><span data-stu-id="3fbb7-177">Export message results</span></span>

1. <span data-ttu-id="3fbb7-178">选择你有意访问的邮件，然后单击“导出结果”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="3fbb7-179">在警告你不要关闭浏览器窗口的确认消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="3fbb7-180">在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="3fbb7-181">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="3fbb7-181">View quarantined message details</span></span>

<span data-ttu-id="3fbb7-182">选择列表中的电子邮件后，可以在“详细信息”\*\*\*\* 浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fbb7-183">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="3fbb7-184">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-184">**Sender address**</span></span>

- <span data-ttu-id="3fbb7-185">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="3fbb7-186">**主题**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-186">**Subject**</span></span>

- <span data-ttu-id="3fbb7-187">**隔离原因：** 显示邮件是被标识**为垃圾邮件、** 批量、网络**钓**鱼邮件、匹配**Bulk**邮件流规则 (**传输规则**) 还是被标识为包含"恶意软件 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="3fbb7-188">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”\*\*\*\* 或“查看邮件头”\*\*\*\*，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="3fbb7-189">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="3fbb7-190">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="3fbb7-191">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="3fbb7-192">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="3fbb7-192">Take action on quarantined email</span></span>

<span data-ttu-id="3fbb7-193">选择邮件后，"详细信息"浮出控件窗格中有几个 **操作适用于这些** 邮件的选项：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fbb7-194">**释放**邮件：在显示的浮出控件窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="3fbb7-195">**向 Microsoft 报告邮件以供**分析：默认情况下该选项处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="3fbb7-196">如果邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件，则也会向 Microsoft 垃圾邮件分析团队报告该邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="3fbb7-197">根据具体分析，可能会调整服务范围内垃圾邮件筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="3fbb7-198">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="3fbb7-199">**将邮件释放给所有收件人**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="3fbb7-200">**将邮件释放给特定收件人**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="3fbb7-201">**向其他用户发布邮件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-201">**Release messages to other people**</span></span>

  <span data-ttu-id="3fbb7-202">完成后，单击“释放邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="3fbb7-203">关于发行邮件的注释：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="3fbb7-204">您不能将邮件释放多次，您不能将邮件释放到同一收件人。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="3fbb7-205">只有未收到此邮件的收件人会显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="3fbb7-206">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="3fbb7-207">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”\*\*\*\*，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="3fbb7-208">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="3fbb7-209">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="3fbb7-210">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="3fbb7-211">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="3fbb7-212">**从隔离中删除：** 在出现的警告 **中单击"是** "后，系统会立即删除邮件，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="3fbb7-213">**下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”\*\*\*\*，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="3fbb7-214">**提交邮件**：在显示的浮出控件窗格中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="3fbb7-215">**对象类型\*\*\*\*：电子邮件** (默认) **URL**或**附件**。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="3fbb7-216">**提交格式**：**默认情况下，" (ID"** 框中具有相应值) **Network Message ID\*\*\*\*或者"** 文件" (浏览到本地 .eml 或 .msg 文件) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="3fbb7-217">请注意，如果您选择" **文件"** 并选择" **网络消息 ID"，** 则初始值将会不存在。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="3fbb7-218">**收件人**：在邮件的一个原始收件人处键入，或单击" **选择全部收件人** "以识别所有收件人。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="3fbb7-219">也可以单击" **选择全部"，** 然后选择性地删除各个收件人。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="3fbb7-220">**提交原因：\*\*\*\*不应在默认设置** (阻止) ，**或已被阻止**。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="3fbb7-221">完成后，请单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="3fbb7-222">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="3fbb7-223">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="3fbb7-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="3fbb7-224">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”\*\*\*\* 浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="3fbb7-225">**释放邮件**：除了无法选择“将邮件释放给特定收件人”\*\*\*\* 之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”\*\*\*\* 或“将邮件释放给其他用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3fbb7-226">假设应用场景如下：john@gmail.com向当前情况faith@contoso.comjohn@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="3fbb7-227">Gmail 会将此邮件放入两个副本中，这些副本都在 Microsoft 都路由到隔离的网络钓鱼中。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="3fbb7-228">管理员将这两种消息均发布以admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="3fbb7-229">第一封达到管理员邮箱的已发布邮件将送达。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="3fbb7-230">第二封已释放的邮件标识为重复传递，并跳过。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="3fbb7-231">如果邮件 ID 和接收时间相同，则邮件被标识为重复项。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="3fbb7-232">**删除邮件**：当你在显示的警告中单击“是”\*\*\*\* 后，邮件会立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="3fbb7-233">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="3fbb7-234">仅 ATP：& 使用安全与合规中心管理隔离的文件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="3fbb7-235">本节中隔离文件的过程仅适用于 ATP 计划 1 和计划 2 订阅者。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="3fbb7-236">在具有 ATP 的组织中，管理员可以管理 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中的隔离文件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="3fbb7-237">查看隔离的文件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-237">View quarantined files</span></span>

1. <span data-ttu-id="3fbb7-238">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“隔离”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="3fbb7-239">**将隔离的视图**更改为默认值**文件**。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="3fbb7-240">通过单击可用列标题，可以对字段排序。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="3fbb7-241">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="3fbb7-242">单击“修改列”\*\*\*\* 最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="3fbb7-243">默认列用星号标记为 <sup>\*</sup> () ：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="3fbb7-244">**用户**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-245">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-246">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-247">**文件 URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-248">**文件大小**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-249">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-250">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3fbb7-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="3fbb7-251">**检测者**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-251">**Detected by**</span></span>

   - <span data-ttu-id="3fbb7-252">**按时间修改**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-252">**Modified by time**</span></span>

4. <span data-ttu-id="3fbb7-253">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="3fbb7-254">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-254">The available filters are:</span></span>

   - <span data-ttu-id="3fbb7-255">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="3fbb7-256">**今天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-256">**Today**</span></span>

     - <span data-ttu-id="3fbb7-257">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-257">**Next 2 days**</span></span>

     - <span data-ttu-id="3fbb7-258">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-258">**Next 7 days**</span></span>

     - <span data-ttu-id="3fbb7-259">自定义日期/时间范围。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-259">A custom date/time range.</span></span>

   - <span data-ttu-id="3fbb7-260">**接收时间**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-260">**Received time**</span></span>

   - <span data-ttu-id="3fbb7-261">**隔离原因：唯一**可用的值为**Malware。**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="3fbb7-262">找到特定的隔离文件后，选择该文件以查看它的详细信息，并对其执行操作 (例如，查看、释放、下载或删除邮件) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="3fbb7-263">导出文件结果</span><span class="sxs-lookup"><span data-stu-id="3fbb7-263">Export file results</span></span>

1. <span data-ttu-id="3fbb7-264">选择你有兴趣的文件，并单击"导出**结果"。**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="3fbb7-265">在警告你不要关闭浏览器窗口的确认消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="3fbb7-266">在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="3fbb7-267">查看隔离文件详细信息</span><span class="sxs-lookup"><span data-stu-id="3fbb7-267">View quarantined file details</span></span>

<span data-ttu-id="3fbb7-268">选择列表中的文件后，"详细信息"浮出控件窗格 **会显示** 以下文件详细信息：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fbb7-269">**文件名**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-269">**File Name**</span></span>

- <span data-ttu-id="3fbb7-270">**文件 URL：** 定义文件位置的 URL (SharePoint Online 站点) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="3fbb7-271">**检测到的恶意内容** 文件隔离的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="3fbb7-272">**过期**：从隔离区删除文件的日期。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="3fbb7-273">**ErP 检测到**：ATP (安全) Microsoft 的反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="3fbb7-274">**释放?**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-274">**Released?**</span></span>

- <span data-ttu-id="3fbb7-275">**恶意软件名称**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-275">**Malware Name**</span></span>

- <span data-ttu-id="3fbb7-276">**文档 ID：** 文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="3fbb7-277">**文件大小**：KB (以) 。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="3fbb7-278">**组织** 组织的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="3fbb7-279">**上次修改时间**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-279">**Last modified**</span></span>

- <span data-ttu-id="3fbb7-280">**修改人**：上次修改文件的用户。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="3fbb7-281">**安全哈希算法 256 位 (SHA-256) 值**： 可以使用此哈希值标识其他信誉存储区或环境中其他位置的文件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="3fbb7-282">对已隔离文件执行操作</span><span class="sxs-lookup"><span data-stu-id="3fbb7-282">Take action on quarantined files</span></span>

<span data-ttu-id="3fbb7-283">当你选择列表中的文件时，可以对"详细信息"浮出控件 **窗格中的文件** 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3fbb7-284">**释放文件**： 选择 (默认) 向**Microsoft 取消选择报告文件以进行分析，** 然后单击"发布**文件"。**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="3fbb7-285">**下载文件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-285">**Download file**</span></span>

- <span data-ttu-id="3fbb7-286">**从隔离区中删除文件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="3fbb7-287">如果不释放或删除文件，它们将在默认隔离保留期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="3fbb7-288">对多个隔离文件执行的操作</span><span class="sxs-lookup"><span data-stu-id="3fbb7-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="3fbb7-289">在列表中选择多个隔离的文件后 (最多 100 **) ，"批量** 操作"窗格将出现，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="3fbb7-290">**发布文件**</span><span class="sxs-lookup"><span data-stu-id="3fbb7-290">**Release files**</span></span>

- <span data-ttu-id="3fbb7-291">**删除文件**：在出现 **的警告** 中单击"是"后，文件将立即删除。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="3fbb7-292">使用在组织中拥有全局管理员权限 (或适当的安全& 合规中心角色) 的工作或学校帐户登录并转到 [安全&合规中心](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="3fbb7-293">使用 Exchange Online PowerShell 或独立 EOP PowerShell 查看和管理隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="3fbb7-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="3fbb7-294">您用于查看和管理隔离的邮件和文件的 cmdlet 是：</span><span class="sxs-lookup"><span data-stu-id="3fbb7-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="3fbb7-295">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3fbb7-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="3fbb7-296">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3fbb7-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="3fbb7-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3fbb7-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="3fbb7-298">[Preview-QuarantineMessage：](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)请注意，此 cmdlet 仅适用于邮件，不适用于来自 SharePoint Online、OneDrive for Business 或 Teams 的 ATP 的恶意软件文件。</span><span class="sxs-lookup"><span data-stu-id="3fbb7-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="3fbb7-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3fbb7-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
