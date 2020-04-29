---
title: 管理员提交、提交、垃圾邮件问题、误报、提交网络钓鱼、提交电子邮件进行扫描、在 Office 365 中使用可疑电子邮件、扫描邮件、使用 Microsoft 扫描网络钓鱼、使用 microsoft 扫描垃圾邮件、提交电子邮件、提交电子邮件、dodgy 电子邮件、错误演员邮件、可疑、不受信任的邮件、向 microsoft 报告诈骗电子邮件、向 microsoft 报告诈骗电子邮件，将电子邮件中的恶意软件报告给 Microsoft，收件箱中的垃圾邮件，电子邮件中的病毒
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
description: 了解如何将可疑电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件从公司的公司提交到 Microsoft 进行扫描。
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921493"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="501e2-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="501e2-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="501e2-104">如果您是使用 Exchange Online 中的邮箱的 Microsoft 365 组织中的管理员，则可以使用安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="501e2-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="501e2-105">当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。</span><span class="sxs-lookup"><span data-stu-id="501e2-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="501e2-106">可能允许邮件的策略包括单个用户的安全发件人列表和租户级策略，如 Exchange 邮件流规则（也称为传输规则）。</span><span class="sxs-lookup"><span data-stu-id="501e2-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="501e2-107">有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="501e2-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="501e2-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="501e2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="501e2-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="501e2-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="501e2-110">若要直接转到**提交**页面，请<https://protection.office.com/reportsubmission>使用。</span><span class="sxs-lookup"><span data-stu-id="501e2-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="501e2-111">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="501e2-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="501e2-112">若要添加、修改和删除反垃圾邮件策略，您必须是 "**组织管理**"、"**安全管理员**" 或 "**安全读者**" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="501e2-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="501e2-113">若要详细了解安全与合规中心内的角色组，请参阅[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="501e2-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="501e2-114">有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="501e2-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="501e2-115">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="501e2-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="501e2-116">在安全 & 合规性中心中，转到 "**威胁管理** \> "**查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="501e2-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="501e2-117">在显示的 "**提交**" 页面上，单击 "**新建提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="501e2-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="501e2-118">使用在提交邮件、URL 或附件时出现的**新提交**浮出控件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="501e2-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="501e2-119">将可疑电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="501e2-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="501e2-120">在 "**对象类型**" 部分，选择 "**电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="501e2-121">在 "**提交格式**" 部分，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="501e2-122">**网络邮件 ID**：这是邮件中**X--组织网络-邮件 ID**标头中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="501e2-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="501e2-123">**文件**：单击 "**选择文件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="501e2-124">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="501e2-125">在 "**收件人**" 部分，指定要对其运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="501e2-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="501e2-126">策略检查将确定电子邮件是否因用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="501e2-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="501e2-127">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="501e2-128">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="501e2-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="501e2-129">**应已阻止**：选择 "**垃圾邮件**"、"**网络钓鱼**" 或 "**恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="501e2-130">如果你不确定，请使用你的最佳判断力。</span><span class="sxs-lookup"><span data-stu-id="501e2-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="501e2-131">如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="501e2-132">如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="501e2-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="501e2-133">您将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="501e2-134">这包括策略检查结果和重新扫描判定结果。</span><span class="sxs-lookup"><span data-stu-id="501e2-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="501e2-135">注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="501e2-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="501e2-136">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="501e2-136">When you're finished, click the **Submit** button.</span></span>

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="501e2-138">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="501e2-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="501e2-139">在 "**对象类型**" 部分，选择 " **URL**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="501e2-140">在出现的框中，输入完整的 URL （例如， <https://www.fabrikam.com/marketing.html>）。</span><span class="sxs-lookup"><span data-stu-id="501e2-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="501e2-141">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="501e2-142">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="501e2-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="501e2-143">**应已阻止**：选择 "**网络钓鱼**" 或 "**恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="501e2-144">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="501e2-144">When you're finished, click the **Submit** button.</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="501e2-146">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="501e2-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="501e2-147">在 "**对象类型**" 部分，选择 "**附件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="501e2-148">单击 "**选择文件**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-148">Click **Choose File**.</span></span> <span data-ttu-id="501e2-149">在打开的对话框中，查找并选择文件，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="501e2-150">在 "**提交原因**" 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="501e2-151">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="501e2-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="501e2-152">**应已被阻止**：**恶意软件**是唯一的选择，并且会自动选中。</span><span class="sxs-lookup"><span data-stu-id="501e2-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="501e2-153">完成后，单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="501e2-153">When you're finished, click the **Submit** button.</span></span>

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="501e2-155">查看管理提交</span><span class="sxs-lookup"><span data-stu-id="501e2-155">View admin submissions</span></span>

1. <span data-ttu-id="501e2-156">在安全 & 合规性中心中，转到 "**威胁管理** \> "**查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="501e2-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="501e2-157">在显示的 "**提交**" 页面上，验证 "**管理员提交**" 选项卡是否已选中。</span><span class="sxs-lookup"><span data-stu-id="501e2-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="501e2-158">在页面顶部附近，可以输入开始日期、结束日期和（默认情况下）可以通过在框中输入值并单击!["刷新" 按钮](../../media/scc-quarantine-refresh.png)按**提交 ID**进行筛选。</span><span class="sxs-lookup"><span data-stu-id="501e2-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="501e2-159">Update</span><span class="sxs-lookup"><span data-stu-id="501e2-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="501e2-160">若要更改筛选条件，请单击 "**提交 ID** " 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="501e2-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="501e2-161">**Sender**</span></span>
- <span data-ttu-id="501e2-162">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="501e2-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="501e2-163">**提交者**</span><span class="sxs-lookup"><span data-stu-id="501e2-163">**Submitted by**</span></span>
- <span data-ttu-id="501e2-164">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-164">**Submission type**</span></span>
- <span data-ttu-id="501e2-165">**状态**</span><span class="sxs-lookup"><span data-stu-id="501e2-165">**Status**</span></span>

![用于管理提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="501e2-167">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="501e2-168">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="501e2-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="501e2-169">在图形下方有三个选项卡：**电子邮件**（默认）、 **URL**和**附件**。</span><span class="sxs-lookup"><span data-stu-id="501e2-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="501e2-170">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="501e2-170">View admin email submissions</span></span>

<span data-ttu-id="501e2-171">单击 "**电子邮件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="501e2-171">Click the **Email** tab.</span></span>

<span data-ttu-id="501e2-172">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="501e2-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="501e2-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="501e2-173">**Date**</span></span>
- <span data-ttu-id="501e2-174">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="501e2-174">**Submission ID**</span></span>
- <span data-ttu-id="501e2-175">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-176">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="501e2-177">**Sender**</span></span>
- <span data-ttu-id="501e2-178">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-179">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-179">**Submission type**</span></span>
- <span data-ttu-id="501e2-180">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="501e2-180">**Delivery reason**</span></span>
- <span data-ttu-id="501e2-181">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-182">**控件类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-182">**Control type**</span></span>
- <span data-ttu-id="501e2-183">**控制源**</span><span class="sxs-lookup"><span data-stu-id="501e2-183">**Control source**</span></span>

  <span data-ttu-id="501e2-184"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="501e2-185">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="501e2-185">View admin URL submissions</span></span>

<span data-ttu-id="501e2-186">单击 " **URL** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="501e2-186">Click the **URL** tab.</span></span>

<span data-ttu-id="501e2-187">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="501e2-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="501e2-188">**Date**</span><span class="sxs-lookup"><span data-stu-id="501e2-188">**Date**</span></span>
- <span data-ttu-id="501e2-189">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="501e2-189">**Submission ID**</span></span>
- <span data-ttu-id="501e2-190">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-192">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-192">**Submission type**</span></span>
- <span data-ttu-id="501e2-193">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="501e2-194"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="501e2-195">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="501e2-195">View admin attachment submissions</span></span>

<span data-ttu-id="501e2-196">单击 "**附件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="501e2-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="501e2-197">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="501e2-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="501e2-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="501e2-198">**Date**</span></span>
- <span data-ttu-id="501e2-199">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="501e2-199">**Submission ID**</span></span>
- <span data-ttu-id="501e2-200">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-201">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-202">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-202">**Submission type**</span></span>
- <span data-ttu-id="501e2-203">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="501e2-204"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="501e2-205">查看向 Microsoft 提交的用户</span><span class="sxs-lookup"><span data-stu-id="501e2-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="501e2-206">如果已部署[报告邮件加载项](enable-the-report-message-add-in.md)，或者用户在[Web 上使用 Outlook 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)功能，则可以在 "**用户提交**" 选项卡上查看要报告的用户。</span><span class="sxs-lookup"><span data-stu-id="501e2-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="501e2-207">在安全 & 合规性中心中，转到 "**威胁管理** \> "**查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="501e2-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="501e2-208">在出现的 "**提交**" 页面上，单击 "**用户提交**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="501e2-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="501e2-209">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="501e2-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="501e2-210">**提交于**</span><span class="sxs-lookup"><span data-stu-id="501e2-210">**Submitted on**</span></span>
- <span data-ttu-id="501e2-211">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-212">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="501e2-213">**Sender**</span></span>
- <span data-ttu-id="501e2-214">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-215">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-215">**Submission type**</span></span>

<span data-ttu-id="501e2-216"><sup>\*</sup>如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="501e2-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="501e2-217">在页面顶部附近，可以输入开始日期、结束日期和（默认情况下），您可以通过在框中输入值并单击!["刷新" 按钮](../../media/scc-quarantine-refresh.png)来筛选**发件人**。</span><span class="sxs-lookup"><span data-stu-id="501e2-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="501e2-218">Update</span><span class="sxs-lookup"><span data-stu-id="501e2-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="501e2-219">若要更改筛选条件，请单击 "**发件人**" 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="501e2-220">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="501e2-220">**Sender domain**</span></span>
- <span data-ttu-id="501e2-221">**主题**</span><span class="sxs-lookup"><span data-stu-id="501e2-221">**Subject**</span></span>
- <span data-ttu-id="501e2-222">**提交者**</span><span class="sxs-lookup"><span data-stu-id="501e2-222">**Submitted by**</span></span>
- <span data-ttu-id="501e2-223">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-223">**Submission type**</span></span>
- <span data-ttu-id="501e2-224">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="501e2-224">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="501e2-226">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="501e2-227">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="501e2-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="501e2-228">查看到自定义邮箱的用户提交</span><span class="sxs-lookup"><span data-stu-id="501e2-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="501e2-229">如果您已[将自定义邮箱配置](user-submission.md)为接收用户报告的邮件，则可以查看并提交传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="501e2-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="501e2-230">在安全 & 合规性中心中，转到 "**威胁管理** \> "**查看** \> **管理员提交消息**。</span><span class="sxs-lookup"><span data-stu-id="501e2-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="501e2-231">在显示的 "**提交**" 页面上，单击 "**自定义邮箱**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="501e2-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="501e2-232">您可以单击页面底部附近的 "**列选项**" 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="501e2-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="501e2-233">**提交于**</span><span class="sxs-lookup"><span data-stu-id="501e2-233">**Submitted on**</span></span>
- <span data-ttu-id="501e2-234">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-235">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="501e2-236">**Sender**</span></span>
- <span data-ttu-id="501e2-237">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="501e2-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="501e2-238">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="501e2-238">**Submission type**</span></span>

<span data-ttu-id="501e2-239">在页面顶部附近，可以输入开始日期和结束日期，您可以通过在框中输入值并单击!["刷新" 按钮](../../media/scc-quarantine-refresh.png)来按**提交的**方式进行筛选。</span><span class="sxs-lookup"><span data-stu-id="501e2-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="501e2-240">Update</span><span class="sxs-lookup"><span data-stu-id="501e2-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="501e2-241">若要导出结果，请单击页面顶部附近的 "**导出**"，然后选择 "**图表数据**" 或 "**表格**"。</span><span class="sxs-lookup"><span data-stu-id="501e2-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="501e2-242">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="501e2-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="501e2-243">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="501e2-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="501e2-244">如果已将自定义邮箱配置为在不向 Microsoft 发送邮件的情况下截获用户报告的邮件，则可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="501e2-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="501e2-245">这将有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="501e2-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="501e2-246">在 "**自定义邮箱**" 选项卡上，选择列表中的一封邮件，单击 "**操作**" 按钮，然后进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="501e2-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="501e2-247">**报告清理**</span><span class="sxs-lookup"><span data-stu-id="501e2-247">**Report clean**</span></span>
- <span data-ttu-id="501e2-248">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="501e2-248">**Report phishing**</span></span>
- <span data-ttu-id="501e2-249">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="501e2-249">**Report malware**</span></span>
- <span data-ttu-id="501e2-250">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="501e2-250">**Report spam**</span></span>

!["操作" 按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
