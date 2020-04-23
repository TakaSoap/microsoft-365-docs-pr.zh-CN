---
title: 以用户身份查找并释放隔离的邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 作为 Microsoft 365 用户，你可以查看、释放和删除隔离的邮件，即你是收件人、但被垃圾邮件筛选功能隔离为垃圾邮件或群发电子邮件的邮件。 在安全与合规中心内，查看和管理已隔离邮件。
ms.openlocfilehash: 215cbc23aca3b7d10eca8c53d816892d0ca042cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638102"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="856f1-104">以用户身份查找并释放隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="856f1-104">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="856f1-105">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="856f1-106">有关详细信息，请参阅 [Office 365 中的隔离功能](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="856f1-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="856f1-107">作为用户，你可以查看、释放和删除已隔离邮件，即你是收件人但被隔离为垃圾邮件、大量电子邮件或（自 2020 年 4 月起）钓鱼电子邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="856f1-108">你可以在“安全与合规中心”或[最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)（如果管理员已对此进行了设置）中查看和管理隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="856f1-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="856f1-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="856f1-110">若要打开安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="856f1-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="856f1-111">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="856f1-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="856f1-112">管理员可以配置邮件在永久删除前的隔离期限（反垃圾邮件策略）。</span><span class="sxs-lookup"><span data-stu-id="856f1-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="856f1-113">隔离到期的邮件不可恢复。</span><span class="sxs-lookup"><span data-stu-id="856f1-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="856f1-114">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="856f1-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="856f1-115">此外，管理员还可以在反垃圾邮件策略中[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。</span><span class="sxs-lookup"><span data-stu-id="856f1-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="856f1-116">用户可以直接从这些通知中释放垃圾邮件隔离邮件，但不能释放隔离的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="856f1-117">有关详细信息，请参阅 [Office 365 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="856f1-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="856f1-118">只有管理员才能访问因为是高可信度钓鱼电子邮件、恶意软件或根据邮件流规则（亦称为“传输规则”）被隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="856f1-119">有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="856f1-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="856f1-120">可以释放邮件，并将它报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="856f1-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="856f1-121">查看已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="856f1-121">View your quarantined messages</span></span>

1. <span data-ttu-id="856f1-122">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“隔离”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="856f1-123">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="856f1-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="856f1-124">单击“修改列”\*\*\*\* 最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="856f1-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="856f1-125">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="856f1-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="856f1-126">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-127">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-128">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-129">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-130">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-131">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-132">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="856f1-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="856f1-133">**收件人**</span><span class="sxs-lookup"><span data-stu-id="856f1-133">**Recipient**</span></span>

   - <span data-ttu-id="856f1-134">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="856f1-134">**Message ID**</span></span>

   - <span data-ttu-id="856f1-135">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="856f1-135">**Policy name**</span></span>

   - <span data-ttu-id="856f1-136">**大小**</span><span class="sxs-lookup"><span data-stu-id="856f1-136">**Size**</span></span>

   - <span data-ttu-id="856f1-137">**方向**</span><span class="sxs-lookup"><span data-stu-id="856f1-137">**Direction**</span></span>

   <span data-ttu-id="856f1-138">完成后，单击“保存”\*\*\*\* 单击“设置为默认设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="856f1-139">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="856f1-140">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="856f1-140">The available filters are:</span></span>

   - <span data-ttu-id="856f1-141">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="856f1-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="856f1-142">**今天**</span><span class="sxs-lookup"><span data-stu-id="856f1-142">**Today**</span></span>

     - <span data-ttu-id="856f1-143">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="856f1-143">**Next 2 days**</span></span>

     - <span data-ttu-id="856f1-144">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="856f1-144">**Next 7 days**</span></span>

     - <span data-ttu-id="856f1-145">**自定义**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="856f1-146">**接收时间**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="856f1-147">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="856f1-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="856f1-148">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="856f1-148">**Bulk**</span></span>

     - <span data-ttu-id="856f1-149">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="856f1-149">**Spam**</span></span>

     - <span data-ttu-id="856f1-150">**钓鱼邮件**（自 2020 年 4 月起）</span><span class="sxs-lookup"><span data-stu-id="856f1-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="856f1-151">若要清除筛选器，请单击“清除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="856f1-152">若要隐藏筛选器浮出控件，请再次单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="856f1-153">使用“结果排序依据”\*\*\*\*（默认为“邮件 ID”\*\*\*\* 按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="856f1-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="856f1-154">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="856f1-154">Wildcards aren't supported.</span></span> <span data-ttu-id="856f1-155">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="856f1-155">You can search by the following values:</span></span>

   - <span data-ttu-id="856f1-156">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="856f1-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="856f1-157">在你选择列表中的邮件后，“详细信息”\*\*\*\* 浮出控件窗格随即显示，其中包含“邮件 ID”\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="856f1-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="856f1-158">管理员可以使用[邮件跟踪](message-trace-scc.md)来查找邮件及其相应“邮件 ID”值。</span><span class="sxs-lookup"><span data-stu-id="856f1-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="856f1-159">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="856f1-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="856f1-160">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="856f1-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="856f1-161">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="856f1-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="856f1-162">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="856f1-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="856f1-163">输入搜索条件后，单击“刷新”\*\*\*\* ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="856f1-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="856f1-164">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="856f1-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="856f1-165">导出邮件结果</span><span class="sxs-lookup"><span data-stu-id="856f1-165">Export message results</span></span>

1. <span data-ttu-id="856f1-166">选择你有意访问的邮件，然后单击“导出结果”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="856f1-167">在警告你不要关闭浏览器窗口的确认消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="856f1-168">在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。</span><span class="sxs-lookup"><span data-stu-id="856f1-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="856f1-169">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="856f1-169">View quarantined message details</span></span>

<span data-ttu-id="856f1-170">选择列表中的电子邮件后，可以在“详细信息”\*\*\*\* 浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="856f1-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="856f1-171">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="856f1-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="856f1-172">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="856f1-172">**Sender address**</span></span>

- <span data-ttu-id="856f1-173">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="856f1-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="856f1-174">**主题**</span><span class="sxs-lookup"><span data-stu-id="856f1-174">**Subject**</span></span>

- <span data-ttu-id="856f1-175">**隔离原因**：显示邮件是被标识为“垃圾邮件”\*\*\*\*、“大量邮件”\*\*\*\* 还是（自 2020 年 4 月起）“钓鱼邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="856f1-176">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”\*\*\*\* 或“查看邮件头”\*\*\*\*，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="856f1-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="856f1-177">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="856f1-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="856f1-178">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="856f1-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="856f1-179">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="856f1-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="856f1-180">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="856f1-180">Take action on quarantined email</span></span>

<span data-ttu-id="856f1-181">选择电子邮件后，可以在“详细信息”\*\*\*\* 浮出控件窗格中选择要对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="856f1-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="856f1-182">**释放邮件**：在显示的浮出控件窗格中，选择是否选中“将邮件报告给 Microsoft 进行分析”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="856f1-183">此选项默认处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="856f1-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="856f1-184">完成后，单击“释放邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="856f1-185">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="856f1-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="856f1-186">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”\*\*\*\*，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="856f1-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="856f1-187">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="856f1-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="856f1-188">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="856f1-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="856f1-189">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="856f1-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="856f1-190">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="856f1-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="856f1-191">**下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”\*\*\*\*，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="856f1-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="856f1-192">**从隔离中删除**：当你在显示的警告中单击“是”\*\*\*\* 后，邮件会立即删除。</span><span class="sxs-lookup"><span data-stu-id="856f1-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="856f1-193">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="856f1-194">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="856f1-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="856f1-195">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="856f1-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="856f1-196">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”\*\*\*\* 浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="856f1-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="856f1-197">**释放邮件**：除了无法选择“将邮件释放给特定收件人”\*\*\*\* 之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”\*\*\*\* 或“将邮件释放给其他用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="856f1-198">**删除邮件**：当你在显示的警告中单击“是”\*\*\*\* 后，邮件会立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="856f1-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="856f1-199">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="856f1-199">When you're finished, click **Close**.</span></span>
