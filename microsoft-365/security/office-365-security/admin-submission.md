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
description: 管理员可以了解如何使用 Microsoft 365 Defender 门户中的提交门户向 Microsoft 提交可疑电子邮件、可疑钓鱼邮件、垃圾邮件以及其他可能有害的邮件、URL 和电子邮件附件，以重新扫描。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b671ce5a44c7be61331a121b49e96658cf14bab1
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964797"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b9fcf-103">使用“管理员提交”将可疑的垃圾邮件、网络钓鱼诈骗、URL和文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9fcf-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b9fcf-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-104">**Applies to**</span></span>
- [<span data-ttu-id="b9fcf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b9fcf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b9fcf-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b9fcf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="b9fcf-107">在Microsoft 365邮箱Exchange Online，管理员可以使用 Microsoft 365 Defender 门户中的提交门户将电子邮件、URL 和附件提交到 Microsoft 进行扫描。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b9fcf-108">当你提交电子邮件时，你得到：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="b9fcf-109">**电子邮件身份验证检查**：有关电子邮件身份验证在传递时通过还是失败的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="b9fcf-110">**策略命中**：有关可能允许或阻止传入电子邮件进入租户的任何策略的信息，覆盖我们的服务筛选器裁定。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="b9fcf-111">**有效负载信誉/触发**：检查邮件中任何 URL 和附件。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="b9fcf-112">**成绩分析**：由人工评分人员完成审阅，以确认邮件是否是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9fcf-113">负载信誉/触发和成绩分析并非在所有租户中都完成。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="b9fcf-114">当数据出于合规性目的不应离开租户边界时，将阻止信息进入组织外部。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="b9fcf-115">有关向 Microsoft 提交电子邮件、URL 和附件的其他方法，请参阅向 Microsoft 报告 [邮件和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9fcf-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b9fcf-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b9fcf-117">访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="b9fcf-118">若要直接转到 **提交页面，** 请使用 <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="b9fcf-119">若要向 Microsoft 提交邮件和文件，你需要是以下角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="b9fcf-120">**组织管理** 或 **安全读者** Microsoft 365 Defender [门户](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="b9fcf-121">**组织管理** 中的 [Exchange Online。](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="b9fcf-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="b9fcf-122">请注意，查看自定义邮箱的用户提交需要此角色组的 [成员身份，如](#view-user-submissions-to-microsoft) 本文稍后所述。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="b9fcf-123">有关用户如何向 Microsoft 提交邮件和文件的信息，请参阅向 Microsoft 报告邮件 [和文件](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="b9fcf-124">向 Microsoft 报告可疑内容</span><span class="sxs-lookup"><span data-stu-id="b9fcf-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="b9fcf-125">在 Microsoft 365 Defender 门户中，转到"电子邮件 **&协作** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="b9fcf-126">在"**提交"** 页上，验证"**已提交进行分析**"选项卡已选中，然后单击广告图标"提交到 ![ Microsoft ](../../media/m365-cc-sc-create-icon.png) **进行分析"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="b9fcf-127">使用 **"提交到 Microsoft 查看** "飞出页面来提交邮件、URL 或电子邮件附件，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b9fcf-128">向 Microsoft 提交有问题的电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9fcf-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="b9fcf-129">在 **"选择提交类型"** 框中，确认 **"电子邮件** "在下拉列表中已选中。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="b9fcf-130">在 **"添加网络邮件 ID 或上载电子邮件文件** "部分，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="b9fcf-131">添加电子邮件网络邮件 **ID：** 这是一个 GUID 值，可在邮件的 **X-MS-Exchange-Organization-Network-Message-Id** 标头中或在隔离邮件的 **X-MS-Office365-Filtering-Correlation-Id** 头中提供。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="b9fcf-132">**Upload电子邮件文件 (.msg 或 .eml) ：单击"浏览\*\*\*\*文件"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="b9fcf-133">在打开的对话框中，查找并选择 .eml 或 .msg 文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9fcf-134">针对客户，针对 Defender 提交 30 天的邮件Office 365暂时暂停。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="b9fcf-135">管理员只能返回 7 天。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="b9fcf-136">在 **"选择具有问题的** 收件人"框中，指定要针对其运行策略检查的收件人。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="b9fcf-137">策略检查将确定电子邮件是否由于用户或组织策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="b9fcf-138">在 **"选择提交** 到 Microsoft 的原因"部分中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="b9fcf-139">**不应阻止误报 (误报)**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="b9fcf-140">**应已被** 阻止：在"电子邮件应已分类为出现的部分"中，选择以下值之一 (如果你不确定，请使用最佳判断) ：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="b9fcf-141">**网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-141">**Phish**</span></span>
     - <span data-ttu-id="b9fcf-142">**垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-142">**Spam**</span></span>
     - <span data-ttu-id="b9fcf-143">**恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-143">**Malware**</span></span>

5. <span data-ttu-id="b9fcf-144">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-144">When you're finished, click the **Submit** button.</span></span>

   ![新 URL 提交示例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b9fcf-146">向 Microsoft 发送可疑 URL</span><span class="sxs-lookup"><span data-stu-id="b9fcf-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="b9fcf-147">在"**选择提交类型"框中**，从下拉列表中选择 **"URL"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="b9fcf-148">在出现的 **"URL"** 框中，输入完整的 URL (例如 `https://www.fabrikam.com/marketing.html` ，) 。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="b9fcf-149">在 **"选择提交** 到 Microsoft 的原因"部分中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="b9fcf-150">**不应阻止误报 (误报)**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="b9fcf-151">**应已被阻止**：在"此 **URL 应** 已分类为出现的部分"中，选择"**钓鱼"** 或"恶意软件 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="b9fcf-152">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-152">When you're finished, click the **Submit** button.</span></span>

   ![新电子邮件提交示例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="b9fcf-154">将可疑的电子邮件附件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9fcf-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="b9fcf-155">在"**选择提交类型"框中\*\*\*\*，从下拉列表** 中选择"文件"。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="b9fcf-156">在出现的 **"文件**"部分，单击"**浏览文件"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="b9fcf-157">在打开的对话框中，查找并选择文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="b9fcf-158">在 **"选择提交** 到 Microsoft 的原因"部分中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="b9fcf-159">**不应阻止误报 (误报)**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="b9fcf-160">**应已被阻止**：在"此 **URL 应** 已分类为出现的部分"中，" **恶意软件"是唯** 一的选择，并自动选中。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="b9fcf-161">完成后，单击"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-161">When you're finished, click the **Submit** button.</span></span>

   ![新附件提交示例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="b9fcf-163">查看向 Microsoft 提交的管理员</span><span class="sxs-lookup"><span data-stu-id="b9fcf-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="b9fcf-164">在 Microsoft 365 Defender 门户中，转到"电子邮件 **&协作** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="b9fcf-165">在 **"提交"** 页上，确认已选中" **已提交进行分析"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="b9fcf-166">可以通过单击可用列标题来对条目进行排序。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="b9fcf-167">单击 **"自定义列** "最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="b9fcf-168">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="b9fcf-169">**提交名称**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-170">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-171">**提交日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-172">**提交类型**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-173">**提交原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-174">**重新扫描状态**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-175">**重新扫描结果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-176">**筛选裁定**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-176">**Filter verdict**</span></span>
     - <span data-ttu-id="b9fcf-177">**传递/阻止原因**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="b9fcf-178">**提交 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-178">**Submission ID**</span></span>
     - <span data-ttu-id="b9fcf-179">**网络消息 ID/对象 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="b9fcf-180">**方向**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-180">**Direction**</span></span>
     - <span data-ttu-id="b9fcf-181">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-181">**Sender IP**</span></span>
     - <span data-ttu-id="b9fcf-182">**BCL (批量)**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="b9fcf-183">**目标**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-183">**Destination**</span></span>
     - <span data-ttu-id="b9fcf-184">**策略操作**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-184">**Policy action**</span></span>
     - <span data-ttu-id="b9fcf-185">**提交者**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-185">**Submitted by**</span></span>

     <span data-ttu-id="b9fcf-186">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="b9fcf-187">若要筛选条目，请单击"筛选器 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="b9fcf-188">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-188">The available filters are:</span></span>
     - <span data-ttu-id="b9fcf-189">**提交日期**：**开始日期和\*\*\*\*结束日期**。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="b9fcf-190">**提交类型\*\*\*\*：Email、URL** 或 **File**。 </span><span class="sxs-lookup"><span data-stu-id="b9fcf-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="b9fcf-191">**提交 ID：** 分配给每个提交的 GUID 值。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="b9fcf-192">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-192">**Network Message ID**</span></span>
     - <span data-ttu-id="b9fcf-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-193">**Sender**</span></span>

     <span data-ttu-id="b9fcf-194">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-194">When you're finished, click **Apply**.</span></span>

     ![管理员提交的新筛选器选项](../../media/admin-submission-email-filter-options.png)

   - <span data-ttu-id="b9fcf-196">若要对条目进行分组，请单击 **"分组** "，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="b9fcf-197">**无**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-197">**None**</span></span>
     - <span data-ttu-id="b9fcf-198">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-198">**Type**</span></span>
     - <span data-ttu-id="b9fcf-199">**原因**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-199">**Reason**</span></span>
     - <span data-ttu-id="b9fcf-200">**状态**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-200">**Status**</span></span>
     - <span data-ttu-id="b9fcf-201">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-201">**Rescan result**</span></span>

   - <span data-ttu-id="b9fcf-202">若要导出条目，请单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="b9fcf-203">在出现的对话框中，保存.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="b9fcf-204">管理员提交重新扫描详细信息</span><span class="sxs-lookup"><span data-stu-id="b9fcf-204">Admin submission rescan details</span></span>

<span data-ttu-id="b9fcf-205">在管理员提交中提交的邮件会重新扫描，并且结果显示在提交详细信息飞出中：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-205">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="b9fcf-206">发件人的电子邮件身份验证是否在发送时验证失败。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="b9fcf-207">任何可能影响或覆盖邮件裁定的策略信息。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="b9fcf-208">当前触发结果，以查看邮件中所包含的 URL 或文件是否是恶意的。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="b9fcf-209">来自成绩者的反馈。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-209">Feedback from graders.</span></span>

<span data-ttu-id="b9fcf-210">如果找到了覆盖，则应该会在数分钟内完成重新扫描。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="b9fcf-211">如果电子邮件身份验证没有问题，或者传递不受替代的影响，则来自成绩认证人员的反馈可能需要一天的时间。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="b9fcf-212">查看向 Microsoft 提交用户</span><span class="sxs-lookup"><span data-stu-id="b9fcf-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="b9fcf-213">如果已部署报告邮件外接程序、[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序或用户使用[Outlook 网页版](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中的内置报告，您可以在"用户报告的邮件"选项卡上看到报告的用户。 [](enable-the-report-phish-add-in.md) </span><span class="sxs-lookup"><span data-stu-id="b9fcf-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="b9fcf-214">在 Microsoft 365 Defender 门户中，转到"电子邮件 **&协作** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="b9fcf-215">在" **提交"** 页上，选择" **用户报告的邮件"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="b9fcf-216">可以通过单击可用列标题来对条目进行排序。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="b9fcf-217">单击 **"自定义列** "最多可显示七列。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="b9fcf-218">默认值标有星号 (<sup>\*</sup>)：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="b9fcf-219">**电子邮件主题**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-220">**报告者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-221">**报告的日期**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-222">**发件人**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-223">**报告的原因**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-224">**重新扫描结果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b9fcf-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="b9fcf-225">**邮件报告 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-225">**Message reported ID**</span></span>
     - <span data-ttu-id="b9fcf-226">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-226">**Network Message ID**</span></span>
     - <span data-ttu-id="b9fcf-227">**发件人 IP**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-227">**Sender IP**</span></span>
     - <span data-ttu-id="b9fcf-228">**网络钓鱼模拟**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-228">**Phish simulation**</span></span>

     <span data-ttu-id="b9fcf-229">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="b9fcf-230">若要筛选条目，请单击"筛选器 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="b9fcf-231">以下筛选器可用：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-231">The available filters are:</span></span>
     - <span data-ttu-id="b9fcf-232">**报告的日期\*\*\*\*：开始日期和\*\*\*\*结束日期**。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="b9fcf-233">**报告者**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-233">**Reported by**</span></span>
     - <span data-ttu-id="b9fcf-234">**电子邮件主题**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-234">**Email subject**</span></span>
     - <span data-ttu-id="b9fcf-235">**邮件报告 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-235">**Message reported ID**</span></span>
     - <span data-ttu-id="b9fcf-236">**网络消息 ID**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-236">**Network Message ID**</span></span>
     - <span data-ttu-id="b9fcf-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-237">**Sender**</span></span>
     - <span data-ttu-id="b9fcf-238">**报告的原因**： **非垃圾邮件**、 **网络钓鱼** 或 **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="b9fcf-239">**网络钓鱼模拟**： **是** 或 **否**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="b9fcf-240">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-240">When you're finished, click **Apply**.</span></span>

    ![用户提交的新筛选器选项](../../media/user-submissions-filter-options.png)

   - <span data-ttu-id="b9fcf-242">若要对条目进行分组，请单击 **"分组** "，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="b9fcf-243">**无**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-243">**None**</span></span>
     - <span data-ttu-id="b9fcf-244">**原因**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-244">**Reason**</span></span>
     - <span data-ttu-id="b9fcf-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-245">**Sender**</span></span>
     - <span data-ttu-id="b9fcf-246">**报告者**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-246">**Reported by**</span></span>
     - <span data-ttu-id="b9fcf-247">**重新扫描结果**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-247">**Rescan result**</span></span>
     - <span data-ttu-id="b9fcf-248">**网络钓鱼模拟**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-248">**Phish simulation**</span></span>

   - <span data-ttu-id="b9fcf-249">若要导出条目，请单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="b9fcf-250">在出现的对话框中，保存.csv文件。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="b9fcf-251">如果组织配置为仅将用户报告的邮件发送到自定义邮箱，将不会发送报告的邮件进行重新扫描，并且 **"用户** 报告的邮件"中的结果将始终为空。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="b9fcf-252">撤消用户提交</span><span class="sxs-lookup"><span data-stu-id="b9fcf-252">Undo user submissions</span></span>

<span data-ttu-id="b9fcf-253">用户向自定义邮箱提交可疑电子邮件后，用户和管理员将无法撤消提交。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="b9fcf-254">如果用户希望恢复电子邮件，可以在"已删除邮件"或"垃圾邮件"文件夹中进行恢复。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="b9fcf-255">从自定义邮箱向 Microsoft 提交邮件</span><span class="sxs-lookup"><span data-stu-id="b9fcf-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="b9fcf-256">如果已配置自定义邮箱，以截获用户报告的邮件，而不将邮件发送到 Microsoft，您可以查找特定邮件并将其发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="b9fcf-257">这有效地将用户提交移动到管理员提交。</span><span class="sxs-lookup"><span data-stu-id="b9fcf-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="b9fcf-258">在" **用户报告的邮件** "选项卡上，选择列表中的邮件，单击"提交给 **Microsoft** 进行分析"，然后从下拉列表中选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b9fcf-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="b9fcf-259">**报告干净**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-259">**Report clean**</span></span>
- <span data-ttu-id="b9fcf-260">**报告网络钓鱼**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-260">**Report phishing**</span></span>
- <span data-ttu-id="b9fcf-261">**报告恶意软件**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-261">**Report malware**</span></span>
- <span data-ttu-id="b9fcf-262">**报告垃圾邮件**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-262">**Report spam**</span></span>
- <span data-ttu-id="b9fcf-263">**触发调查**</span><span class="sxs-lookup"><span data-stu-id="b9fcf-263">**Trigger investigation**</span></span>

!["操作"按钮上的"新建选项"](../../media/user-submission-custom-mailbox-action-button.png)
