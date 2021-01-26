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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的提交门户将可疑电子邮件、可疑网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976599"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="e972c-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e972c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e972c-104">在 Exchange Online 中具有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="e972c-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="e972c-105">当你提交电子邮件时，你将获得：</span><span class="sxs-lookup"><span data-stu-id="e972c-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="e972c-106">**电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e972c-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="e972c-107">**策略命中**：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖我们的服务筛选器裁定。</span><span class="sxs-lookup"><span data-stu-id="e972c-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="e972c-108">**有效负载信誉/触发**：检查邮件中任何 URL 和附件。</span><span class="sxs-lookup"><span data-stu-id="e972c-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="e972c-109">**成绩分析**：由人工评分人员进行审阅，以确认邮件是否是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="e972c-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e972c-110">负载信誉/触发和成绩分析并非在所有租户中完成。</span><span class="sxs-lookup"><span data-stu-id="e972c-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="e972c-111">当数据出于合规性目的不应离开租户边界时，将阻止信息进入组织外部。</span><span class="sxs-lookup"><span data-stu-id="e972c-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="e972c-112">有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="e972c-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e972c-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e972c-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e972c-114">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="e972c-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e972c-115">若要直接转到提交 **页面，** 请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="e972c-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="e972c-116">若要向 Microsoft 提交邮件和文件，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="e972c-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="e972c-117">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="e972c-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="e972c-118">**Exchange** [Online 中的组织管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="e972c-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="e972c-119">请注意，查看自定义邮箱的用户提交需要此角色[](#view-user-submissions-to-the-custom-mailbox)组成员身份，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="e972c-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="e972c-120">若要详细了解用户如何向 Microsoft 提交邮件和文件，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="e972c-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="e972c-121">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="e972c-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="e972c-122">在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="e972c-123">使用 **显示为** 提交邮件、URL 或附件的新提交飞出，如以下部分所述。</span><span class="sxs-lookup"><span data-stu-id="e972c-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e972c-124">向 Microsoft 提交一封有问题的电子邮件</span><span class="sxs-lookup"><span data-stu-id="e972c-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="e972c-125">在"**对象类型"** 部分，选择"**电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="e972c-126">在 **"提交格式** "部分中，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="e972c-127">**网络邮件 ID：** 这是一个 GUID 值，在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 标头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id 标头** 中可用。</span><span class="sxs-lookup"><span data-stu-id="e972c-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="e972c-128">**文件**：单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="e972c-129">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e972c-130">具有 Defender for Office 365 计划 1 或计划 2 的管理员可以提交 30 天的邮件。</span><span class="sxs-lookup"><span data-stu-id="e972c-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="e972c-131">其他管理员将只能返回 7 天。</span><span class="sxs-lookup"><span data-stu-id="e972c-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="e972c-132">在 **"收件人"** 部分中，指定要针对这些收件人运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="e972c-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="e972c-133">策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="e972c-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="e972c-134">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e972c-135">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="e972c-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e972c-136">**应该已被阻止**：选择 **垃圾邮件**、 **网络钓鱼** 或 **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="e972c-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="e972c-137">如果你不确定，请使用最佳判断。</span><span class="sxs-lookup"><span data-stu-id="e972c-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="e972c-138">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e972c-138">When you're finished, click the **Submit** button.</span></span>

   ![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e972c-140">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="e972c-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="e972c-141">在"**对象类型"** 部分，选择 **URL。**</span><span class="sxs-lookup"><span data-stu-id="e972c-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="e972c-142">在出现的框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。</span><span class="sxs-lookup"><span data-stu-id="e972c-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="e972c-143">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e972c-144">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="e972c-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e972c-145">**应该已被阻止：** 选择 **网络钓鱼或\*\*\*\*恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="e972c-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="e972c-146">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e972c-146">When you're finished, click the **Submit** button.</span></span>

   ![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="e972c-148">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e972c-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="e972c-149">在"**对象类型"** 部分，选择"**附件"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="e972c-150">单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-150">Click **Choose File**.</span></span> <span data-ttu-id="e972c-151">在打开的对话框中，查找并选择文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="e972c-152">在 **"提交原因"部分** ，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e972c-153">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="e972c-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e972c-154">**应该已被阻止**： **恶意软件** 是唯一的选择，并且会自动选中。</span><span class="sxs-lookup"><span data-stu-id="e972c-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="e972c-155">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e972c-155">When you're finished, click the **Submit** button.</span></span>

   ![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="e972c-157">查看管理员提交</span><span class="sxs-lookup"><span data-stu-id="e972c-157">View admin submissions</span></span>

<span data-ttu-id="e972c-158">在安全&合规中心，转到"**威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e972c-159">在页面顶部附近，你可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (筛选分配给每个提交) 的 GUID 值 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e972c-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e972c-160">Update</span><span class="sxs-lookup"><span data-stu-id="e972c-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e972c-161">若要更改筛选条件，请单击 **"提交 ID"** 按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="e972c-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e972c-162">**Sender**</span></span>
- <span data-ttu-id="e972c-163">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="e972c-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="e972c-164">**提交者**</span><span class="sxs-lookup"><span data-stu-id="e972c-164">**Submitted by**</span></span>
- <span data-ttu-id="e972c-165">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-165">**Submission type**</span></span>
- <span data-ttu-id="e972c-166">"状态"</span><span class="sxs-lookup"><span data-stu-id="e972c-166">**Status**</span></span>

![管理员提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="e972c-168">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e972c-169">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e972c-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="e972c-170">在图形下方，有三个选项卡：电子邮件 (默认 **) 、URL** 和 **附件**。</span><span class="sxs-lookup"><span data-stu-id="e972c-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="e972c-171">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="e972c-171">View admin email submissions</span></span>

<span data-ttu-id="e972c-172">单击 **"电子邮件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e972c-172">Click the **Email** tab.</span></span>

<span data-ttu-id="e972c-173">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e972c-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e972c-174">"日期"</span><span class="sxs-lookup"><span data-stu-id="e972c-174">**Date**</span></span>
- <span data-ttu-id="e972c-175">**提交 ID：** 分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="e972c-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="e972c-176">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-177">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e972c-178">**Sender**</span></span>
- <span data-ttu-id="e972c-179">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-180">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-180">**Submission type**</span></span>
- <span data-ttu-id="e972c-181">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="e972c-181">**Delivery reason**</span></span>
- <span data-ttu-id="e972c-182">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e972c-183"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="e972c-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="e972c-184">管理员提交重新扫描详细信息</span><span class="sxs-lookup"><span data-stu-id="e972c-184">Admin submission rescan details</span></span>

<span data-ttu-id="e972c-185">在管理员提交中提交的邮件将重新扫描，详细信息飞出中显示的结果如下：</span><span class="sxs-lookup"><span data-stu-id="e972c-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="e972c-186">如果在发送时发件人的电子邮件身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="e972c-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="e972c-187">有关可能影响或替代邮件裁定的任何策略命中的信息。</span><span class="sxs-lookup"><span data-stu-id="e972c-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="e972c-188">当前触发结果，以查看邮件中包含的 URL 或文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="e972c-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="e972c-189">来自成绩人员的反馈。</span><span class="sxs-lookup"><span data-stu-id="e972c-189">Feedback from graders.</span></span>

<span data-ttu-id="e972c-190">如果发现覆盖，则重新扫描应在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="e972c-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="e972c-191">如果电子邮件身份验证没有问题，或者传递不受替代影响，则来自成绩人员的反馈可能需要一天的时间。</span><span class="sxs-lookup"><span data-stu-id="e972c-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="e972c-192">查看管理员 URL 提交</span><span class="sxs-lookup"><span data-stu-id="e972c-192">View admin URL submissions</span></span>

<span data-ttu-id="e972c-193">单击 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e972c-193">Click the **URL** tab.</span></span>

<span data-ttu-id="e972c-194">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e972c-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e972c-195">"日期"</span><span class="sxs-lookup"><span data-stu-id="e972c-195">**Date**</span></span>
- <span data-ttu-id="e972c-196">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="e972c-196">**Submission ID**</span></span>
- <span data-ttu-id="e972c-197">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-199">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-199">**Submission type**</span></span>
- <span data-ttu-id="e972c-200">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e972c-201"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="e972c-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="e972c-202">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="e972c-202">View admin attachment submissions</span></span>

<span data-ttu-id="e972c-203">单击 **"附件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e972c-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="e972c-204">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e972c-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e972c-205">"日期"</span><span class="sxs-lookup"><span data-stu-id="e972c-205">**Date**</span></span>
- <span data-ttu-id="e972c-206">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="e972c-206">**Submission ID**</span></span>
- <span data-ttu-id="e972c-207">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-208">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-209">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-209">**Submission type**</span></span>
- <span data-ttu-id="e972c-210">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e972c-211"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="e972c-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="e972c-212">查看用户向 Microsoft 提交内容</span><span class="sxs-lookup"><span data-stu-id="e972c-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="e972c-213">如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用 Outlook [](enable-the-report-phish-add-in.md)[网页](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中的内置报告，可以在"用户提交"选项卡上查看用户报告的内容。 </span><span class="sxs-lookup"><span data-stu-id="e972c-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="e972c-214">在安全&中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e972c-215">选择 **"用户提交"** 选项卡，然后单击"**新建提交"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e972c-216">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e972c-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e972c-217">**提交于**</span><span class="sxs-lookup"><span data-stu-id="e972c-217">**Submitted on**</span></span>
- <span data-ttu-id="e972c-218">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-219">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e972c-220">**Sender**</span></span>
- <span data-ttu-id="e972c-221">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-222">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-222">**Submission type**</span></span>

<span data-ttu-id="e972c-223"><sup>\*</sup> 如果单击此值，则详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="e972c-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="e972c-224">在页面顶部附近，可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮按发件人进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e972c-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e972c-225">Update</span><span class="sxs-lookup"><span data-stu-id="e972c-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e972c-226">若要更改筛选条件，请单击 **"发件人"** 按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="e972c-227">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="e972c-227">**Sender domain**</span></span>
- <span data-ttu-id="e972c-228">**主题**</span><span class="sxs-lookup"><span data-stu-id="e972c-228">**Subject**</span></span>
- <span data-ttu-id="e972c-229">**提交者**</span><span class="sxs-lookup"><span data-stu-id="e972c-229">**Submitted by**</span></span>
- <span data-ttu-id="e972c-230">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-230">**Submission type**</span></span>
- <span data-ttu-id="e972c-231">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="e972c-231">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="e972c-233">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e972c-234">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e972c-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="e972c-235">查看用户提交到自定义邮箱</span><span class="sxs-lookup"><span data-stu-id="e972c-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="e972c-236">**如果** 已配置自定义 [邮箱](user-submission.md) 以接收用户报告的邮件，则还可以查看并提交已传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="e972c-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="e972c-237">在安全&中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e972c-238">选择 **"自定义邮箱"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e972c-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="e972c-239">可以单击页面 **底部附近的** "列选项"按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e972c-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e972c-240">**提交于**</span><span class="sxs-lookup"><span data-stu-id="e972c-240">**Submitted on**</span></span>
- <span data-ttu-id="e972c-241">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-242">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e972c-243">**Sender**</span></span>
- <span data-ttu-id="e972c-244">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e972c-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e972c-245">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e972c-245">**Submission type**</span></span>

<span data-ttu-id="e972c-246">在页面顶部附近，可以输入开始日期、结束日期，并且可以通过在框中输入值并单击"刷新"按钮按"提交 ![ "进行筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e972c-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e972c-247">Update</span><span class="sxs-lookup"><span data-stu-id="e972c-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e972c-248">若要导出结果，请单击页面顶部附近的"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="e972c-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e972c-249">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e972c-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="e972c-250">撤消用户提交</span><span class="sxs-lookup"><span data-stu-id="e972c-250">Undo user submissions</span></span>

<span data-ttu-id="e972c-251">用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法选择撤消提交。</span><span class="sxs-lookup"><span data-stu-id="e972c-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="e972c-252">如果用户希望恢复电子邮件，它将可用于"已删除邮件"或"垃圾邮件"文件夹中的恢复。</span><span class="sxs-lookup"><span data-stu-id="e972c-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="e972c-253">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="e972c-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="e972c-254">如果已配置自定义邮箱以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e972c-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="e972c-255">这有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="e972c-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="e972c-256">在 **"自定义邮箱**"选项卡上，在列表中选择一封邮件，单击"操作"按钮，然后进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="e972c-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="e972c-257">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="e972c-257">**Report clean**</span></span>
- <span data-ttu-id="e972c-258">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="e972c-258">**Report phishing**</span></span>
- <span data-ttu-id="e972c-259">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e972c-259">**Report malware**</span></span>
- <span data-ttu-id="e972c-260">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="e972c-260">**Report spam**</span></span>

!["操作"按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
