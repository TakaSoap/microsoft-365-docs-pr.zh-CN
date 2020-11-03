---
title: 管理员提交
f1.keywords:
- NOCSH
ms.author: chrisda
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
description: 管理员可以了解如何使用安全 & 合规性中心中的提交门户将可疑的电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件提交到 Microsoft 进行扫描。
ms.openlocfilehash: 1ca1dc5e740aa5aa03a4c8b0c138eadb55c08a20
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844640"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="7ae78-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ae78-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7ae78-104">在 Exchange Online 中有邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规性中心中的提交门户将电子邮件、Url 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="7ae78-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="7ae78-105">当您提交电子邮件时，您将获得可能允许传入的电子邮件进入租户的任何策略的信息，以及对邮件中的任何 Url 和附件的检查。</span><span class="sxs-lookup"><span data-stu-id="7ae78-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="7ae78-106">可能允许邮件的策略包括单个用户的安全发件人列表以及租户级别策略（如 Exchange 邮件流规则） (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="7ae78-107">有关向 Microsoft 提交电子邮件、Url 和附件的其他方法，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae78-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ae78-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="7ae78-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ae78-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="7ae78-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7ae78-110">若要直接转到 **提交** 页面，请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="7ae78-111">若要向 Microsoft 提交邮件和文件，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="7ae78-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="7ae78-112">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。</span><span class="sxs-lookup"><span data-stu-id="7ae78-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="7ae78-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **组织管理** 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="7ae78-114">请注意，此角色组中的成员身份是 [查看用户提交到自定义邮箱的](#view-user-submissions-to-the-custom-mailbox) 必要条件，如本主题后面所述。</span><span class="sxs-lookup"><span data-stu-id="7ae78-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="7ae78-115">有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅 [向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7ae78-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="7ae78-116">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="7ae78-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="7ae78-117">在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **提交** "，确认您在 " **管理员提交** " 选项卡上，然后单击 " **新建提交** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="7ae78-118">使用在提交邮件、URL 或附件时出现的 **新提交** 浮出控件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="7ae78-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="7ae78-119">将可疑电子邮件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ae78-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="7ae78-120">在 " **对象类型** " 部分，选择 " **电子邮件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="7ae78-121">在 " **提交格式** " 部分，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="7ae78-122">**网络邮件 ID** ：这是邮件中 **X--组织网络-邮件 ID** 标头中可用的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="7ae78-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="7ae78-123">**文件** ：单击 " **选择文件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-123">**File** : Click **Choose file**.</span></span> <span data-ttu-id="7ae78-124">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击 " **打开** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="7ae78-125">在 " **收件人** " 部分，指定要对其运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="7ae78-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="7ae78-126">策略检查将确定电子邮件是否因用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="7ae78-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="7ae78-127">在 " **提交原因** " 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ae78-128">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="7ae78-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ae78-129">**应已阻止** ：选择 " **垃圾邮件** "、" **网络钓鱼** " 或 " **恶意软件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware**.</span></span> <span data-ttu-id="7ae78-130">如果你不确定，请使用你的最佳判断力。</span><span class="sxs-lookup"><span data-stu-id="7ae78-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="7ae78-131">如果由于提交策略而绕过筛选器，你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="7ae78-132">如果筛选器由于一个或多个策略而被绕过，扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="7ae78-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="7ae78-133">您将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="7ae78-134">这包括策略检查结果和重新扫描判定结果。</span><span class="sxs-lookup"><span data-stu-id="7ae78-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="7ae78-135">注意这不会再次通过 Microsoft Defender for Office 365 完全筛选堆栈运行电子邮件，但会根据邮件、URL 或文件的某些属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="7ae78-135">Note this does not run the email through the Microsoft Defender for Office 365 full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="7ae78-136">完成后，单击 " **提交** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="7ae78-136">When you're finished, click the **Submit** button.</span></span>

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="7ae78-138">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="7ae78-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="7ae78-139">在 " **对象类型** " 部分，选择 " **URL** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="7ae78-140">在出现的框中，输入完整的 URL (例如， `https://www.fabrikam.com/marketing.html`) 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="7ae78-141">在 " **提交原因** " 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ae78-142">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="7ae78-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ae78-143">**应已阻止** ：选择 " **网络钓鱼** " 或 " **恶意软件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-143">**Should have been blocked** : Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="7ae78-144">完成后，单击 " **提交** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="7ae78-144">When you're finished, click the **Submit** button.</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="7ae78-146">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ae78-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="7ae78-147">在 " **对象类型** " 部分，选择 " **附件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="7ae78-148">单击 " **选择文件** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-148">Click **Choose File**.</span></span> <span data-ttu-id="7ae78-149">在打开的对话框中，查找并选择文件，然后单击 " **打开** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="7ae78-150">在 " **提交原因** " 部分，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ae78-151">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="7ae78-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ae78-152">**应已被阻止** ： **恶意软件** 是唯一的选择，并且会自动选中。</span><span class="sxs-lookup"><span data-stu-id="7ae78-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="7ae78-153">完成后，单击 " **提交** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="7ae78-153">When you're finished, click the **Submit** button.</span></span>

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="7ae78-155">查看管理提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-155">View admin submissions</span></span>

<span data-ttu-id="7ae78-156">在 "安全性 & 合规性中心" 中，转到 " **威胁管理** \> **提交** "，确认您在 " **管理员提交** " 选项卡上，然后单击 " **新建提交** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="7ae78-157">在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以按 **提交 ID** (筛选器分配给每个提交) 的 GUID 值，方法是在框中输入一个值，然后单击 " ![ 刷新" ](../../media/scc-quarantine-refresh.png) 按钮。</span><span class="sxs-lookup"><span data-stu-id="7ae78-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ae78-158">Update</span><span class="sxs-lookup"><span data-stu-id="7ae78-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ae78-159">若要更改筛选条件，请单击 " **提交 ID** " 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="7ae78-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ae78-160">**Sender**</span></span>
- <span data-ttu-id="7ae78-161">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="7ae78-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="7ae78-162">**提交者**</span><span class="sxs-lookup"><span data-stu-id="7ae78-162">**Submitted by**</span></span>
- <span data-ttu-id="7ae78-163">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-163">**Submission type**</span></span>
- <span data-ttu-id="7ae78-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="7ae78-164">**Status**</span></span>

![用于管理提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="7ae78-166">若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ae78-167">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="7ae78-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="7ae78-168">在图形下方有三个选项卡： **电子邮件** (默认) 、 **URL** 和 **附件** 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="7ae78-169">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-169">View admin email submissions</span></span>

<span data-ttu-id="7ae78-170">单击 " **电子邮件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ae78-170">Click the **Email** tab.</span></span>

<span data-ttu-id="7ae78-171">您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="7ae78-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ae78-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="7ae78-172">**Date**</span></span>
- <span data-ttu-id="7ae78-173">**提交 ID** ：分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="7ae78-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="7ae78-174">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-175">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ae78-176">**Sender**</span></span>
- <span data-ttu-id="7ae78-177">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-178">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-178">**Submission type**</span></span>
- <span data-ttu-id="7ae78-179">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="7ae78-179">**Delivery reason**</span></span>
- <span data-ttu-id="7ae78-180">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-181">**控件类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-181">**Control type**</span></span>
- <span data-ttu-id="7ae78-182">**控制源**</span><span class="sxs-lookup"><span data-stu-id="7ae78-182">**Control source**</span></span>

  <span data-ttu-id="7ae78-183"><sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="7ae78-184">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-184">View admin URL submissions</span></span>

<span data-ttu-id="7ae78-185">单击 " **URL** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ae78-185">Click the **URL** tab.</span></span>

<span data-ttu-id="7ae78-186">您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="7ae78-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ae78-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="7ae78-187">**Date**</span></span>
- <span data-ttu-id="7ae78-188">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="7ae78-188">**Submission ID**</span></span>
- <span data-ttu-id="7ae78-189">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-191">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-191">**Submission type**</span></span>
- <span data-ttu-id="7ae78-192">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7ae78-193"><sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="7ae78-194">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-194">View admin attachment submissions</span></span>

<span data-ttu-id="7ae78-195">单击 " **附件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ae78-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="7ae78-196">您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="7ae78-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ae78-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="7ae78-197">**Date**</span></span>
- <span data-ttu-id="7ae78-198">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="7ae78-198">**Submission ID**</span></span>
- <span data-ttu-id="7ae78-199">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-200">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-201">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-201">**Submission type**</span></span>
- <span data-ttu-id="7ae78-202">**状态值**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7ae78-203"><sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="7ae78-204">查看向 Microsoft 提交的用户</span><span class="sxs-lookup"><span data-stu-id="7ae78-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="7ae78-205">如果已部署 [报告邮件加载项](enable-the-report-message-add-in.md)，或者用户在 [Web 上使用 Outlook 中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)功能，则可以在 " **用户提交** " 选项卡上查看要报告的用户。</span><span class="sxs-lookup"><span data-stu-id="7ae78-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="7ae78-206">在安全 & 合规性中心中，转到 " **威胁管理** \> **提交** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7ae78-207">选择 " **用户提交** " 选项卡，然后单击 " **新建提交** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="7ae78-208">您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="7ae78-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ae78-209">**提交于**</span><span class="sxs-lookup"><span data-stu-id="7ae78-209">**Submitted on**</span></span>
- <span data-ttu-id="7ae78-210">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-211">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ae78-212">**Sender**</span></span>
- <span data-ttu-id="7ae78-213">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-214">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-214">**Submission type**</span></span>

<span data-ttu-id="7ae78-215"><sup>\*</sup> 如果单击此值，则会在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ae78-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="7ae78-216">在页面顶部附近，您可以输入开始日期、结束日期和 (默认情况下) 您可以通过在框中输入值并单击 "刷新" 按钮来按 **发件人** 进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ae78-217">Update</span><span class="sxs-lookup"><span data-stu-id="7ae78-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ae78-218">若要更改筛选条件，请单击 " **发件人** " 按钮，然后选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="7ae78-219">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="7ae78-219">**Sender domain**</span></span>
- <span data-ttu-id="7ae78-220">**主题**</span><span class="sxs-lookup"><span data-stu-id="7ae78-220">**Subject**</span></span>
- <span data-ttu-id="7ae78-221">**提交者**</span><span class="sxs-lookup"><span data-stu-id="7ae78-221">**Submitted by**</span></span>
- <span data-ttu-id="7ae78-222">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-222">**Submission type**</span></span>
- <span data-ttu-id="7ae78-223">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="7ae78-223">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="7ae78-225">若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ae78-226">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="7ae78-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="7ae78-227">查看到自定义邮箱的用户提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="7ae78-228">**如果** 您已 [将自定义邮箱配置](user-submission.md) 为接收用户报告的邮件，则可以查看并提交传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="7ae78-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="7ae78-229">在安全 & 合规性中心中，转到 " **威胁管理** \> **提交** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7ae78-230">选择 " **自定义邮箱** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ae78-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="7ae78-231">您可以单击页面底部附近的 " **列选项** " 按钮，在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="7ae78-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ae78-232">**提交于**</span><span class="sxs-lookup"><span data-stu-id="7ae78-232">**Submitted on**</span></span>
- <span data-ttu-id="7ae78-233">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-234">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ae78-235">**Sender**</span></span>
- <span data-ttu-id="7ae78-236">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ae78-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ae78-237">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="7ae78-237">**Submission type**</span></span>

<span data-ttu-id="7ae78-238">在页面顶部附近，可以输入开始日期和结束日期，您可以通过在框中输入值并单击 "刷新" 按钮来按 **提交的** 方式进行筛选 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="7ae78-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ae78-239">Update</span><span class="sxs-lookup"><span data-stu-id="7ae78-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ae78-240">若要导出结果，请单击页面顶部附近的 " **导出** "，然后选择 " **图表数据** " 或 " **表格** "。</span><span class="sxs-lookup"><span data-stu-id="7ae78-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ae78-241">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="7ae78-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="7ae78-242">撤消用户提交</span><span class="sxs-lookup"><span data-stu-id="7ae78-242">Undo user submissions</span></span>

<span data-ttu-id="7ae78-243">用户将可疑电子邮件提交到自定义邮箱后，用户和管理员不能选择撤消提交。</span><span class="sxs-lookup"><span data-stu-id="7ae78-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="7ae78-244">如果用户想要恢复该电子邮件，则可在 "已删除邮件" 或 "垃圾邮件" 文件夹中进行恢复。</span><span class="sxs-lookup"><span data-stu-id="7ae78-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="7ae78-245">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="7ae78-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="7ae78-246">如果已将自定义邮箱配置为在不向 Microsoft 发送邮件的情况下截获用户报告的邮件，则可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="7ae78-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="7ae78-247">这将有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="7ae78-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="7ae78-248">在 " **自定义邮箱** " 选项卡上，选择列表中的一封邮件，单击 " **操作** " 按钮，然后进行下列选择之一：</span><span class="sxs-lookup"><span data-stu-id="7ae78-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="7ae78-249">**报告清理**</span><span class="sxs-lookup"><span data-stu-id="7ae78-249">**Report clean**</span></span>
- <span data-ttu-id="7ae78-250">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="7ae78-250">**Report phishing**</span></span>
- <span data-ttu-id="7ae78-251">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="7ae78-251">**Report malware**</span></span>
- <span data-ttu-id="7ae78-252">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="7ae78-252">**Report spam**</span></span>

!["操作" 按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
