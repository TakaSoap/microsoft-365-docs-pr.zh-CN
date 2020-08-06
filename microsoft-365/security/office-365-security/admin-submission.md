---
title: 管理员提交
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规性中心中的提交门户将可疑的电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件提交到 Microsoft 进行扫描。
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577866"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="665f1-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="665f1-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="665f1-104">在 Exchange Online 中有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="665f1-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="665f1-105">当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。</span><span class="sxs-lookup"><span data-stu-id="665f1-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="665f1-106">可能允许邮件的策略包括单个用户的安全发件人列表以及租户级别策略（如 Exchange 邮件流规则） (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="665f1-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="665f1-107">有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="665f1-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="665f1-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="665f1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="665f1-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="665f1-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="665f1-110">若要直接转到**提交**页面，请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="665f1-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="665f1-111">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="665f1-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="665f1-112">若要向 Microsoft 提交邮件和文件，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="665f1-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="665f1-113">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="665f1-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="665f1-114">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="665f1-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="665f1-115">若要对提交门户进行只读访问，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="665f1-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="665f1-116">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="665f1-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="665f1-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="665f1-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="665f1-118">有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="665f1-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="665f1-119">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="665f1-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="665f1-120">在安全 & 合规性中心中，转到 "**威胁管理**" \> **查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="665f1-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="665f1-121">在显示的 "**提交**" 页面上，单击 "**新建提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="665f1-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="665f1-122">使用在提交邮件、URL 或附件时出现的**新提交**浮出控件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="665f1-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="665f1-123">将可疑电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="665f1-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="665f1-124">在 "**对象类型**" 部分，选择 "**电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="665f1-125">在 "**提交格式**" 部分，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="665f1-126">**网络邮件 ID**：这是邮件中**X--组织网络-邮件 ID**标头中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="665f1-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="665f1-127">**文件**：单击 "**选择文件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="665f1-128">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="665f1-129">在 "**收件人**" 部分，指定要对其运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="665f1-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="665f1-130">策略检查将确定电子邮件是否因用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="665f1-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="665f1-131">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="665f1-132">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="665f1-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="665f1-133">**应已阻止**：选择 "**垃圾邮件**"、"**网络钓鱼**" 或 "**恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="665f1-134">如果你不确定，请使用你的最佳判断力。</span><span class="sxs-lookup"><span data-stu-id="665f1-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="665f1-135">如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="665f1-136">如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="665f1-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="665f1-137">您将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="665f1-138">这包括策略检查结果和重新扫描判定结果。</span><span class="sxs-lookup"><span data-stu-id="665f1-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="665f1-139">注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="665f1-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="665f1-140">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="665f1-140">When you're finished, click the **Submit** button.</span></span>

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="665f1-142">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="665f1-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="665f1-143">在 "**对象类型**" 部分，选择 " **URL**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="665f1-144">在出现的框中，输入完整的 URL (例如， <https://www.fabrikam.com/marketing.html>) 。</span><span class="sxs-lookup"><span data-stu-id="665f1-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="665f1-145">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="665f1-146">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="665f1-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="665f1-147">**应已阻止**：选择 "**网络钓鱼**" 或 "**恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="665f1-148">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="665f1-148">When you're finished, click the **Submit** button.</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="665f1-150">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="665f1-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="665f1-151">在 "**对象类型**" 部分，选择 "**附件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="665f1-152">单击 "**选择文件**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-152">Click **Choose File**.</span></span> <span data-ttu-id="665f1-153">在打开的对话框中，查找并选择文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="665f1-154">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="665f1-155">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="665f1-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="665f1-156">**应已被阻止**：**恶意软件**是唯一的选择，并且会自动选中。</span><span class="sxs-lookup"><span data-stu-id="665f1-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="665f1-157">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="665f1-157">When you're finished, click the **Submit** button.</span></span>

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="665f1-159">查看管理提交</span><span class="sxs-lookup"><span data-stu-id="665f1-159">View admin submissions</span></span>

1. <span data-ttu-id="665f1-160">在安全 & 合规性中心中，转到 "**威胁管理**" \> **查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="665f1-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="665f1-161">在显示的 "**提交**" 页面上，验证 "**管理员提交**" 选项卡是否已选中。</span><span class="sxs-lookup"><span data-stu-id="665f1-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="665f1-162">在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以按**提交 ID** (筛选器分配给每个提交) 的 GUID 值，方法是在框中输入一个值，然后单击 " ![ 刷新" ](../../media/scc-quarantine-refresh.png) 按钮。</span><span class="sxs-lookup"><span data-stu-id="665f1-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="665f1-163">Update</span><span class="sxs-lookup"><span data-stu-id="665f1-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="665f1-164">若要更改筛选条件，请单击 "**提交 ID** " 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="665f1-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="665f1-165">**Sender**</span></span>
- <span data-ttu-id="665f1-166">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="665f1-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="665f1-167">**提交者**</span><span class="sxs-lookup"><span data-stu-id="665f1-167">**Submitted by**</span></span>
- <span data-ttu-id="665f1-168">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-168">**Submission type**</span></span>
- <span data-ttu-id="665f1-169">**状态**</span><span class="sxs-lookup"><span data-stu-id="665f1-169">**Status**</span></span>

![用于管理提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="665f1-171">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="665f1-172">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="665f1-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="665f1-173">在图形下方有三个选项卡：**电子邮件** (默认) 、 **URL**和**附件**。</span><span class="sxs-lookup"><span data-stu-id="665f1-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="665f1-174">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="665f1-174">View admin email submissions</span></span>

<span data-ttu-id="665f1-175">单击 "**电子邮件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="665f1-175">Click the **Email** tab.</span></span>

<span data-ttu-id="665f1-176">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="665f1-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="665f1-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="665f1-177">**Date**</span></span>
- <span data-ttu-id="665f1-178">**提交 ID**：分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="665f1-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="665f1-179">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-180">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="665f1-181">**Sender**</span></span>
- <span data-ttu-id="665f1-182">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-183">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-183">**Submission type**</span></span>
- <span data-ttu-id="665f1-184">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="665f1-184">**Delivery reason**</span></span>
- <span data-ttu-id="665f1-185">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-186">**控件类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-186">**Control type**</span></span>
- <span data-ttu-id="665f1-187">**控制源**</span><span class="sxs-lookup"><span data-stu-id="665f1-187">**Control source**</span></span>

  <span data-ttu-id="665f1-188"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="665f1-189">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="665f1-189">View admin URL submissions</span></span>

<span data-ttu-id="665f1-190">单击 " **URL** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="665f1-190">Click the **URL** tab.</span></span>

<span data-ttu-id="665f1-191">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="665f1-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="665f1-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="665f1-192">**Date**</span></span>
- <span data-ttu-id="665f1-193">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="665f1-193">**Submission ID**</span></span>
- <span data-ttu-id="665f1-194">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-196">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-196">**Submission type**</span></span>
- <span data-ttu-id="665f1-197">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="665f1-198"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="665f1-199">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="665f1-199">View admin attachment submissions</span></span>

<span data-ttu-id="665f1-200">单击 "**附件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="665f1-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="665f1-201">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="665f1-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="665f1-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="665f1-202">**Date**</span></span>
- <span data-ttu-id="665f1-203">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="665f1-203">**Submission ID**</span></span>
- <span data-ttu-id="665f1-204">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-205">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-206">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-206">**Submission type**</span></span>
- <span data-ttu-id="665f1-207">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="665f1-208"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="665f1-209">查看向 Microsoft 提交的用户</span><span class="sxs-lookup"><span data-stu-id="665f1-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="665f1-210">如果已部署[报告邮件加载项](enable-the-report-message-add-in.md)，或者用户在[Web 上使用 Outlook 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)功能，则可以在 "**用户提交**" 选项卡上查看要报告的用户。</span><span class="sxs-lookup"><span data-stu-id="665f1-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="665f1-211">在安全 & 合规性中心中，转到 "**威胁管理**" \> **查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="665f1-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="665f1-212">在出现的 "**提交**" 页面上，单击 "**用户提交**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="665f1-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="665f1-213">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="665f1-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="665f1-214">**提交于**</span><span class="sxs-lookup"><span data-stu-id="665f1-214">**Submitted on**</span></span>
- <span data-ttu-id="665f1-215">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-216">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="665f1-217">**Sender**</span></span>
- <span data-ttu-id="665f1-218">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-219">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-219">**Submission type**</span></span>

<span data-ttu-id="665f1-220"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="665f1-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="665f1-221">在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以通过在框中输入值并单击 "刷新" 按钮来按**发件人**进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="665f1-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="665f1-222">Update</span><span class="sxs-lookup"><span data-stu-id="665f1-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="665f1-223">若要更改筛选条件，请单击 "**发件人**" 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="665f1-224">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="665f1-224">**Sender domain**</span></span>
- <span data-ttu-id="665f1-225">**主题**</span><span class="sxs-lookup"><span data-stu-id="665f1-225">**Subject**</span></span>
- <span data-ttu-id="665f1-226">**提交者**</span><span class="sxs-lookup"><span data-stu-id="665f1-226">**Submitted by**</span></span>
- <span data-ttu-id="665f1-227">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-227">**Submission type**</span></span>
- <span data-ttu-id="665f1-228">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="665f1-228">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="665f1-230">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="665f1-231">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="665f1-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="665f1-232">查看到自定义邮箱的用户提交</span><span class="sxs-lookup"><span data-stu-id="665f1-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="665f1-233">如果您已[将自定义邮箱配置](user-submission.md)为接收用户报告的邮件，则可以查看并提交传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="665f1-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="665f1-234">在安全 & 合规性中心中，转到 "**威胁管理**" \> **查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="665f1-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="665f1-235">在显示的 "**提交**" 页面上，单击 "**自定义邮箱**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="665f1-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="665f1-236">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="665f1-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="665f1-237">**提交于**</span><span class="sxs-lookup"><span data-stu-id="665f1-237">**Submitted on**</span></span>
- <span data-ttu-id="665f1-238">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-239">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="665f1-240">**Sender**</span></span>
- <span data-ttu-id="665f1-241">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="665f1-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="665f1-242">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="665f1-242">**Submission type**</span></span>

<span data-ttu-id="665f1-243">在页面顶部附近，可以输入开始日期和结束日期，您可以通过在框中输入值并单击 "刷新" 按钮来按**提交的**方式进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="665f1-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="665f1-244">Update</span><span class="sxs-lookup"><span data-stu-id="665f1-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="665f1-245">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="665f1-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="665f1-246">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="665f1-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="665f1-247">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="665f1-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="665f1-248">如果已将自定义邮箱配置为在不向 Microsoft 发送邮件的情况下截获用户报告的邮件，则可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="665f1-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="665f1-249">这将有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="665f1-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="665f1-250">在 "**自定义邮箱**" 选项卡上，选择列表中的一封邮件，单击 "**操作**" 按钮，然后进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="665f1-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="665f1-251">**报告清理**</span><span class="sxs-lookup"><span data-stu-id="665f1-251">**Report clean**</span></span>
- <span data-ttu-id="665f1-252">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="665f1-252">**Report phishing**</span></span>
- <span data-ttu-id="665f1-253">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="665f1-253">**Report malware**</span></span>
- <span data-ttu-id="665f1-254">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="665f1-254">**Report spam**</span></span>

!["操作" 按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
