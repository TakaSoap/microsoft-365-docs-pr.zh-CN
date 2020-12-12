---
title: 管理员提交
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的提交门户将可疑电子邮件、可疑网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.openlocfilehash: 7327768780e5db16e09e2b709c9c11344573c404
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659821"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="66807-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="66807-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="66807-104">在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="66807-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="66807-105">提交电子邮件时，将获取有关可能允许传入电子邮件进入租户的任何策略的信息，以及检查邮件中任何 URL 和附件的信息。</span><span class="sxs-lookup"><span data-stu-id="66807-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="66807-106">允许邮件的策略包括单个用户的安全发件人列表以及租户级别策略（如 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="66807-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="66807-107">有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="66807-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="66807-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="66807-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="66807-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="66807-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="66807-110">若要直接转到提交 **页面，** 请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="66807-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="66807-111">若要向 Microsoft 提交邮件和文件，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="66807-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="66807-112">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="66807-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="66807-113">**Exchange** [Online 中的组织管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="66807-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="66807-114">请注意，查看自定义邮箱的用户提交需要此角色[](#view-user-submissions-to-the-custom-mailbox)组成员身份，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="66807-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="66807-115">若要详细了解用户如何向 Microsoft 提交邮件和文件，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="66807-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="66807-116">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="66807-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="66807-117">在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="66807-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="66807-118">使用 **显示为** 提交邮件、URL 或附件的新提交飞出，如以下部分所述。</span><span class="sxs-lookup"><span data-stu-id="66807-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="66807-119">向 Microsoft 提交一封有问题的电子邮件</span><span class="sxs-lookup"><span data-stu-id="66807-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="66807-120">在"**对象类型"** 部分，选择"**电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="66807-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="66807-121">在 **"提交格式** "部分中，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="66807-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="66807-122">**网络邮件 ID：** 这是一个 GUID 值，在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 标头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id 标头** 中可用。</span><span class="sxs-lookup"><span data-stu-id="66807-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="66807-123">**文件**：单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="66807-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="66807-124">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="66807-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66807-125">具有 Defender for Office 365 计划 1 或计划 2 的管理员可以提交 30 天的邮件。</span><span class="sxs-lookup"><span data-stu-id="66807-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="66807-126">其他管理员将只能返回 7 天。</span><span class="sxs-lookup"><span data-stu-id="66807-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="66807-127">在 **"收件人"** 部分中，指定要针对这些收件人运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="66807-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="66807-128">策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="66807-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="66807-129">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="66807-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="66807-130">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="66807-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66807-131">**应该已被阻止**：选择 **垃圾邮件**、 **网络钓鱼** 或 **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="66807-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="66807-132">如果你不确定，请使用最佳判断。</span><span class="sxs-lookup"><span data-stu-id="66807-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="66807-133">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="66807-133">When you're finished, click the **Submit** button.</span></span>

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="66807-135">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="66807-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="66807-136">在"**对象类型"** 部分，选择 **URL。**</span><span class="sxs-lookup"><span data-stu-id="66807-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="66807-137">在出现的框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。</span><span class="sxs-lookup"><span data-stu-id="66807-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="66807-138">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="66807-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="66807-139">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="66807-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66807-140">**应该已被阻止：** 选择 **网络钓鱼或\*\*\*\*恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="66807-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="66807-141">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="66807-141">When you're finished, click the **Submit** button.</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="66807-143">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="66807-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="66807-144">在"**对象类型"** 部分，选择"**附件"。**</span><span class="sxs-lookup"><span data-stu-id="66807-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="66807-145">单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="66807-145">Click **Choose File**.</span></span> <span data-ttu-id="66807-146">在打开的对话框中，查找并选择文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="66807-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="66807-147">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="66807-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="66807-148">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="66807-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66807-149">**应该已被阻止**： **恶意软件** 是唯一的选择，并且会自动选中。</span><span class="sxs-lookup"><span data-stu-id="66807-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="66807-150">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="66807-150">When you're finished, click the **Submit** button.</span></span>

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="66807-152">查看管理员提交</span><span class="sxs-lookup"><span data-stu-id="66807-152">View admin submissions</span></span>

<span data-ttu-id="66807-153">在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="66807-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="66807-154">在页面顶部附近，你可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (筛选分配给每个提交) 的 GUID 值 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="66807-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66807-155">Update</span><span class="sxs-lookup"><span data-stu-id="66807-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66807-156">若要更改筛选条件，请单击 **"提交 ID"** 按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="66807-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="66807-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66807-157">**Sender**</span></span>
- <span data-ttu-id="66807-158">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="66807-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="66807-159">**提交者**</span><span class="sxs-lookup"><span data-stu-id="66807-159">**Submitted by**</span></span>
- <span data-ttu-id="66807-160">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-160">**Submission type**</span></span>
- <span data-ttu-id="66807-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="66807-161">**Status**</span></span>

![管理员提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="66807-163">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="66807-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66807-164">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="66807-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="66807-165">在图形下方，有三个选项卡：电子邮件 (默认 **) 、URL** 和 **附件**。</span><span class="sxs-lookup"><span data-stu-id="66807-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="66807-166">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="66807-166">View admin email submissions</span></span>

<span data-ttu-id="66807-167">单击 **"电子邮件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="66807-167">Click the **Email** tab.</span></span>

<span data-ttu-id="66807-168">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="66807-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66807-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="66807-169">**Date**</span></span>
- <span data-ttu-id="66807-170">**提交 ID：** 分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="66807-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="66807-171">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-172">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66807-173">**Sender**</span></span>
- <span data-ttu-id="66807-174">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-175">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-175">**Submission type**</span></span>
- <span data-ttu-id="66807-176">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="66807-176">**Delivery reason**</span></span>
- <span data-ttu-id="66807-177">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66807-178"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="66807-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="66807-179">管理员提交重新扫描详细信息</span><span class="sxs-lookup"><span data-stu-id="66807-179">Admin submission rescan details</span></span>

<span data-ttu-id="66807-180">在管理员提交中提交的邮件将重新扫描，详细信息飞出中显示的结果如下：</span><span class="sxs-lookup"><span data-stu-id="66807-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="66807-181">如果在发送时发件人的电子邮件身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="66807-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="66807-182">有关可能影响或替代邮件裁定的任何策略命中的信息。</span><span class="sxs-lookup"><span data-stu-id="66807-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="66807-183">当前触发结果，以查看邮件中包含的 URL 或文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="66807-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="66807-184">来自成绩人员的反馈。</span><span class="sxs-lookup"><span data-stu-id="66807-184">Feedback from graders.</span></span>

<span data-ttu-id="66807-185">如果发现覆盖，则重新扫描应在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="66807-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="66807-186">如果电子邮件身份验证没有问题，或者传递不受替代影响，则来自成绩人员的反馈可能需要一天的时间。</span><span class="sxs-lookup"><span data-stu-id="66807-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="66807-187">查看管理员 URL 提交</span><span class="sxs-lookup"><span data-stu-id="66807-187">View admin URL submissions</span></span>

<span data-ttu-id="66807-188">单击 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="66807-188">Click the **URL** tab.</span></span>

<span data-ttu-id="66807-189">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="66807-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66807-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="66807-190">**Date**</span></span>
- <span data-ttu-id="66807-191">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="66807-191">**Submission ID**</span></span>
- <span data-ttu-id="66807-192">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-194">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-194">**Submission type**</span></span>
- <span data-ttu-id="66807-195">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66807-196"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="66807-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="66807-197">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="66807-197">View admin attachment submissions</span></span>

<span data-ttu-id="66807-198">单击 **"附件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="66807-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="66807-199">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="66807-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66807-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="66807-200">**Date**</span></span>
- <span data-ttu-id="66807-201">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="66807-201">**Submission ID**</span></span>
- <span data-ttu-id="66807-202">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-203">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-204">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-204">**Submission type**</span></span>
- <span data-ttu-id="66807-205">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66807-206"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="66807-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="66807-207">查看用户向 Microsoft 提交内容</span><span class="sxs-lookup"><span data-stu-id="66807-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="66807-208">如果已部署"报告邮件"[](enable-the-report-message-add-in.md)加载项，或者用户使用[Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)网页中的内置报告，可以在"用户提交"选项卡上查看报告的用户。 </span><span class="sxs-lookup"><span data-stu-id="66807-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="66807-209">在安全&中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="66807-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="66807-210">选择 **"用户提交"** 选项卡，然后单击"**新建提交"。**</span><span class="sxs-lookup"><span data-stu-id="66807-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="66807-211">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="66807-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66807-212">**提交于**</span><span class="sxs-lookup"><span data-stu-id="66807-212">**Submitted on**</span></span>
- <span data-ttu-id="66807-213">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-214">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66807-215">**Sender**</span></span>
- <span data-ttu-id="66807-216">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-217">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-217">**Submission type**</span></span>

<span data-ttu-id="66807-218"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="66807-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="66807-219">在页面顶部附近，可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮按发件人进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="66807-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66807-220">Update</span><span class="sxs-lookup"><span data-stu-id="66807-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66807-221">若要更改筛选条件，请单击 **"发件人"** 按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="66807-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="66807-222">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="66807-222">**Sender domain**</span></span>
- <span data-ttu-id="66807-223">**主题**</span><span class="sxs-lookup"><span data-stu-id="66807-223">**Subject**</span></span>
- <span data-ttu-id="66807-224">**提交者**</span><span class="sxs-lookup"><span data-stu-id="66807-224">**Submitted by**</span></span>
- <span data-ttu-id="66807-225">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-225">**Submission type**</span></span>
- <span data-ttu-id="66807-226">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="66807-226">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="66807-228">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="66807-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66807-229">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="66807-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="66807-230">查看用户提交到自定义邮箱</span><span class="sxs-lookup"><span data-stu-id="66807-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="66807-231">**如果** 已配置自定义 [邮箱](user-submission.md) 以接收用户报告的邮件，则还可以查看并提交已传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="66807-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="66807-232">在安全&中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="66807-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="66807-233">选择 **"自定义邮箱"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="66807-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="66807-234">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="66807-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66807-235">**提交于**</span><span class="sxs-lookup"><span data-stu-id="66807-235">**Submitted on**</span></span>
- <span data-ttu-id="66807-236">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-237">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66807-238">**Sender**</span></span>
- <span data-ttu-id="66807-239">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66807-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66807-240">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="66807-240">**Submission type**</span></span>

<span data-ttu-id="66807-241">在页面顶部附近，可以输入开始日期、结束日期，并且可以通过在框中输入值并单击"刷新"按钮按"提交 ![ "进行筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="66807-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66807-242">Update</span><span class="sxs-lookup"><span data-stu-id="66807-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66807-243">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="66807-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66807-244">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="66807-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="66807-245">撤消用户提交</span><span class="sxs-lookup"><span data-stu-id="66807-245">Undo user submissions</span></span>

<span data-ttu-id="66807-246">用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法选择撤消提交。</span><span class="sxs-lookup"><span data-stu-id="66807-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="66807-247">如果用户希望恢复电子邮件，它将可用于"已删除邮件"或"垃圾邮件"文件夹中的恢复。</span><span class="sxs-lookup"><span data-stu-id="66807-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="66807-248">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="66807-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="66807-249">如果已配置自定义邮箱以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="66807-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="66807-250">这有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="66807-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="66807-251">在 **"自定义邮箱**"选项卡上，在列表中选择一封邮件，单击"操作"按钮，然后进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="66807-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="66807-252">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="66807-252">**Report clean**</span></span>
- <span data-ttu-id="66807-253">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="66807-253">**Report phishing**</span></span>
- <span data-ttu-id="66807-254">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="66807-254">**Report malware**</span></span>
- <span data-ttu-id="66807-255">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="66807-255">**Report spam**</span></span>

!["操作"按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
