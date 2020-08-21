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
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的"提交"门户将可疑的电子邮件、疑头发邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交给 Microsoft 进行扫描。
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845962"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="e94a0-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e94a0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="e94a0-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，管理员可以使用安全 & 合规中心中的提交门户将电子邮件、URL 和附件提交给 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="e94a0-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="e94a0-105">提交电子邮件时，你将获得有关可能允许传入电子邮件进入租户的所有策略的信息，并查看邮件中的任何 URL 和附件。</span><span class="sxs-lookup"><span data-stu-id="e94a0-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="e94a0-106">可能允许邮件的策略包括单个用户的安全发件人列表和租户级策略（如 Exchange 邮件流规则 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="e94a0-107">有关提交电子邮件、URL 和附件给 Microsoft 的其他方法，请参阅"[报告邮件和文件到 Microsoft"。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e94a0-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e94a0-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e94a0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e94a0-109">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="e94a0-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e94a0-110">若要直接转到"提交 **"** 页面，请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="e94a0-111">你必须首先分配有权限，然后才能执行本主题中的步骤：</span><span class="sxs-lookup"><span data-stu-id="e94a0-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="e94a0-112">要向 Microsoft 提交邮件和文件，您必须是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="e94a0-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e94a0-113">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="e94a0-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e94a0-114">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。</span><span class="sxs-lookup"><span data-stu-id="e94a0-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="e94a0-115">若要获取对提交门户的只读访问权限，你需要是以下角色组的成员之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e94a0-116">[安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。</span><span class="sxs-lookup"><span data-stu-id="e94a0-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e94a0-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。</span><span class="sxs-lookup"><span data-stu-id="e94a0-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="e94a0-118">有关用户如何向 Microsoft 提交邮件和文件的详细信息，请参阅"[报告邮件和文件"发送给 Microsoft。](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e94a0-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="e94a0-119">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="e94a0-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="e94a0-120">在安全与 &合规中心内，转到 **"威**胁 \> **管理提交**"，验证你是否在"**管理员提交"** 选项卡上，然后单击"新建**提交"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="e94a0-121">使用 **似** 下来提交邮件、URL 或附件的新提交浮出控件，如下面各节中所述。</span><span class="sxs-lookup"><span data-stu-id="e94a0-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e94a0-122">向 Microsoft 提交可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="e94a0-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="e94a0-123">在"对象**类型"部分**，选择"**电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="e94a0-124">在" **提交格式** "部分，使用下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="e94a0-125">**网络消息 ID：** 这是在邮件的 **X-MS-Exchange-Organization-Network-Message-Id 标头中可用的** GUID 值。</span><span class="sxs-lookup"><span data-stu-id="e94a0-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="e94a0-126">**文件**：单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="e94a0-127">在打开的对话框中，找到并选择 .eml 或 .msg 文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="e94a0-128">在 **"收件人** "部分，指定要对其运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="e94a0-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="e94a0-129">策略检查将确定是否由于用户或组织策略绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="e94a0-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="e94a0-130">在" **提交的原因** "部分，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e94a0-131">**不应已经阻止**</span><span class="sxs-lookup"><span data-stu-id="e94a0-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e94a0-132">**应已阻止：\*\*\*\*选择垃圾邮件\*\*\*\*、网络钓鱼**或**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="e94a0-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="e94a0-133">如果你不确定，请使用最佳问题。</span><span class="sxs-lookup"><span data-stu-id="e94a0-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="e94a0-134">如果在提交后策略导致筛选器被绕过，则你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="e94a0-135">如果由于一个或多个策略而导致未绕过筛选器，则扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="e94a0-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="e94a0-136">你将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="e94a0-137">这包括策略检查结果和重新扫描的版本。</span><span class="sxs-lookup"><span data-stu-id="e94a0-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="e94a0-138">请注意，这不会再次通过 Office 365 ATP 完整筛选堆栈运行电子邮件，而是基于邮件、URL 或文件的特定属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="e94a0-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="e94a0-139">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e94a0-139">When you're finished, click the **Submit** button.</span></span>

![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e94a0-141">将可自定义 URL 发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e94a0-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="e94a0-142">在"对象**类型"部分**，选择 **"URL"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="e94a0-143">在出现的框中，输入完整的 URL (例如 <https://www.fabrikam.com/marketing.html>) 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="e94a0-144">在" **提交的原因** "部分，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e94a0-145">**不应已经阻止**</span><span class="sxs-lookup"><span data-stu-id="e94a0-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e94a0-146">**应该已阻止：** 选择 **网络钓鱼** 或 **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="e94a0-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="e94a0-147">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e94a0-147">When you're finished, click the **Submit** button.</span></span>

![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="e94a0-149">将可检查的文件提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e94a0-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="e94a0-150">在"对象**类型"部分**，选择"附件 **"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="e94a0-151">单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-151">Click **Choose File**.</span></span> <span data-ttu-id="e94a0-152">在打开的对话框中，找到并选择文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="e94a0-153">在" **提交的原因** "部分，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e94a0-154">**不应已经阻止**</span><span class="sxs-lookup"><span data-stu-id="e94a0-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e94a0-155">**应已阻止："\*\*\*\*只"** 恶意软件"是唯一选择，并自动选择。</span><span class="sxs-lookup"><span data-stu-id="e94a0-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="e94a0-156">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e94a0-156">When you're finished, click the **Submit** button.</span></span>

![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="e94a0-158">查看管理员提交</span><span class="sxs-lookup"><span data-stu-id="e94a0-158">View admin submissions</span></span>

<span data-ttu-id="e94a0-159">在安全与 &合规中心内，转到 **"威**胁 \> **管理提交**"，验证你是否在"**管理员提交"** 选项卡上，然后单击"新建**提交"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e94a0-160">在页面顶部区域的开头，可以输入开始日期、结束日期和 (默认情况下) 你可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (进行筛选，即分配给每个提交) 的 GUID ![ 值 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e94a0-161">Update</span><span class="sxs-lookup"><span data-stu-id="e94a0-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e94a0-162">若要更改筛选条件，请单击提交 **ID 按钮** ，然后选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="e94a0-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e94a0-163">**Sender**</span></span>
- <span data-ttu-id="e94a0-164">**使用者/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="e94a0-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="e94a0-165">**提交者**</span><span class="sxs-lookup"><span data-stu-id="e94a0-165">**Submitted by**</span></span>
- <span data-ttu-id="e94a0-166">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-166">**Submission type**</span></span>
- <span data-ttu-id="e94a0-167">**状态**</span><span class="sxs-lookup"><span data-stu-id="e94a0-167">**Status**</span></span>

![筛选管理提交选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="e94a0-169">要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e94a0-170">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e94a0-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="e94a0-171">在图下方有三个**选项卡：电子邮件** (个) **URL，和\*\*\*\*附件**。</span><span class="sxs-lookup"><span data-stu-id="e94a0-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="e94a0-172">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="e94a0-172">View admin email submissions</span></span>

<span data-ttu-id="e94a0-173">单击" **电子邮件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e94a0-173">Click the **Email** tab.</span></span>

<span data-ttu-id="e94a0-174">可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e94a0-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e94a0-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="e94a0-175">**Date**</span></span>
- <span data-ttu-id="e94a0-176">**提交 ID：** 分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="e94a0-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="e94a0-177">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-178">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e94a0-179">**Sender**</span></span>
- <span data-ttu-id="e94a0-180">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-181">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-181">**Submission type**</span></span>
- <span data-ttu-id="e94a0-182">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="e94a0-182">**Delivery reason**</span></span>
- <span data-ttu-id="e94a0-183">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-184">**控件类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-184">**Control type**</span></span>
- <span data-ttu-id="e94a0-185">**控件源**</span><span class="sxs-lookup"><span data-stu-id="e94a0-185">**Control source**</span></span>

  <span data-ttu-id="e94a0-186"><sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="e94a0-187">查看管理 URL 提交</span><span class="sxs-lookup"><span data-stu-id="e94a0-187">View admin URL submissions</span></span>

<span data-ttu-id="e94a0-188">单击 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e94a0-188">Click the **URL** tab.</span></span>

<span data-ttu-id="e94a0-189">可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e94a0-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e94a0-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="e94a0-190">**Date**</span></span>
- <span data-ttu-id="e94a0-191">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="e94a0-191">**Submission ID**</span></span>
- <span data-ttu-id="e94a0-192">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-194">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-194">**Submission type**</span></span>
- <span data-ttu-id="e94a0-195">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e94a0-196"><sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="e94a0-197">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="e94a0-197">View admin attachment submissions</span></span>

<span data-ttu-id="e94a0-198">单击" **附件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e94a0-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="e94a0-199">可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e94a0-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e94a0-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="e94a0-200">**Date**</span></span>
- <span data-ttu-id="e94a0-201">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="e94a0-201">**Submission ID**</span></span>
- <span data-ttu-id="e94a0-202">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-203">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-204">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-204">**Submission type**</span></span>
- <span data-ttu-id="e94a0-205">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e94a0-206"><sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="e94a0-207">查看用户提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e94a0-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="e94a0-208">如果已部署报告 [邮件加载项或](enable-the-report-message-add-in.md)用户使用 Outlook 网页 [版中的内置报告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)，可以在"用户提交"选项卡上 **查看有哪些用户报告** 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="e94a0-209">在安全与&合规中心内，转到 **威胁** \> **管理提交**。</span><span class="sxs-lookup"><span data-stu-id="e94a0-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e94a0-210">选择"**用户提交"** 选项卡，然后单击"新建**提交"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="e94a0-211">可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e94a0-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e94a0-212">**Submitted on - 提交时间**</span><span class="sxs-lookup"><span data-stu-id="e94a0-212">**Submitted on**</span></span>
- <span data-ttu-id="e94a0-213">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-214">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e94a0-215">**Sender**</span></span>
- <span data-ttu-id="e94a0-216">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-217">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-217">**Submission type**</span></span>

<span data-ttu-id="e94a0-218"><sup>\*</sup> 如果你单击此值，则在浮出控件中显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="e94a0-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="e94a0-219">在页面顶部区域的开头，可以输入开始日期、结束日期和 (默认情况下) 您可以按 **发件人进行筛选** ，方法是在框中输入值，然后单击"刷新 ![ "按钮 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e94a0-220">Update</span><span class="sxs-lookup"><span data-stu-id="e94a0-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e94a0-221">若要更改筛选条件，请单击"发件人 **"** 按钮，并选择以下值之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="e94a0-222">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="e94a0-222">**Sender domain**</span></span>
- <span data-ttu-id="e94a0-223">**主题**</span><span class="sxs-lookup"><span data-stu-id="e94a0-223">**Subject**</span></span>
- <span data-ttu-id="e94a0-224">**提交者**</span><span class="sxs-lookup"><span data-stu-id="e94a0-224">**Submitted by**</span></span>
- <span data-ttu-id="e94a0-225">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-225">**Submission type**</span></span>
- <span data-ttu-id="e94a0-226">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="e94a0-226">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="e94a0-228">要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e94a0-229">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e94a0-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="e94a0-230">查看用户提交到自定义邮箱</span><span class="sxs-lookup"><span data-stu-id="e94a0-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="e94a0-231">如果您配置了 [自定义邮箱以](user-submission.md) 接收用户报告的邮件，则您可以查看和提交已传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="e94a0-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="e94a0-232">在安全与&合规中心内，转到 **威胁** \> **管理提交**。</span><span class="sxs-lookup"><span data-stu-id="e94a0-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="e94a0-233">选择" **自定义邮箱"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e94a0-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="e94a0-234">可单击页面 **底部** 近的"列选项"按钮以在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="e94a0-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e94a0-235">**Submitted on - 提交时间**</span><span class="sxs-lookup"><span data-stu-id="e94a0-235">**Submitted on**</span></span>
- <span data-ttu-id="e94a0-236">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-237">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e94a0-238">**Sender**</span></span>
- <span data-ttu-id="e94a0-239">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e94a0-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e94a0-240">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="e94a0-240">**Submission type**</span></span>

<span data-ttu-id="e94a0-241">在页面顶部区域的开头，可以输入开始日期和结束日期，并可通过在 **框中** 输入值并单击"刷新"按钮来进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e94a0-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e94a0-242">Update</span><span class="sxs-lookup"><span data-stu-id="e94a0-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e94a0-243">要导出结果，请单击页面**顶部的"** 导出"，然后选择"图表数据 **"或**"**表"。**</span><span class="sxs-lookup"><span data-stu-id="e94a0-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="e94a0-244">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e94a0-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="e94a0-245">从自定义邮箱将邮件提交至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e94a0-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="e94a0-246">如果你已将自定义邮箱配置为截获用户报告的邮件，而不向 Microsoft 发送邮件，则您可以找到特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e94a0-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="e94a0-247">这可有效地将用户提交移至管理员提交。</span><span class="sxs-lookup"><span data-stu-id="e94a0-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="e94a0-248">在" **自定义邮箱** "选项卡上，在列表中选择邮件，再 **单击"操作** "按钮，然后做出以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="e94a0-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="e94a0-249">**报告干净报告**</span><span class="sxs-lookup"><span data-stu-id="e94a0-249">**Report clean**</span></span>
- <span data-ttu-id="e94a0-250">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="e94a0-250">**Report phishing**</span></span>
- <span data-ttu-id="e94a0-251">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="e94a0-251">**Report malware**</span></span>
- <span data-ttu-id="e94a0-252">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="e94a0-252">**Report spam**</span></span>

![操作按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
