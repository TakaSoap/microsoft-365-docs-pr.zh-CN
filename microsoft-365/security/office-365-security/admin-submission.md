---
title: 管理员提交
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: 管理员可以了解如何使用安全与合规中心中的提交门户将可疑电子邮件、可疑网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、URL 和文件提交到 Microsoft 进行扫描。 &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288785"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="9cbe1-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cbe1-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9cbe1-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-104">**Applies to**</span></span>
- [<span data-ttu-id="9cbe1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9cbe1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9cbe1-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9cbe1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="9cbe1-107">在具有 Exchange & Online 邮箱的 Microsoft 365 组织中，管理员可以使用安全与合规中心中的提交门户将电子邮件、URL 和附件提交到 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="9cbe1-108">提交电子邮件时，将获取：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="9cbe1-109">**电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="9cbe1-110">**策略命中**：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖服务筛选器裁定。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="9cbe1-111">**有效负载信誉/触发**：检查邮件中任何 URL 和附件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="9cbe1-112">**成绩分析**：由人工评分人员进行审阅，以确认邮件是否是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cbe1-113">负载信誉/触发和评分器分析并非在所有租户中完成。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="9cbe1-114">当数据出于合规性目的不应离开租户边界时，将阻止信息进入组织外部。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="9cbe1-115">有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告 [邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9cbe1-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9cbe1-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9cbe1-117">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9cbe1-118">若要直接转到提交 **页面，** 请使用 <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="9cbe1-119">若要将邮件和文件提交到 Microsoft，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9cbe1-120">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="9cbe1-121">**Exchange** Online 中的 [组织管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="9cbe1-122">请注意，查看用户提交到自定义邮箱需要此[](#view-user-submissions-to-the-custom-mailbox)角色组成员身份，如本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="9cbe1-123">若要详细了解用户如何向 Microsoft 提交邮件和文件，请参阅向 Microsoft 报告 [邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="9cbe1-124">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="9cbe1-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="9cbe1-125">在安全&合规中心，转到 **"威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="9cbe1-126">使用 **显示为** 提交邮件、URL 或附件的新提交飞出，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="9cbe1-127">向 Microsoft 提交一封有问题的电子邮件</span><span class="sxs-lookup"><span data-stu-id="9cbe1-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="9cbe1-128">在"**对象类型"** 部分，选择 **"电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="9cbe1-129">在 **"提交格式** "部分中，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="9cbe1-130">**网络邮件 ID：** 这是一个 GUID 值，在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 标头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id** 标头中可用。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="9cbe1-131">**文件**：单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="9cbe1-132">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9cbe1-133">使用 Defender for Office 365 计划 1 或计划 2 的管理员可以提交 30 天之前的邮件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="9cbe1-134">其他管理员只能返回 7 天。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="9cbe1-135">在 **"收件人"** 部分中，指定要针对其运行策略检查的一个或多个收件人。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="9cbe1-136">策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="9cbe1-137">在 **"提交原因"部分** ，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9cbe1-138">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9cbe1-139">**应已被阻止：** 选择 **垃圾邮件**、**网络钓鱼或\*\*\*\*恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="9cbe1-140">如果你不确定，请使用最佳判断。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="9cbe1-141">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-141">When you're finished, click the **Submit** button.</span></span>

   ![URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="9cbe1-143">将可疑 URL 发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cbe1-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="9cbe1-144">在"**对象类型"** 部分，选择 **URL。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="9cbe1-145">在出现的框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="9cbe1-146">在 **"提交原因"部分** ，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9cbe1-147">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9cbe1-148">**应该已被阻止：** 选择 **网络钓鱼或\*\*\*\*恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="9cbe1-149">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-149">When you're finished, click the **Submit** button.</span></span>

   ![电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="9cbe1-151">将可疑文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9cbe1-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="9cbe1-152">在"**对象类型"** 部分，选择"**附件"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="9cbe1-153">单击 **"选择文件"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-153">Click **Choose File**.</span></span> <span data-ttu-id="9cbe1-154">在打开的对话框中，查找并选择文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="9cbe1-155">在 **"提交原因"部分** ，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9cbe1-156">**不应被阻止**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9cbe1-157">**应该已被阻止**： **恶意软件** 是唯一的选择，并且会自动选择。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="9cbe1-158">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-158">When you're finished, click the **Submit** button.</span></span>

   ![附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="9cbe1-160">查看管理员提交</span><span class="sxs-lookup"><span data-stu-id="9cbe1-160">View admin submissions</span></span>

<span data-ttu-id="9cbe1-161">在安全&合规中心，转到 **"威胁** 管理提交"，确认你位于"管理员提交"选项卡上， \> 然后单击"新建 **提交"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9cbe1-162">在页面顶部附近，你可以输入开始日期、结束日期和 (（默认情况下) 可以通过在框中输入值并单击"刷新"按钮，按提交 **ID** (筛选分配给每个提交) 的 GUID 值 ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9cbe1-163">Update</span><span class="sxs-lookup"><span data-stu-id="9cbe1-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9cbe1-164">若要更改筛选条件，请单击 **"提交 ID"** 按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="9cbe1-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-165">**Sender**</span></span>
- <span data-ttu-id="9cbe1-166">**主题/URL/文件名**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="9cbe1-167">**提交者**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-167">**Submitted by**</span></span>
- <span data-ttu-id="9cbe1-168">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-168">**Submission type**</span></span>
- <span data-ttu-id="9cbe1-169">"状态"</span><span class="sxs-lookup"><span data-stu-id="9cbe1-169">**Status**</span></span>

![管理员提交的筛选器选项](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="9cbe1-171">若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9cbe1-172">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="9cbe1-173">在图形下方，有三个选项卡：电子邮件 (默认 **) 、URL** 和 **附件**。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="9cbe1-174">查看管理员电子邮件提交</span><span class="sxs-lookup"><span data-stu-id="9cbe1-174">View admin email submissions</span></span>

<span data-ttu-id="9cbe1-175">单击 **"电子邮件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-175">Click the **Email** tab.</span></span>

<span data-ttu-id="9cbe1-176">可以单击页面 **底部附近的** "列选项"按钮在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9cbe1-177">"日期"</span><span class="sxs-lookup"><span data-stu-id="9cbe1-177">**Date**</span></span>
- <span data-ttu-id="9cbe1-178">**提交 ID：** 分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="9cbe1-179">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-180">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-181">**Sender**</span></span>
- <span data-ttu-id="9cbe1-182">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-183">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-183">**Submission type**</span></span>
- <span data-ttu-id="9cbe1-184">**传递原因**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-184">**Delivery reason**</span></span>
- <span data-ttu-id="9cbe1-185">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9cbe1-186"><sup>\*</sup> 如果单击此值，详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="9cbe1-187">管理员提交重新扫描详细信息</span><span class="sxs-lookup"><span data-stu-id="9cbe1-187">Admin submission rescan details</span></span>

<span data-ttu-id="9cbe1-188">在管理员提交中提交的邮件会重新扫描，并且结果显示在详细信息飞出中：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="9cbe1-189">如果在发送时发件人的电子邮件身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="9cbe1-190">有关可能影响或替代邮件裁定的任何策略命中的信息。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="9cbe1-191">当前触发结果，以查看邮件中包含的 URL 或文件是否恶意。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="9cbe1-192">来自成绩人员的反馈。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-192">Feedback from graders.</span></span>

<span data-ttu-id="9cbe1-193">如果发现覆盖，则重新扫描应在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="9cbe1-194">如果电子邮件身份验证没有问题，或者传递不受覆盖影响，则来自成绩人员的反馈可能需要一天的时间。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="9cbe1-195">查看管理员 URL 提交</span><span class="sxs-lookup"><span data-stu-id="9cbe1-195">View admin URL submissions</span></span>

<span data-ttu-id="9cbe1-196">单击 **"URL"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-196">Click the **URL** tab.</span></span>

<span data-ttu-id="9cbe1-197">可以单击页面 **底部附近的** "列选项"按钮在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9cbe1-198">"日期"</span><span class="sxs-lookup"><span data-stu-id="9cbe1-198">**Date**</span></span>
- <span data-ttu-id="9cbe1-199">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-199">**Submission ID**</span></span>
- <span data-ttu-id="9cbe1-200">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-202">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-202">**Submission type**</span></span>
- <span data-ttu-id="9cbe1-203">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9cbe1-204"><sup>\*</sup> 如果单击此值，详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="9cbe1-205">查看管理员附件提交</span><span class="sxs-lookup"><span data-stu-id="9cbe1-205">View admin attachment submissions</span></span>

<span data-ttu-id="9cbe1-206">单击 **"附件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="9cbe1-207">可以单击页面 **底部附近的** "列选项"按钮在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9cbe1-208">"日期"</span><span class="sxs-lookup"><span data-stu-id="9cbe1-208">**Date**</span></span>
- <span data-ttu-id="9cbe1-209">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-209">**Submission ID**</span></span>
- <span data-ttu-id="9cbe1-210">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-211">**文件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-212">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-212">**Submission type**</span></span>
- <span data-ttu-id="9cbe1-213">**状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9cbe1-214"><sup>\*</sup> 如果单击此值，详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="9cbe1-215">查看向 Microsoft 提交用户</span><span class="sxs-lookup"><span data-stu-id="9cbe1-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="9cbe1-216">如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用 Outlook [](enable-the-report-phish-add-in.md)[网页](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中的内置报告，可以在"用户提交"选项卡上查看用户报告的内容。 </span><span class="sxs-lookup"><span data-stu-id="9cbe1-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="9cbe1-217">在安全&合规中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9cbe1-218">选择 **"用户提交"** 选项卡，然后单击"**新建提交"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9cbe1-219">可以单击页面 **底部附近的** "列选项"按钮在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9cbe1-220">**提交于**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-220">**Submitted on**</span></span>
- <span data-ttu-id="9cbe1-221">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-222">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-223">**Sender**</span></span>
- <span data-ttu-id="9cbe1-224">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-225">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-225">**Submission type**</span></span>

<span data-ttu-id="9cbe1-226"><sup>\*</sup> 如果单击此值，详细信息将显示在一个标注中。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="9cbe1-227">在页面顶部附近，可以输入开始日期、结束日期和 (默认情况下) 可以通过在框中输入值并单击"刷新"按钮按发件人进行 ![ 筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9cbe1-228">Update</span><span class="sxs-lookup"><span data-stu-id="9cbe1-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9cbe1-229">若要更改筛选条件，请单击 **"发件人** "按钮并选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="9cbe1-230">**发件人域**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-230">**Sender domain**</span></span>
- <span data-ttu-id="9cbe1-231">**主题**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-231">**Subject**</span></span>
- <span data-ttu-id="9cbe1-232">**提交者**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-232">**Submitted by**</span></span>
- <span data-ttu-id="9cbe1-233">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-233">**Submission type**</span></span>
- <span data-ttu-id="9cbe1-234">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-234">**Sender IP**</span></span>

![用户提交的筛选器选项](../../media/user-submissions-filter-options.png)

<span data-ttu-id="9cbe1-236">若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9cbe1-237">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="9cbe1-238">查看用户提交到自定义邮箱</span><span class="sxs-lookup"><span data-stu-id="9cbe1-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="9cbe1-239">**如果** 已配置自定义 [邮箱](user-submission.md) 以接收用户报告的邮件，则还可以查看并提交已传递到报告邮箱的邮件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="9cbe1-240">在安全&合规中心，转到 **"威胁管理** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9cbe1-241">选择 **"自定义邮箱"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="9cbe1-242">可以单击页面 **底部附近的** "列选项"按钮在视图中添加或删除列：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9cbe1-243">**提交于**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-243">**Submitted on**</span></span>
- <span data-ttu-id="9cbe1-244">**提交者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-245">**主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-246">**Sender**</span></span>
- <span data-ttu-id="9cbe1-247">**发件人 IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9cbe1-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9cbe1-248">**提交类型**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-248">**Submission type**</span></span>

<span data-ttu-id="9cbe1-249">在页面顶部附近，可以输入开始日期、结束日期，并且可以通过在框中输入值并单击"刷新"按钮按"提交 ![ "进行筛选 ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9cbe1-250">Update</span><span class="sxs-lookup"><span data-stu-id="9cbe1-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9cbe1-251">若要导出结果，请单击页面 **顶部附近的**"导出"，然后选择 **"图表"数据或\*\*\*\*"表"。**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9cbe1-252">在出现的对话框中，保存 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="9cbe1-253">撤消用户提交</span><span class="sxs-lookup"><span data-stu-id="9cbe1-253">Undo user submissions</span></span>

<span data-ttu-id="9cbe1-254">用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法撤消提交。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="9cbe1-255">如果用户希望恢复电子邮件，可以在"已删除邮件"或"垃圾邮件"文件夹中进行恢复。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="9cbe1-256">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="9cbe1-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="9cbe1-257">如果已配置自定义邮箱以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="9cbe1-258">这有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="9cbe1-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="9cbe1-259">在 **"自定义邮箱**"选项卡上，在列表中选择一封邮件，单击"操作"按钮，然后进行以下选择之一：</span><span class="sxs-lookup"><span data-stu-id="9cbe1-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="9cbe1-260">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-260">**Report clean**</span></span>
- <span data-ttu-id="9cbe1-261">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-261">**Report phishing**</span></span>
- <span data-ttu-id="9cbe1-262">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-262">**Report malware**</span></span>
- <span data-ttu-id="9cbe1-263">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="9cbe1-263">**Report spam**</span></span>

![操作按钮上的选项](../../media/user-submission-custom-mailbox-action-button.png)
