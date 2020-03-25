---
title: 在 Office 365 中以用户的身份查找并释放隔离的邮件。
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
description: 作为 Office 365 用户，你可以查看、释放和删除已隔离邮件，即你是收件人但被垃圾邮件筛选功能隔离为垃圾邮件或大量电子邮件的邮件。 在安全与合规中心内，查看和管理已隔离邮件。
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893666"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="54dd6-104">在 Office 365 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="54dd6-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="54dd6-105">无论是在有 Exchange Online 邮箱的 Office 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="54dd6-106">有关详细信息，请参阅 [Office 365 中的隔离功能](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="54dd6-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="54dd6-107">作为用户，你可以查看、释放和删除已隔离邮件，即你是收件人但被隔离为垃圾邮件、大量电子邮件或（自 2020 年 4 月起）钓鱼电子邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="54dd6-108">用户还可以向 Microsoft 报告误报。</span><span class="sxs-lookup"><span data-stu-id="54dd6-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="54dd6-109">在安全与合规中心内，查看和管理已隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54dd6-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="54dd6-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54dd6-111">若要打开 Office 365 安全与合规中心，请转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="54dd6-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="54dd6-112">若要直接打开“隔离”页，请转到 <https://protection.office.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="54dd6-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="54dd6-113">管理员可以配置邮件在永久删除前的隔离期限（反垃圾邮件策略）。</span><span class="sxs-lookup"><span data-stu-id="54dd6-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="54dd6-114">隔离到期的邮件不可恢复。</span><span class="sxs-lookup"><span data-stu-id="54dd6-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="54dd6-115">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="54dd6-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="54dd6-116">此外，管理员还可以在反垃圾邮件策略中[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。</span><span class="sxs-lookup"><span data-stu-id="54dd6-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="54dd6-117">自 2019 年 10 月起，你无法再直接通过这些通知来释放已隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="54dd6-118">可以单击通知中的“审阅”\*\*\*\*，这会定向到安全与合规中心内的“隔离”。</span><span class="sxs-lookup"><span data-stu-id="54dd6-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="54dd6-119">若要详细了解这些通知，请参阅 [Office 365 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="54dd6-119">For more information about the notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="54dd6-120">只有管理员才能访问因为是高可信度钓鱼电子邮件、恶意软件或根据邮件流规则（亦称为“传输规则”）被隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="54dd6-121">有关详细信息，请参阅[在 Office 365 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="54dd6-121">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="54dd6-122">可以释放邮件，并将它报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="54dd6-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="54dd6-123">查看已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="54dd6-123">View your quarantined messages</span></span>

1. <span data-ttu-id="54dd6-124">在安全与合规中心内，依次转到“威胁管理”\*\*\*\*\>“审阅”\*\*\*\*\>“隔离”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="54dd6-125">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="54dd6-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="54dd6-126">单击“修改列”\*\*\*\* 最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="54dd6-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="54dd6-127">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="54dd6-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="54dd6-128">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-129">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-130">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-131">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-132">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-133">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-134">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="54dd6-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="54dd6-135">**收件人**</span><span class="sxs-lookup"><span data-stu-id="54dd6-135">**Recipient**</span></span>

   - <span data-ttu-id="54dd6-136">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="54dd6-136">**Message ID**</span></span>

   - <span data-ttu-id="54dd6-137">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="54dd6-137">**Policy name**</span></span>

   - <span data-ttu-id="54dd6-138">**大小**</span><span class="sxs-lookup"><span data-stu-id="54dd6-138">**Size**</span></span>

   - <span data-ttu-id="54dd6-139">**方向**</span><span class="sxs-lookup"><span data-stu-id="54dd6-139">**Direction**</span></span>

   <span data-ttu-id="54dd6-140">完成后，单击“保存”\*\*\*\* 单击“设置为默认设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="54dd6-141">若要筛选结果，请单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="54dd6-142">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="54dd6-142">The available filters are:</span></span>

   - <span data-ttu-id="54dd6-143">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="54dd6-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="54dd6-144">**今天**</span><span class="sxs-lookup"><span data-stu-id="54dd6-144">**Today**</span></span>

     - <span data-ttu-id="54dd6-145">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="54dd6-145">**Next 2 days**</span></span>

     - <span data-ttu-id="54dd6-146">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="54dd6-146">**Next 7 days**</span></span>

     - <span data-ttu-id="54dd6-147">**自定义**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="54dd6-148">**接收时间**：输入“开始日期”\*\*\*\* 和“结束日期”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="54dd6-149">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="54dd6-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="54dd6-150">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="54dd6-150">**Bulk**</span></span>

     - <span data-ttu-id="54dd6-151">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="54dd6-151">**Spam**</span></span>

     - <span data-ttu-id="54dd6-152">**钓鱼邮件**（自 2020 年 4 月起）</span><span class="sxs-lookup"><span data-stu-id="54dd6-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="54dd6-153">若要清除筛选器，请单击“清除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="54dd6-154">若要隐藏筛选器浮出控件，请再次单击“筛选器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="54dd6-155">使用“结果排序依据”\*\*\*\*（默认为“邮件 ID”\*\*\*\* 按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="54dd6-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="54dd6-156">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="54dd6-156">Wildcards aren't supported.</span></span> <span data-ttu-id="54dd6-157">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="54dd6-157">You can search by the following values:</span></span>

   - <span data-ttu-id="54dd6-158">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="54dd6-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="54dd6-159">在你选择列表中的邮件后，“详细信息”\*\*\*\* 浮出控件窗格随即显示，其中包含“邮件 ID”\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="54dd6-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="54dd6-160">管理员可以使用[邮件跟踪](message-trace-scc.md)来查找邮件及其相应“邮件 ID”值。</span><span class="sxs-lookup"><span data-stu-id="54dd6-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="54dd6-161">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="54dd6-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="54dd6-162">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="54dd6-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="54dd6-163">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="54dd6-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="54dd6-164">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="54dd6-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="54dd6-165">输入搜索条件后，单击“刷新”\*\*\*\* ![“刷新”按钮](../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="54dd6-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="54dd6-166">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="54dd6-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="54dd6-167">导出邮件结果</span><span class="sxs-lookup"><span data-stu-id="54dd6-167">Export message results</span></span>

1. <span data-ttu-id="54dd6-168">选择你有意访问的邮件，然后单击“导出结果”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="54dd6-169">在警告你不要关闭浏览器窗口的确认消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="54dd6-170">在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。</span><span class="sxs-lookup"><span data-stu-id="54dd6-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="54dd6-171">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="54dd6-171">View quarantined message details</span></span>

<span data-ttu-id="54dd6-172">选择列表中的电子邮件后，可以在“详细信息”\*\*\*\* 浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="54dd6-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="54dd6-173">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="54dd6-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="54dd6-174">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="54dd6-174">**Sender address**</span></span>

- <span data-ttu-id="54dd6-175">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="54dd6-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="54dd6-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="54dd6-176">**Subject**</span></span>

- <span data-ttu-id="54dd6-177">**隔离原因**：显示邮件是被标识为“垃圾邮件”\*\*\*\*、“大量邮件”\*\*\*\* 还是（自 2020 年 4 月起）“钓鱼邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="54dd6-178">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”\*\*\*\* 或“查看邮件头”\*\*\*\*，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="54dd6-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="54dd6-179">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="54dd6-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="54dd6-180">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="54dd6-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="54dd6-181">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="54dd6-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="54dd6-182">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="54dd6-182">Take action on quarantined email</span></span>

<span data-ttu-id="54dd6-183">选择电子邮件后，可以在“详细信息”\*\*\*\* 浮出控件窗格中选择要对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="54dd6-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="54dd6-184">**释放邮件**：在显示的浮出控件窗格中，选择是否选中“将邮件报告给 Microsoft 进行分析”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="54dd6-185">此选项默认处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="54dd6-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="54dd6-186">完成后，单击“释放邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="54dd6-187">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="54dd6-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="54dd6-188">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器\*\*\*\*”，即可转到远程连接分析器（如果希望在不离开 Office 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="54dd6-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="54dd6-189">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="54dd6-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="54dd6-190">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="54dd6-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="54dd6-191">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="54dd6-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="54dd6-192">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="54dd6-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="54dd6-193">**下载邮件**：在显示的浮出控件窗格中，选择“我了解下载此邮件所面临的风险”\*\*\*\*，以使用 .eml 格式保存邮件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="54dd6-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="54dd6-194">**从隔离中删除**：当你在显示的警告中单击“是”\*\*\*\* 后，邮件会立即删除。</span><span class="sxs-lookup"><span data-stu-id="54dd6-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="54dd6-195">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="54dd6-196">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="54dd6-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="54dd6-197">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="54dd6-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="54dd6-198">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”\*\*\*\* 浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54dd6-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="54dd6-199">**释放邮件**：除了无法选择“将邮件释放给特定收件人”\*\*\*\* 之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”\*\*\*\* 或“将邮件释放给其他用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="54dd6-200">**删除邮件**：当你在显示的警告中单击“是”\*\*\*\* 后，邮件会立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="54dd6-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="54dd6-201">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54dd6-201">When you're finished, click **Close**.</span></span>
