---
title: 以用户身份查找并释放隔离的邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 用户可在 Exchange Online Protection （EOP）中了解如何查看和管理应该已提供给他们的隔离邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0f95561977c453d7040d84ba0c779c3d33e07f0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029821"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="8e734-103">在 EOP 中以用户身份查找和释放已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="8e734-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8e734-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="8e734-104">**Applies to**</span></span>
- [<span data-ttu-id="8e734-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e734-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8e734-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="8e734-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8e734-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e734-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8e734-108">无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="8e734-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="8e734-109">有关详细信息，请参阅 [EOP 的隔离功能](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8e734-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8e734-110">作为隔离邮件的收件人，常规用户可以对消息执行的操作如下表所述：</span><span class="sxs-lookup"><span data-stu-id="8e734-110">As a recipient of a quarantined message, what you can do to the message as a non-admin user is described in the following table:</span></span>

<br>

****

|<span data-ttu-id="8e734-111">隔离原因：</span><span class="sxs-lookup"><span data-stu-id="8e734-111">Quarantine reason</span></span>|<span data-ttu-id="8e734-112">查看</span><span class="sxs-lookup"><span data-stu-id="8e734-112">View</span></span>|<span data-ttu-id="8e734-113">发布</span><span class="sxs-lookup"><span data-stu-id="8e734-113">Release</span></span>|<span data-ttu-id="8e734-114">删除</span><span class="sxs-lookup"><span data-stu-id="8e734-114">Delete</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="8e734-115">批量邮件</span><span class="sxs-lookup"><span data-stu-id="8e734-115">Bulk</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e734-119">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8e734-119">Spam</span></span>|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|<span data-ttu-id="8e734-123">钓鱼(非高可信度钓鱼)</span><span class="sxs-lookup"><span data-stu-id="8e734-123">Phishing (not high confidence phishing)</span></span>|![复选标记](../../media/checkmark.png)||![复选标记](../../media/checkmark.png)|
|

<span data-ttu-id="8e734-126">你可以在“Microsoft 365 Defender 门户”或[最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)（如果管理员已对此进行了设置）中查看和管理隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="8e734-126">You view and manage your quarantined messages in the Microsoft 365 Defender portal or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8e734-127">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8e734-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8e734-128">若要打开 Microsoft 365 Defender 门户，请转到 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="8e734-128">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="8e734-129">若要直接打开“隔离”页，请转到 <https://security.microsoft.com/quarantine>。</span><span class="sxs-lookup"><span data-stu-id="8e734-129">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="8e734-130">管理员可以配置邮件在永久删除前的隔离期限（反垃圾邮件策略）。</span><span class="sxs-lookup"><span data-stu-id="8e734-130">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="8e734-131">隔离到期的邮件不可恢复。</span><span class="sxs-lookup"><span data-stu-id="8e734-131">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="8e734-132">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8e734-132">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="8e734-133">此外，管理员还可以在反垃圾邮件策略中[启用最终用户垃圾邮件通知](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)。</span><span class="sxs-lookup"><span data-stu-id="8e734-133">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="8e734-134">用户可以直接从这些通知释放隔离的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="8e734-134">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="8e734-135">用户可以直接从这些通知查看隔离的网络仿冒邮件（不是高可信度网络仿冒邮件）。</span><span class="sxs-lookup"><span data-stu-id="8e734-135">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="8e734-136">有关详细信息，请参阅 [EOP 中的最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8e734-136">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="8e734-137">只有管理员才能访问因为是高可信度网络仿冒邮件、恶意软件或根据邮件流规则（亦称为“传输规则”）被隔离的邮件，用户看不到这些内容。</span><span class="sxs-lookup"><span data-stu-id="8e734-137">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="8e734-138">有关详细信息，请参阅[在 EOP 中以管理员身份管理已隔离邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="8e734-138">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="8e734-139">可以释放邮件，并将它报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="8e734-139">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="8e734-140">查看已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="8e734-140">View your quarantined messages</span></span>

1. <span data-ttu-id="8e734-141">在 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**检查**”\>“**隔离**”。</span><span class="sxs-lookup"><span data-stu-id="8e734-141">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="8e734-142">若要对结果进行排序，可以单击可用列标题。</span><span class="sxs-lookup"><span data-stu-id="8e734-142">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="8e734-143">单击“修改列”最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="8e734-143">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="8e734-144">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="8e734-144">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="8e734-145">**接收时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-145">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-146">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-146">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-147">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-147">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-148">**隔离原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-148">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-149">**释放?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-149">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-150">**策略类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-150">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-151">**到期时间**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e734-151">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="8e734-152">**收件人**</span><span class="sxs-lookup"><span data-stu-id="8e734-152">**Recipient**</span></span>
   - <span data-ttu-id="8e734-153">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="8e734-153">**Message ID**</span></span>
   - <span data-ttu-id="8e734-154">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="8e734-154">**Policy name**</span></span>
   - <span data-ttu-id="8e734-155">**大小**</span><span class="sxs-lookup"><span data-stu-id="8e734-155">**Size**</span></span>
   - <span data-ttu-id="8e734-156">**方向**</span><span class="sxs-lookup"><span data-stu-id="8e734-156">**Direction**</span></span>

   <span data-ttu-id="8e734-157">完成后，单击“保存”单击“设置为默认设置”。</span><span class="sxs-lookup"><span data-stu-id="8e734-157">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="8e734-158">若要筛选结果，请单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="8e734-158">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8e734-159">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="8e734-159">The available filters are:</span></span>

   - <span data-ttu-id="8e734-160">**到期时间**：按邮件的隔离到期时间筛选：</span><span class="sxs-lookup"><span data-stu-id="8e734-160">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="8e734-161">**今天**</span><span class="sxs-lookup"><span data-stu-id="8e734-161">**Today**</span></span>
     - <span data-ttu-id="8e734-162">**未来 2 天**</span><span class="sxs-lookup"><span data-stu-id="8e734-162">**Next 2 days**</span></span>
     - <span data-ttu-id="8e734-163">**未来 7 天**</span><span class="sxs-lookup"><span data-stu-id="8e734-163">**Next 7 days**</span></span>
     - <span data-ttu-id="8e734-164">**自定义**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="8e734-164">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8e734-165">**接收时间**：输入“开始日期”和“结束日期”。</span><span class="sxs-lookup"><span data-stu-id="8e734-165">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8e734-166">**隔离原因**：</span><span class="sxs-lookup"><span data-stu-id="8e734-166">**Quarantine reason**:</span></span>
     - <span data-ttu-id="8e734-167">**大量邮件**</span><span class="sxs-lookup"><span data-stu-id="8e734-167">**Bulk**</span></span>
     - <span data-ttu-id="8e734-168">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="8e734-168">**Spam**</span></span>
     - <span data-ttu-id="8e734-169">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="8e734-169">**Phish**</span></span>

   - <span data-ttu-id="8e734-170">**策略类型**：按策略类型筛选邮件：</span><span class="sxs-lookup"><span data-stu-id="8e734-170">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="8e734-171">**反恶意软件策略**</span><span class="sxs-lookup"><span data-stu-id="8e734-171">**Anti-malware policy**</span></span>
     - <span data-ttu-id="8e734-172">**安全附加策略**(Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="8e734-172">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="8e734-173">**反网络钓鱼策略**</span><span class="sxs-lookup"><span data-stu-id="8e734-173">**Anti-phish policy**</span></span>
     - <span data-ttu-id="8e734-174">**托管内容筛选器策略**（反垃圾邮件策略）</span><span class="sxs-lookup"><span data-stu-id="8e734-174">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="8e734-175">**传输规则**</span><span class="sxs-lookup"><span data-stu-id="8e734-175">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="8e734-176">若要清除筛选器，请单击“清除”。</span><span class="sxs-lookup"><span data-stu-id="8e734-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="8e734-177">若要隐藏筛选器浮出控件，请再次单击“筛选器”。</span><span class="sxs-lookup"><span data-stu-id="8e734-177">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="8e734-178">使用“结果排序依据”（默认为“邮件 ID”按钮）和相应值查找特定邮件。</span><span class="sxs-lookup"><span data-stu-id="8e734-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="8e734-179">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="8e734-179">Wildcards aren't supported.</span></span> <span data-ttu-id="8e734-180">可以按下面的值搜索：</span><span class="sxs-lookup"><span data-stu-id="8e734-180">You can search by the following values:</span></span>

   - <span data-ttu-id="8e734-181">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8e734-181">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="8e734-182">在你选择列表中的邮件后，“详细信息”浮出控件窗格随即显示，其中包含“邮件 ID”值。</span><span class="sxs-lookup"><span data-stu-id="8e734-182">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="8e734-183">管理员可以使用[邮件跟踪](message-trace-scc.md)来查找邮件及其相应“邮件 ID”值。</span><span class="sxs-lookup"><span data-stu-id="8e734-183">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="8e734-184">**发件人电子邮件地址**：单个发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8e734-184">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="8e734-185">**策略名称**：使用邮件的完整策略名称。</span><span class="sxs-lookup"><span data-stu-id="8e734-185">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="8e734-186">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8e734-186">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="8e734-187">**收件人电子邮件地址**：单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8e734-187">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="8e734-188">**主题**：使用邮件的整个主题。</span><span class="sxs-lookup"><span data-stu-id="8e734-188">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="8e734-189">搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="8e734-189">The search is not case-sensitive.</span></span>

   <span data-ttu-id="8e734-190">输入搜索条件后，单击“刷新” ![“刷新”按钮](../../media/scc-quarantine-refresh.png) 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="8e734-190">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="8e734-191">找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。</span><span class="sxs-lookup"><span data-stu-id="8e734-191">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="8e734-192">导出邮件结果</span><span class="sxs-lookup"><span data-stu-id="8e734-192">Export message results</span></span>

1. <span data-ttu-id="8e734-193">选择你有意访问的邮件，然后单击“导出结果”。</span><span class="sxs-lookup"><span data-stu-id="8e734-193">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="8e734-194">在警告你不要关闭浏览器窗口的确认消息中，单击“是”。</span><span class="sxs-lookup"><span data-stu-id="8e734-194">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="8e734-195">在导出结果准备就绪后，可以为 .csv 文件命令并选择下载位置。</span><span class="sxs-lookup"><span data-stu-id="8e734-195">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="8e734-196">查看已隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="8e734-196">View quarantined message details</span></span>

<span data-ttu-id="8e734-197">选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：</span><span class="sxs-lookup"><span data-stu-id="8e734-197">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8e734-198">**邮件 ID**：邮件的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8e734-198">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="8e734-199">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="8e734-199">**Sender address**</span></span>
- <span data-ttu-id="8e734-200">**接收时间**：收到邮件的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="8e734-200">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="8e734-201">**主题**</span><span class="sxs-lookup"><span data-stu-id="8e734-201">**Subject**</span></span>
- <span data-ttu-id="8e734-202">**隔离原因**：显示邮件是否被标识为“**垃圾邮件**”，“**批量邮件**”或“**钓鱼邮件**”。</span><span class="sxs-lookup"><span data-stu-id="8e734-202">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="8e734-203">**收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="8e734-203">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="8e734-204">**到期时间**：邮件自动从隔离中永久删除的日期/时间。</span><span class="sxs-lookup"><span data-stu-id="8e734-204">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="8e734-205">**已释放到的位置**：邮件已释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="8e734-205">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="8e734-206">**尚未释放到的位置**：邮件尚未释放到的所有电子邮件地址（若有）。</span><span class="sxs-lookup"><span data-stu-id="8e734-206">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="8e734-207">对已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="8e734-207">Take action on quarantined email</span></span>

<span data-ttu-id="8e734-208">选择电子邮件后，可以在“详细信息”浮出控件窗格中选择要对邮件执行的操作：</span><span class="sxs-lookup"><span data-stu-id="8e734-208">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8e734-209">**释放邮件**：在显示的浮出控件窗格中，选择是否选中“将邮件报告给 Microsoft 进行分析”。</span><span class="sxs-lookup"><span data-stu-id="8e734-209">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="8e734-210">此选项默认处于选中状态，并将已错误隔离的邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8e734-210">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="8e734-211">完成后，单击“释放邮件”。</span><span class="sxs-lookup"><span data-stu-id="8e734-211">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="8e734-212">**查看邮件头**：选择此链接可查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="8e734-212">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="8e734-213">若要深入分析邮件头字段和值，请将邮件头文本复制到剪贴板，然后选择“Microsoft 邮件头分析器”，即可转到远程连接分析器（如果希望在不离开 Microsoft 365 的情况下完成这项任务，请右键单击并选择“在新标签页中打开”）。</span><span class="sxs-lookup"><span data-stu-id="8e734-213">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="8e734-214">将邮件头粘贴到页面上的“邮件头分析器”部分中，然后选择“分析邮件头”：</span><span class="sxs-lookup"><span data-stu-id="8e734-214">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="8e734-215">**预览邮件**：在显示的浮出控件窗格中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="8e734-215">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="8e734-216">**源视图**：显示禁用所有链接的 HTML 版邮件正文。</span><span class="sxs-lookup"><span data-stu-id="8e734-216">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="8e734-217">**文本视图**：以纯文本格式显示邮件正文。</span><span class="sxs-lookup"><span data-stu-id="8e734-217">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="8e734-218">**从隔离中删除**：当你在显示的警告中单击“是”后，邮件会立即删除。</span><span class="sxs-lookup"><span data-stu-id="8e734-218">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="8e734-219">**阻止发件人**：将发件人添加到邮箱上的"阻止发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="8e734-219">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="8e734-220">有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="8e734-220">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="8e734-221">将发件人添加到邮箱上的"阻止发件人"列表中。</span><span class="sxs-lookup"><span data-stu-id="8e734-221">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="8e734-222">有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。</span><span class="sxs-lookup"><span data-stu-id="8e734-222">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="8e734-223">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="8e734-223">When you're finished, click **Close**.</span></span>

<span data-ttu-id="8e734-224">如果你没有释放或删除邮件，它会在默认隔离保持期到期后删除。</span><span class="sxs-lookup"><span data-stu-id="8e734-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="8e734-225">对多封已隔离电子邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="8e734-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="8e734-226">在你选择列表中的多封已隔离邮件（最多 100 封）后，“批量操作”浮出控件窗格随即显示，你可以在其中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e734-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="8e734-227">**释放邮件**：除了无法选择“将邮件释放给特定收件人”之外，可以选择的选项与释放一封邮件时相同，即只能选择“将邮件释放给所有收件人”或“将邮件释放给其他用户”。</span><span class="sxs-lookup"><span data-stu-id="8e734-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="8e734-228">**删除邮件**：当你在显示的警告中单击“是”后，邮件会立即删除，而不会发送给原始收件人。</span><span class="sxs-lookup"><span data-stu-id="8e734-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="8e734-229">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="8e734-229">When you're finished, click **Close**.</span></span>
