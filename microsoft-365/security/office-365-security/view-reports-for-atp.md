---
title: 查看高级威胁防护报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 在安全合规中心中查找和使用适用于 Office 365 高级威胁防护的报告 &amp; 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc68df40e6b7b576644be607697d7b1ed0a33660
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653529"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="60871-103">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="60871-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="60871-104">Office 365 高级威胁防护 (ATP) 组织 (例如，Microsoft 365 E5 订阅或 ATP Plan 1 或 ATP Plan 2 加载项) 包含各种与安全相关的报告。</span><span class="sxs-lookup"><span data-stu-id="60871-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="60871-105">如果您具有[必要的权限](#what-permissions-are-needed-to-view-the-atp-reports)，则可以转到 "**报告**" \> **仪表板**，在安全 & 合规中心中查看这些报告。</span><span class="sxs-lookup"><span data-stu-id="60871-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="60871-106">若要直接转到 "报表" 仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="60871-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全 & 合规中心中的 "报告" 仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="60871-108">高级威胁防护文件类型报告</span><span class="sxs-lookup"><span data-stu-id="60871-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="60871-109">**高级威胁防护文件类型报告**报告显示通过[ATP 安全附件](atp-safe-attachments.md)检测为恶意的文件类型。</span><span class="sxs-lookup"><span data-stu-id="60871-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="60871-110">报告的聚合视图允许在筛选过程中90天，而详细信息视图仅允许10天的筛选。</span><span class="sxs-lookup"><span data-stu-id="60871-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="60871-111">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 " **Office ATP 文件类型**"。</span><span class="sxs-lookup"><span data-stu-id="60871-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="60871-112">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="60871-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

!["报表" 仪表板中的 Office ATP 文件类型小组件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="60871-114">[高级威胁防护邮件处置报告](#advanced-threat-protection-message-disposition-report)中也提供了此报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="60871-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="60871-115">高级威胁防护文件类型报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="60871-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="60871-116">可以使用以下视图：</span><span class="sxs-lookup"><span data-stu-id="60871-116">The following views are available:</span></span>

- <span data-ttu-id="60871-117">**数据查看依据：文件**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="60871-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="60871-118">**恶意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="60871-119">**恶意 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="60871-120">**恶意 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="60871-121">**恶意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="60871-122">**恶意 Url**</span><span class="sxs-lookup"><span data-stu-id="60871-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="60871-123">**恶意 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="60871-124">**恶意可执行附件**</span><span class="sxs-lookup"><span data-stu-id="60871-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="60871-125">**其他**</span><span class="sxs-lookup"><span data-stu-id="60871-125">**Others**</span></span>

  <span data-ttu-id="60871-126">当您将鼠标悬停在特定日期 (数据点) 时，您可以通过 EOP 中的[ATP 安全附件](atp-safe-attachments.md)和[反恶意软件保护](anti-malware-protection.md)来查看检测到的恶意文件类型的细目。</span><span class="sxs-lookup"><span data-stu-id="60871-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="60871-128">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-129">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-130">图表中显示的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="60871-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="60871-131">**数据查看依据：消息**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="60871-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="60871-132">**阻止访问**</span><span class="sxs-lookup"><span data-stu-id="60871-132">**Block access**</span></span>
  - <span data-ttu-id="60871-133">**邮件已替换**</span><span class="sxs-lookup"><span data-stu-id="60871-133">**Messages replaced**</span></span>
  - <span data-ttu-id="60871-134">**监视的邮件**</span><span class="sxs-lookup"><span data-stu-id="60871-134">**Messages monitored**</span></span>
  - <span data-ttu-id="60871-135">**替换为动态电子邮件传递**：有关详细信息，请参阅[使用 ATP 安全附件进行动态传递和预览](dynamic-delivery-and-previewing.md)。</span><span class="sxs-lookup"><span data-stu-id="60871-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![ATP 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="60871-137">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-138">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-139">图表中可用的相同邮件处置值，以及传递的其他**邮件**值。</span><span class="sxs-lookup"><span data-stu-id="60871-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="60871-140">高级威胁防护文件类型报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="60871-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="60871-141">如果单击 "**查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。</span><span class="sxs-lookup"><span data-stu-id="60871-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="60871-142">显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="60871-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="60871-143">**数据查看依据：文件**：</span><span class="sxs-lookup"><span data-stu-id="60871-143">**View data by: File**:</span></span>

  - <span data-ttu-id="60871-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="60871-144">**Date**</span></span>
  - <span data-ttu-id="60871-145">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-145">**Recipient address**</span></span>
  - <span data-ttu-id="60871-146">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-146">**Sender address**</span></span>
  - <span data-ttu-id="60871-147">**邮件 id**：在邮件头的**邮件 id**标头字段中可用，并且应是唯一的。</span><span class="sxs-lookup"><span data-stu-id="60871-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="60871-148"> (的示例值 `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 记下尖括号) 。</span><span class="sxs-lookup"><span data-stu-id="60871-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="60871-149">**File**</span><span class="sxs-lookup"><span data-stu-id="60871-149">**File**</span></span>

  <span data-ttu-id="60871-150">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-151">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-152">图表中显示的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="60871-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="60871-153">**数据查看依据：消息**：</span><span class="sxs-lookup"><span data-stu-id="60871-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="60871-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="60871-154">**Date**</span></span>
  - <span data-ttu-id="60871-155">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-155">**Recipient address**</span></span>
  - <span data-ttu-id="60871-156">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-156">**Sender address**</span></span>
  - <span data-ttu-id="60871-157">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="60871-157">**Message ID**</span></span>
  - <span data-ttu-id="60871-158">**File**</span><span class="sxs-lookup"><span data-stu-id="60871-158">**File**</span></span>
  - <span data-ttu-id="60871-159">**主题**</span><span class="sxs-lookup"><span data-stu-id="60871-159">**Subject**</span></span>

  <span data-ttu-id="60871-160">如果单击 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="60871-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="60871-161">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-162">图表中可用的相同邮件处置值，以及传递的其他**邮件**值。</span><span class="sxs-lookup"><span data-stu-id="60871-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="60871-163">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="60871-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="60871-164">高级威胁防护邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="60871-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="60871-165">**ATP 邮件处置**报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="60871-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="60871-166">若要查看报告，请打开 "[安全 & 合规中心](https://protection.office.com)"，转到 "**报告**" \> **仪表板**，然后选择 " **Office ATP 邮件处置**"。</span><span class="sxs-lookup"><span data-stu-id="60871-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="60871-167">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="60871-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

!["报告" 仪表板中的 Office 365 ATP 邮件处置小部件](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="60871-169">[高级威胁防护文件类型报告](#advanced-threat-protection-file-types-report)中也提供了此报告中的信息。</span><span class="sxs-lookup"><span data-stu-id="60871-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="60871-170">高级威胁防护邮件处置报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="60871-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="60871-171">可以使用以下视图：</span><span class="sxs-lookup"><span data-stu-id="60871-171">The following views are available:</span></span>

- <span data-ttu-id="60871-172">**数据查看依据：消息**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="60871-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="60871-173">**阻止访问**</span><span class="sxs-lookup"><span data-stu-id="60871-173">**Block access**</span></span>
  - <span data-ttu-id="60871-174">**邮件已替换**</span><span class="sxs-lookup"><span data-stu-id="60871-174">**Messages replaced**</span></span>
  - <span data-ttu-id="60871-175">**监视的邮件**</span><span class="sxs-lookup"><span data-stu-id="60871-175">**Messages monitored**</span></span>
  - <span data-ttu-id="60871-176">**替换为动态电子邮件传递**：有关详细信息，请参阅[使用 ATP 安全附件进行动态传递和预览](dynamic-delivery-and-previewing.md)。</span><span class="sxs-lookup"><span data-stu-id="60871-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![ATP 文件类型报告中的邮件视图](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="60871-178">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-179">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-180">图表中可用的相同邮件处置值，以及传递的其他**邮件**值。</span><span class="sxs-lookup"><span data-stu-id="60871-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="60871-181">**数据查看依据：文件**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="60871-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="60871-182">**恶意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="60871-183">**恶意 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="60871-184">**恶意 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="60871-185">**恶意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="60871-186">**恶意 Url**</span><span class="sxs-lookup"><span data-stu-id="60871-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="60871-187">**恶意 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="60871-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="60871-188">**恶意可执行附件**</span><span class="sxs-lookup"><span data-stu-id="60871-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="60871-189">**其他**</span><span class="sxs-lookup"><span data-stu-id="60871-189">**Others**</span></span>

  <span data-ttu-id="60871-190">当您将鼠标悬停在特定日期 (数据点) 时，您可以通过 EOP 中的[ATP 安全附件](atp-safe-attachments.md)和[反恶意软件保护](anti-malware-protection.md)来查看检测到的恶意文件类型的细目。</span><span class="sxs-lookup"><span data-stu-id="60871-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="60871-192">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-193">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-194">图表中显示的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="60871-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="60871-195">高级威胁防护邮件处置报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="60871-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="60871-196">如果单击 "**查看详细信息表**"，则报告将提供最近10天内组织内发生的所有点击的近实时视图。</span><span class="sxs-lookup"><span data-stu-id="60871-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="60871-197">显示的信息取决于您所查看的图表：</span><span class="sxs-lookup"><span data-stu-id="60871-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="60871-198">**数据查看依据：消息**：</span><span class="sxs-lookup"><span data-stu-id="60871-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="60871-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="60871-199">**Date**</span></span>
  - <span data-ttu-id="60871-200">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-200">**Recipient address**</span></span>
  - <span data-ttu-id="60871-201">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-201">**Sender address**</span></span>
  - <span data-ttu-id="60871-202">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="60871-202">**Message ID**</span></span>
  - <span data-ttu-id="60871-203">**File**</span><span class="sxs-lookup"><span data-stu-id="60871-203">**File**</span></span>
  - <span data-ttu-id="60871-204">**主题**</span><span class="sxs-lookup"><span data-stu-id="60871-204">**Subject**</span></span>

  <span data-ttu-id="60871-205">如果单击 "**筛选器**"，则可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="60871-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="60871-206">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-207">图表中可用的相同邮件处置值，以及传递的其他**邮件**值。</span><span class="sxs-lookup"><span data-stu-id="60871-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="60871-208">**数据查看依据：文件**：</span><span class="sxs-lookup"><span data-stu-id="60871-208">**View data by: File**:</span></span>

  - <span data-ttu-id="60871-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="60871-209">**Date**</span></span>
  - <span data-ttu-id="60871-210">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-210">**Recipient address**</span></span>
  - <span data-ttu-id="60871-211">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="60871-211">**Sender address**</span></span>
  - <span data-ttu-id="60871-212">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="60871-212">**Message ID**</span></span>
  - <span data-ttu-id="60871-213">**File**</span><span class="sxs-lookup"><span data-stu-id="60871-213">**File**</span></span>

  <span data-ttu-id="60871-214">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-215">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-216">图表中显示的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="60871-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="60871-217">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="60871-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="60871-218">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="60871-218">Threat protection status report</span></span>

<span data-ttu-id="60871-219">**威胁防护状态**报告是一个单一视图，它将有关检测到的恶意内容和恶意电子邮件的信息，以及[Exchange ONLINE protection](exchange-online-protection-overview.md) (EOP) 和 Office 365 ATP 进行了阻止。</span><span class="sxs-lookup"><span data-stu-id="60871-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="60871-220">有关详细信息，请参阅[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="60871-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="60871-221">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="60871-221">URL threat protection report</span></span>

<span data-ttu-id="60871-222">**Url 威胁防护报告**提供了检测到的威胁的汇总和趋势视图，以及对 URL 单击执行的操作作为[ATP 安全链接](atp-safe-links.md)的一部分。</span><span class="sxs-lookup"><span data-stu-id="60871-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="60871-223">此报告将不会从用户处单击 "数据"，即应用了 "安全链接策略" 的用户已选中 "不**跟踪用户点击**" 选项。</span><span class="sxs-lookup"><span data-stu-id="60871-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="60871-224">若要查看报告，请打开[安全性 & 合规性中心](https://protection.office.com)，转到 "**报告**" \> **仪表板**，然后选择 " **URL 保护报告**"。</span><span class="sxs-lookup"><span data-stu-id="60871-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="60871-225">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="60871-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

!["报告" 仪表板中的 URL 保护报告小部件](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="60871-227">这是一个 "*保护趋势" 报告*，即数据表示较大数据集中的趋势。</span><span class="sxs-lookup"><span data-stu-id="60871-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="60871-228">因此，在这里，聚合视图中的数据不是实时提供的，但详细信息表视图中的数据是，因此在这两种视图之间可能会出现细微差异。</span><span class="sxs-lookup"><span data-stu-id="60871-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="60871-229">URL 威胁防护报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="60871-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="60871-230">**URL 威胁防护**报告包含两个聚合视图，每四个小时刷新一次，显示最近90天的数据：</span><span class="sxs-lookup"><span data-stu-id="60871-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="60871-231">**URL 单击 "保护操作**"：显示组织中的用户单击的 url 的数量以及单击的结果：</span><span class="sxs-lookup"><span data-stu-id="60871-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="60871-232">**阻止 (阻止**用户导航到 URL) </span><span class="sxs-lookup"><span data-stu-id="60871-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="60871-233">**阻止并单击**</span><span class="sxs-lookup"><span data-stu-id="60871-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="60871-234">**在扫描过程中单击**</span><span class="sxs-lookup"><span data-stu-id="60871-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="60871-235">单击指示用户已通过阻止页面单击了恶意网站， (管理员可以禁用 "安全链接策略") 中的 "单击"。</span><span class="sxs-lookup"><span data-stu-id="60871-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="60871-236">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-237">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-238">可用的单击保护操作加上 (**允许**用户导航到 URL) 的值。</span><span class="sxs-lookup"><span data-stu-id="60871-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL 单击 URL 威胁防护报告中的 "保护操作" 视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="60871-240">**URL 单击应用程序**：显示支持 OFFICE 365 ATP 安全链接的应用程序的 url 单击次数：</span><span class="sxs-lookup"><span data-stu-id="60871-240">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="60871-241">**电子邮件客户端**</span><span class="sxs-lookup"><span data-stu-id="60871-241">**Email client**</span></span>
  - <span data-ttu-id="60871-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="60871-242">**PowerPoint**</span></span>
  - <span data-ttu-id="60871-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="60871-243">**Word**</span></span>
  - <span data-ttu-id="60871-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="60871-244">**Excel**</span></span>
  - <span data-ttu-id="60871-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="60871-245">**OneNote**</span></span>
  - <span data-ttu-id="60871-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="60871-246">**Visio**</span></span>
  - <span data-ttu-id="60871-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="60871-247">**Teams**</span></span>
  - <span data-ttu-id="60871-248">**其他**</span><span class="sxs-lookup"><span data-stu-id="60871-248">**Other**</span></span>

  <span data-ttu-id="60871-249">如果单击 "**筛选器**"，则可以使用以下筛选器修改报表：</span><span class="sxs-lookup"><span data-stu-id="60871-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="60871-250">**开始日期**和**结束日期**</span><span class="sxs-lookup"><span data-stu-id="60871-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="60871-251">可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="60871-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="60871-252">URL 威胁防护报告的详细信息表格视图</span><span class="sxs-lookup"><span data-stu-id="60871-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="60871-253">如果单击 "**查看详细信息表**"，则报告将提供最近7天内在组织内发生的所有点击的近实时视图，并提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="60871-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="60871-254">**单击 "时间"**</span><span class="sxs-lookup"><span data-stu-id="60871-254">**Click time**</span></span>
- <span data-ttu-id="60871-255">**用户**</span><span class="sxs-lookup"><span data-stu-id="60871-255">**User**</span></span>
- <span data-ttu-id="60871-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="60871-256">**URL**</span></span>
- <span data-ttu-id="60871-257">**操作**</span><span class="sxs-lookup"><span data-stu-id="60871-257">**Action**</span></span>
- <span data-ttu-id="60871-258">**App**</span><span class="sxs-lookup"><span data-stu-id="60871-258">**App**</span></span>

<span data-ttu-id="60871-259">如果单击 "详细信息表" 视图中的 "**筛选器**"，则可以按与报表视图中相同的条件进行筛选，也可以按逗号分隔的**域**或**收件人**进行筛选。</span><span class="sxs-lookup"><span data-stu-id="60871-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="60871-260">若要返回到 "报告" 视图，请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="60871-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="60871-261">要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="60871-261">Additional reports to view</span></span>

<span data-ttu-id="60871-262">除了本主题中所述的 ATP 报告之外，还有几个其他报告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="60871-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="60871-263">报告</span><span class="sxs-lookup"><span data-stu-id="60871-263">Report</span></span>|<span data-ttu-id="60871-264">主题</span><span class="sxs-lookup"><span data-stu-id="60871-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="60871-265">**资源管理器** (atp plan 2) 或 (ATP plan 1) 的**实时检测**</span><span class="sxs-lookup"><span data-stu-id="60871-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="60871-266">威胁资源管理器（和实时检测）</span><span class="sxs-lookup"><span data-stu-id="60871-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="60871-267">**电子邮件安全报告**，如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="60871-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="60871-268">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="60871-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="60871-269">**邮件流报告**，例如转发报告、邮件流状态报告和主要发件人和收件人报告。</span><span class="sxs-lookup"><span data-stu-id="60871-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="60871-270">查看安全 & 合规性中心中的邮件流报告</span><span class="sxs-lookup"><span data-stu-id="60871-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="60871-271">**ATP 安全链接的 URL 跟踪**仅 (PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="60871-271">**URL trace for ATP Safe Links** (PowerShell only).</span></span> <span data-ttu-id="60871-272">此 cmdlet 的输出显示在过去七天内 ATP 安全链接操作的结果。</span><span class="sxs-lookup"><span data-stu-id="60871-272">The output of this cmdlet shows you the results of ATP Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="60871-273">UrlTrace</span><span class="sxs-lookup"><span data-stu-id="60871-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="60871-274">仅) **的 EOP 和 ATP (PowerShell 的邮件流量结果**。</span><span class="sxs-lookup"><span data-stu-id="60871-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="60871-275">此 cmdlet 的输出包含有关域、日期、事件类型、方向、操作和邮件计数的信息。</span><span class="sxs-lookup"><span data-stu-id="60871-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="60871-276">MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="60871-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="60871-277">仅 (PowerShell) 中**的 EOP 和 ATP 检测的邮件详细信息报告**。</span><span class="sxs-lookup"><span data-stu-id="60871-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="60871-278">此 cmdlet 的输出包含有关恶意文件或 Url、网络钓鱼企图、模拟以及电子邮件或文件中的其他潜在威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60871-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="60871-279">MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="60871-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="60871-280">查看 ATP 报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="60871-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="60871-281">为了查看和使用本主题中所述的报告，**必须为安全 &amp; 合规中心和 Exchange 管理中心分配适当的角色**。</span><span class="sxs-lookup"><span data-stu-id="60871-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="60871-282">对于 "安全 & 合规中心"，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="60871-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="60871-283">组织管理</span><span class="sxs-lookup"><span data-stu-id="60871-283">Organization Management</span></span>
  - <span data-ttu-id="60871-284">安全管理员 (可以在 Azure Active Directory 管理中心 (中分配此项 [https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3</span><span class="sxs-lookup"><span data-stu-id="60871-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="60871-285"> (可以在 Azure Active Directory 管理中心中分配安全操作员 ([https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3</span><span class="sxs-lookup"><span data-stu-id="60871-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="60871-286">安全读取者</span><span class="sxs-lookup"><span data-stu-id="60871-286">Security Reader</span></span>

- <span data-ttu-id="60871-287">对于 Exchange Online，必须在 Exchange 管理中心 () 或 PowerShell cmdlet 中分配以下角色之一 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) ：</span><span class="sxs-lookup"><span data-stu-id="60871-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="60871-288">组织管理</span><span class="sxs-lookup"><span data-stu-id="60871-288">Organization Management</span></span>
  - <span data-ttu-id="60871-289">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="60871-289">View-only Organization Management</span></span>
  - <span data-ttu-id="60871-290">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="60871-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="60871-291">合规性管理</span><span class="sxs-lookup"><span data-stu-id="60871-291">Compliance Management</span></span>

<span data-ttu-id="60871-292">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="60871-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="60871-293">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="60871-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="60871-294">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="60871-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="60871-295">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="60871-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="60871-296">如果您未在 ATP 报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="60871-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="60871-297">您的组织必须定义[Atp 安全链接策略](set-up-atp-safe-links-policies.md)和[atp 安全附件策略](set-up-atp-safe-attachments-policies.md)，以便将 ATP 保护设置到位。</span><span class="sxs-lookup"><span data-stu-id="60871-297">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="60871-298">另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="60871-298">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="60871-299">相关主题</span><span class="sxs-lookup"><span data-stu-id="60871-299">Related topics</span></span>

[<span data-ttu-id="60871-300">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="60871-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="60871-301">Azure Active Directory (角色权限</span><span class="sxs-lookup"><span data-stu-id="60871-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
