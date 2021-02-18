---
title: 在"报告"仪表板中查看 Defender for Office 365 报告
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在安全与合规中心查找和使用 Microsoft Defender for Office 365 &报告。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e5d48f6ac8f6246b65761f5728405c37333d71
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286593"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="a21d1-103">在安全与合规中心的报告仪表板中查看 Defender for Office 365 &报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a21d1-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a21d1-104">**Applies to**</span></span>
- [<span data-ttu-id="a21d1-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a21d1-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a21d1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a21d1-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a21d1-107">Microsoft Defender for Office 365 组织 (例如，Microsoft 365 E5 订阅或 Microsoft Defender for Office 365 计划 1 或 Microsoft Defender for Office 365 计划 2 加载项) 包含各种与安全相关的报告。</span><span class="sxs-lookup"><span data-stu-id="a21d1-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="a21d1-108">如果您具有 [必要的权限](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)，可以通过访问报告仪表板&安全与合规中心 **查看** \> **这些报告**。</span><span class="sxs-lookup"><span data-stu-id="a21d1-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a21d1-109">若要直接转到报表仪表板，请打开 <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-109">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![安全与合规中心&仪表板](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="a21d1-111">Defender for Office 365 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="a21d1-112">Defender **for Office 365** 文件类型报告显示安全附件检测到的恶意 [文件类型](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="a21d1-113">报告的聚合视图允许筛选 90 天，而详细信息视图仅允许筛选 10 天。</span><span class="sxs-lookup"><span data-stu-id="a21d1-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="a21d1-114">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到"报告仪表板"，然后选择 \> 适用于 Office **365** 的 Defender 文件类型。</span><span class="sxs-lookup"><span data-stu-id="a21d1-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="a21d1-115">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![报告仪表板中的 Defender for Office 365 文件类型小组件](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="a21d1-117">此报告中的信息也可在 Defender for [Office 365 邮件处置报告中获取](#defender-for-office-365-message-disposition-report)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="a21d1-118">Defender for Office 365 文件类型报告的报表视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="a21d1-119">以下视图可用：</span><span class="sxs-lookup"><span data-stu-id="a21d1-119">The following views are available:</span></span>

- <span data-ttu-id="a21d1-120">**查看数据者：文件**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="a21d1-121">**恶意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="a21d1-122">**恶意 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="a21d1-123">**恶意 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="a21d1-124">**恶意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="a21d1-125">**恶意 URL**</span><span class="sxs-lookup"><span data-stu-id="a21d1-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="a21d1-126">**恶意 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="a21d1-127">**恶意可执行附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="a21d1-128">**其他**</span><span class="sxs-lookup"><span data-stu-id="a21d1-128">**Others**</span></span>

  <span data-ttu-id="a21d1-129">当您将鼠标悬停在 (数据点) 时，可以看到 EOP 中安全附件和反恶意软件保护检测到的恶意文件类型[的细目](anti-malware-protection.md)。 [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="a21d1-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="a21d1-131">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-132">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-133">图表中可见的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="a21d1-134">**查看数据者：消息**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="a21d1-135">**阻止访问**</span><span class="sxs-lookup"><span data-stu-id="a21d1-135">**Block access**</span></span>
  - <span data-ttu-id="a21d1-136">**已替换邮件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-136">**Messages replaced**</span></span>
  - <span data-ttu-id="a21d1-137">**监视的邮件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-137">**Messages monitored**</span></span>
  - <span data-ttu-id="a21d1-138">**替换为动态电子邮件传递**：有关详细信息，请参阅"安全附件 [策略中的动态传递"。](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="a21d1-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Defender for Office 365 文件类型报告中的消息视图](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="a21d1-140">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-141">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-142">图表中可用的相同邮件处置值，以及传递 **值的其他邮件** 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="a21d1-143">Defender for Office 365 文件类型报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="a21d1-144">如果单击 **"查看详细信息"表**，报告将提供最近 10 天内在组织中发生的所有单击的近实时视图。</span><span class="sxs-lookup"><span data-stu-id="a21d1-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="a21d1-145">显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="a21d1-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a21d1-146">**查看数据者：文件**：</span><span class="sxs-lookup"><span data-stu-id="a21d1-146">**View data by: File**:</span></span>

  - <span data-ttu-id="a21d1-147">"日期"</span><span class="sxs-lookup"><span data-stu-id="a21d1-147">**Date**</span></span>
  - <span data-ttu-id="a21d1-148">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-148">**Recipient address**</span></span>
  - <span data-ttu-id="a21d1-149">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-149">**Sender address**</span></span>
  - <span data-ttu-id="a21d1-150">**邮件 ID：** 在邮件 **头的 Message-ID** 头字段中可用，并且应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a21d1-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="a21d1-151">示例值是 (`<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 中括号) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="a21d1-152">**File**</span><span class="sxs-lookup"><span data-stu-id="a21d1-152">**File**</span></span>

  <span data-ttu-id="a21d1-153">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-154">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-155">图表中可见的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="a21d1-156">**查看数据者：消息**：</span><span class="sxs-lookup"><span data-stu-id="a21d1-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="a21d1-157">"日期"</span><span class="sxs-lookup"><span data-stu-id="a21d1-157">**Date**</span></span>
  - <span data-ttu-id="a21d1-158">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-158">**Recipient address**</span></span>
  - <span data-ttu-id="a21d1-159">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-159">**Sender address**</span></span>
  - <span data-ttu-id="a21d1-160">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="a21d1-160">**Message ID**</span></span>
  - <span data-ttu-id="a21d1-161">**File**</span><span class="sxs-lookup"><span data-stu-id="a21d1-161">**File**</span></span>
  - <span data-ttu-id="a21d1-162">**主题**</span><span class="sxs-lookup"><span data-stu-id="a21d1-162">**Subject**</span></span>

  <span data-ttu-id="a21d1-163">如果单击 **"筛选器**"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="a21d1-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="a21d1-164">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-165">图表中可用的相同邮件处置值，以及传递 **值的其他邮件** 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="a21d1-166">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="a21d1-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="a21d1-167">Defender for Office 365 邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="a21d1-168">**ATP 邮件处置** 报告将显示对检测到包含恶意内容的电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="a21d1-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="a21d1-169">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到报告 \> **仪表板** 并选择 Defender for Office **365 邮件处置**。</span><span class="sxs-lookup"><span data-stu-id="a21d1-169">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="a21d1-170">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![报告仪表板中的 Defender for Office 365 邮件处置小组件](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="a21d1-172">此报告中的信息也可在 Defender for [Office 365 文件类型报告中获取](#defender-for-office-365-file-types-report)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="a21d1-173">Defender for Office 365 邮件处置报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="a21d1-174">以下视图可用：</span><span class="sxs-lookup"><span data-stu-id="a21d1-174">The following views are available:</span></span>

- <span data-ttu-id="a21d1-175">**查看数据者：消息**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="a21d1-176">**阻止访问**</span><span class="sxs-lookup"><span data-stu-id="a21d1-176">**Block access**</span></span>
  - <span data-ttu-id="a21d1-177">**已替换邮件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-177">**Messages replaced**</span></span>
  - <span data-ttu-id="a21d1-178">**监视的邮件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-178">**Messages monitored**</span></span>
  - <span data-ttu-id="a21d1-179">**替换为动态电子邮件传递**：有关详细信息，请参阅"安全附件 [策略中的动态传递"。](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="a21d1-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Defender for Office 365 文件类型报告中的消息视图](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="a21d1-181">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-182">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-183">图表中可用的相同邮件处置值，以及传递 **值的其他邮件** 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="a21d1-184">**查看数据者：文件**：图表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="a21d1-185">**恶意 Excel 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="a21d1-186">**恶意 Flash 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="a21d1-187">**恶意 PDF 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="a21d1-188">**恶意 PowerPoint 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="a21d1-189">**恶意 URL**</span><span class="sxs-lookup"><span data-stu-id="a21d1-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="a21d1-190">**恶意 Word 附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="a21d1-191">**恶意可执行附件**</span><span class="sxs-lookup"><span data-stu-id="a21d1-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="a21d1-192">**其他**</span><span class="sxs-lookup"><span data-stu-id="a21d1-192">**Others**</span></span>

  <span data-ttu-id="a21d1-193">当您将鼠标悬停在 (数据点) 时，可以看到 EOP 中安全附件和反恶意软件保护检测到的恶意文件类型[的细目](anti-malware-protection.md)。 [](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="a21d1-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Defender for Office 365 文件类型报告中的文件视图](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="a21d1-195">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-196">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-197">图表中可见的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="a21d1-198">Defender for Office 365 邮件处置报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="a21d1-199">如果单击 **"查看详细信息"表**，报告将提供最近 10 天内在组织中发生的所有单击的近实时视图。</span><span class="sxs-lookup"><span data-stu-id="a21d1-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="a21d1-200">显示的信息取决于您正在查看的图表：</span><span class="sxs-lookup"><span data-stu-id="a21d1-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a21d1-201">**查看数据者：消息**：</span><span class="sxs-lookup"><span data-stu-id="a21d1-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="a21d1-202">"日期"</span><span class="sxs-lookup"><span data-stu-id="a21d1-202">**Date**</span></span>
  - <span data-ttu-id="a21d1-203">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-203">**Recipient address**</span></span>
  - <span data-ttu-id="a21d1-204">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-204">**Sender address**</span></span>
  - <span data-ttu-id="a21d1-205">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="a21d1-205">**Message ID**</span></span>
  - <span data-ttu-id="a21d1-206">**File**</span><span class="sxs-lookup"><span data-stu-id="a21d1-206">**File**</span></span>
  - <span data-ttu-id="a21d1-207">**主题**</span><span class="sxs-lookup"><span data-stu-id="a21d1-207">**Subject**</span></span>

  <span data-ttu-id="a21d1-208">如果单击 **"筛选器**"，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="a21d1-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="a21d1-209">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-210">图表中可用的相同邮件处置值，以及传递 **值的其他邮件** 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="a21d1-211">**查看数据者：文件**：</span><span class="sxs-lookup"><span data-stu-id="a21d1-211">**View data by: File**:</span></span>

  - <span data-ttu-id="a21d1-212">"日期"</span><span class="sxs-lookup"><span data-stu-id="a21d1-212">**Date**</span></span>
  - <span data-ttu-id="a21d1-213">**收件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-213">**Recipient address**</span></span>
  - <span data-ttu-id="a21d1-214">**发件人地址**</span><span class="sxs-lookup"><span data-stu-id="a21d1-214">**Sender address**</span></span>
  - <span data-ttu-id="a21d1-215">**邮件 ID**</span><span class="sxs-lookup"><span data-stu-id="a21d1-215">**Message ID**</span></span>
  - <span data-ttu-id="a21d1-216">**File**</span><span class="sxs-lookup"><span data-stu-id="a21d1-216">**File**</span></span>

  <span data-ttu-id="a21d1-217">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-218">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-219">图表中可见的相同文件类型值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="a21d1-220">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="a21d1-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="a21d1-221">邮件延迟报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-221">Mail latency report</span></span>

<span data-ttu-id="a21d1-222">邮件 **延迟报告** 显示组织中遇到的邮件传递和触发延迟的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="a21d1-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="a21d1-223">服务中的邮件传递时间受多种因素影响，绝对传递时间（以秒表示）通常不是成功或出现问题的良好指示器。</span><span class="sxs-lookup"><span data-stu-id="a21d1-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="a21d1-224">一天中较慢的送达时间可能被视为另一天的平均送达时间，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a21d1-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="a21d1-225">邮件 **延迟报告** 尝试根据有关其他邮件的观测送达时间的统计数据来限定邮件传递：</span><span class="sxs-lookup"><span data-stu-id="a21d1-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="a21d1-226">**第 50** 个百分点：这是邮件传递时间中间值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="a21d1-227">可以将此值视为平均送达时间。</span><span class="sxs-lookup"><span data-stu-id="a21d1-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="a21d1-228">**第 90** 个百分点：这表示邮件传递的延迟时间长。</span><span class="sxs-lookup"><span data-stu-id="a21d1-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="a21d1-229">只有 10% 的邮件传递时间超过此值。</span><span class="sxs-lookup"><span data-stu-id="a21d1-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="a21d1-230">**第 99** 个百分点：这表示邮件传递的延迟最大。</span><span class="sxs-lookup"><span data-stu-id="a21d1-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="a21d1-231">不包括客户端和网络延迟。</span><span class="sxs-lookup"><span data-stu-id="a21d1-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="a21d1-232">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，**转到"** 报告仪表板 \> "并选择 **"邮件延迟报告"。**</span><span class="sxs-lookup"><span data-stu-id="a21d1-232">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="a21d1-233">若要直接转到报表，请打开 <https://protection.office.com/mailLatencyReport?viewid=P50> 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-233">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

!["报告"仪表板中的"邮件延迟报告"小部件](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="a21d1-235">邮件延迟报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="a21d1-236">打开报表时，默认情况下会选择 **第 50** 个百分点选项卡。</span><span class="sxs-lookup"><span data-stu-id="a21d1-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="a21d1-237">默认情况下，此视图包含使用以下筛选器配置的图表：</span><span class="sxs-lookup"><span data-stu-id="a21d1-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="a21d1-238">**日期**：最近 7 天</span><span class="sxs-lookup"><span data-stu-id="a21d1-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="a21d1-239">**消息视图**：</span><span class="sxs-lookup"><span data-stu-id="a21d1-239">**Message View**:</span></span>
  - <span data-ttu-id="a21d1-240">触发的邮件</span><span class="sxs-lookup"><span data-stu-id="a21d1-240">Detonated messages</span></span>

<span data-ttu-id="a21d1-241">此图表显示按以下类别组织的消息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="a21d1-242">**邮件传递延迟**</span><span class="sxs-lookup"><span data-stu-id="a21d1-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="a21d1-243">**触发延迟**</span><span class="sxs-lookup"><span data-stu-id="a21d1-243">**Detonation latency**</span></span>

<span data-ttu-id="a21d1-244">将鼠标悬停在图表中的类别上时，可以看到每个类别中的延迟细分。</span><span class="sxs-lookup"><span data-stu-id="a21d1-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![邮件延迟报告](../../media/mail-latency-report.png)

<span data-ttu-id="a21d1-246">如果 **单击"** 筛选器"报表视图，可以使用以下筛选器修改结果：</span><span class="sxs-lookup"><span data-stu-id="a21d1-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a21d1-247">所有邮件</span><span class="sxs-lookup"><span data-stu-id="a21d1-247">All messages</span></span>
- <span data-ttu-id="a21d1-248">包含附件或 URL 的邮件</span><span class="sxs-lookup"><span data-stu-id="a21d1-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="a21d1-249">如果单击第 **90** 个百分点值选项卡或 **第 99** 个百分点选项卡，则使用第 **50** 个百分点视图中的相同默认筛选器。</span><span class="sxs-lookup"><span data-stu-id="a21d1-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="a21d1-250">邮件延迟报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="a21d1-251">详细信息表视图中显示了以下信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="a21d1-252">"日期"</span><span class="sxs-lookup"><span data-stu-id="a21d1-252">**Date**</span></span>
- <span data-ttu-id="a21d1-253">**百分点值**</span><span class="sxs-lookup"><span data-stu-id="a21d1-253">**Percentiles**</span></span>
- <span data-ttu-id="a21d1-254">**邮件计数**</span><span class="sxs-lookup"><span data-stu-id="a21d1-254">**Message count**</span></span>
- <span data-ttu-id="a21d1-255">**总体延迟**</span><span class="sxs-lookup"><span data-stu-id="a21d1-255">**Overall latency**</span></span>

![邮件延迟报告详细信息](../../media/mail-latency-report-details.png)

<span data-ttu-id="a21d1-257">以上显示，11 月 14 日，所有传递和触发的邮件的平均延迟为 **108.033** 秒。</span><span class="sxs-lookup"><span data-stu-id="a21d1-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="a21d1-258">详细信息表包含每个选项卡上的相同信息。</span><span class="sxs-lookup"><span data-stu-id="a21d1-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="a21d1-259">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-259">Threat protection status report</span></span>

<span data-ttu-id="a21d1-260">威胁 **防护状态** 报告是一个视图，它汇集 [了 Exchange Online Protection](exchange-online-protection-overview.md) (EOP) 和 Microsoft Defender for Office 365 检测并阻止的恶意内容和恶意电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="a21d1-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a21d1-261">有关详细信息，请参阅 [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="a21d1-262">URL 威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-262">URL threat protection report</span></span>

<span data-ttu-id="a21d1-263">URL **威胁防护报告** 提供检测到的威胁的摘要和趋势视图，以及作为安全链接的一部分对 URL 单击 [采取的操作](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="a21d1-264">此报告不会包含已选择"不跟踪用户单击"选项且应用了安全链接策略的用户 **的单击** 数据。</span><span class="sxs-lookup"><span data-stu-id="a21d1-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="a21d1-265">若要查看报告，请打开 [安全](https://protection.office.com)与合规&，转到 **报告** \> **仪表板** 并选择 **URL 保护报告**。</span><span class="sxs-lookup"><span data-stu-id="a21d1-265">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="a21d1-266">若要直接转到报表，请打开 <https://protection.office.com/reportv2?id=URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-266">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

!["报告"仪表板中的"URL 保护报告"小部件](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="a21d1-268">这是一 *个保护趋势报告*，表示数据表示较大数据集中的趋势。</span><span class="sxs-lookup"><span data-stu-id="a21d1-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="a21d1-269">因此，聚合视图中的数据在此处无法实时使用，但详细信息表视图中的数据是，因此您可能会看到这两个视图之间稍有差异。</span><span class="sxs-lookup"><span data-stu-id="a21d1-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="a21d1-270">URL 威胁防护报告的报告视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="a21d1-271">**URL 威胁防护** 报告有两个聚合视图，每四小时刷新一次，显示过去 90 天的数据：</span><span class="sxs-lookup"><span data-stu-id="a21d1-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="a21d1-272">**URL 单击保护操作**：显示组织中用户单击的 URL 数和单击结果：</span><span class="sxs-lookup"><span data-stu-id="a21d1-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="a21d1-273">**阻止** (用户导航到 URL) </span><span class="sxs-lookup"><span data-stu-id="a21d1-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="a21d1-274">**阻止并单击**</span><span class="sxs-lookup"><span data-stu-id="a21d1-274">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="a21d1-275">**在扫描过程中单击**</span><span class="sxs-lookup"><span data-stu-id="a21d1-275">**Clicked through during scan**</span></span>

  <span data-ttu-id="a21d1-276">单击表示用户已单击阻止页面到恶意网站 (在安全链接策略中禁用) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="a21d1-277">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-278">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-279">可用的单击保护操作，以及 (导航到URL 地址时允许) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL 威胁防护报告中的 URL 单击保护操作视图](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="a21d1-281">**按应用程序单击的 URL：** 显示支持安全链接的应用程序单击的 URL 数：</span><span class="sxs-lookup"><span data-stu-id="a21d1-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="a21d1-282">**电子邮件客户端**</span><span class="sxs-lookup"><span data-stu-id="a21d1-282">**Email client**</span></span>
  - <span data-ttu-id="a21d1-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="a21d1-283">**PowerPoint**</span></span>
  - <span data-ttu-id="a21d1-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="a21d1-284">**Word**</span></span>
  - <span data-ttu-id="a21d1-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="a21d1-285">**Excel**</span></span>
  - <span data-ttu-id="a21d1-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="a21d1-286">**OneNote**</span></span>
  - <span data-ttu-id="a21d1-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="a21d1-287">**Visio**</span></span>
  - <span data-ttu-id="a21d1-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="a21d1-288">**Teams**</span></span>
  - <span data-ttu-id="a21d1-289">**其他**</span><span class="sxs-lookup"><span data-stu-id="a21d1-289">**Other**</span></span>

  <span data-ttu-id="a21d1-290">如果单击 **"筛选器**"，可以使用以下筛选器修改报告：</span><span class="sxs-lookup"><span data-stu-id="a21d1-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="a21d1-291">**开始日期和\*\*\*\*结束日期**</span><span class="sxs-lookup"><span data-stu-id="a21d1-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="a21d1-292">可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a21d1-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="a21d1-293">URL 威胁防护报告的详细信息表视图</span><span class="sxs-lookup"><span data-stu-id="a21d1-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="a21d1-294">如果单击 **"查看详细信息"表**，报告将提供最近 7 天内在组织中发生的所有单击的近实时视图，并包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="a21d1-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="a21d1-295">**单击时间**</span><span class="sxs-lookup"><span data-stu-id="a21d1-295">**Click time**</span></span>
- <span data-ttu-id="a21d1-296">"用户"</span><span class="sxs-lookup"><span data-stu-id="a21d1-296">**User**</span></span>
- <span data-ttu-id="a21d1-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="a21d1-297">**URL**</span></span>
- <span data-ttu-id="a21d1-298">**操作**</span><span class="sxs-lookup"><span data-stu-id="a21d1-298">**Action**</span></span>
- <span data-ttu-id="a21d1-299">**App**</span><span class="sxs-lookup"><span data-stu-id="a21d1-299">**App**</span></span>

<span data-ttu-id="a21d1-300">如果 **单击详细信息** 表视图中的"筛选器"，可以按照与"收件人"报表视图相同的条件进行筛选，也可以按以逗号分隔的"域"或"收件人"进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a21d1-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="a21d1-301">域 **筛选器** 引用报告结果中列出的 URL 域。</span><span class="sxs-lookup"><span data-stu-id="a21d1-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="a21d1-302">若要返回到报告视图，请单击"**查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="a21d1-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="a21d1-303">要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-303">Additional reports to view</span></span>

<span data-ttu-id="a21d1-304">除了本文中所述的报告之外，还有其他一些报告可用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="a21d1-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="a21d1-305">报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-305">Report</span></span>|<span data-ttu-id="a21d1-306">主题</span><span class="sxs-lookup"><span data-stu-id="a21d1-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="a21d1-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) 或实时检测 **(** Microsoft Defender for Office 365 计划 1) </span><span class="sxs-lookup"><span data-stu-id="a21d1-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="a21d1-308">威胁资源管理器（和实时检测）</span><span class="sxs-lookup"><span data-stu-id="a21d1-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="a21d1-309">**电子邮件安全报告**，如顶级发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="a21d1-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="a21d1-310">查看安全与合规中心内的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-310">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="a21d1-311">**邮件流报告**，如转发报告、邮件流状态报告以及顶级发件人和收件人报告。</span><span class="sxs-lookup"><span data-stu-id="a21d1-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="a21d1-312">在安全与合规中心&邮件流报告</span><span class="sxs-lookup"><span data-stu-id="a21d1-312">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="a21d1-313">**仅 PowerShell 中安全链接 (** URL 跟踪) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="a21d1-314">此 cmdlet 的输出显示过去七天内安全链接操作的结果。</span><span class="sxs-lookup"><span data-stu-id="a21d1-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="a21d1-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="a21d1-315">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="a21d1-316">**仅支持 PowerShell 的 EOP 和 Microsoft Defender for Office 365** (邮件) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="a21d1-317">此 cmdlet 的输出包含有关域、日期、事件类型、方向、操作和消息计数的信息。</span><span class="sxs-lookup"><span data-stu-id="a21d1-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="a21d1-318">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="a21d1-318">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="a21d1-319">仅适用于 PowerShell 的 EOP 和 **Defender for Office 365** 检测的邮件 (报告) 。</span><span class="sxs-lookup"><span data-stu-id="a21d1-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="a21d1-320">此 cmdlet 的输出包含有关恶意文件或 URL、网络钓鱼尝试、模拟以及电子邮件或文件中其他潜在威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a21d1-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="a21d1-321">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="a21d1-321">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="a21d1-322">查看 Defender for Office 365 报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="a21d1-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="a21d1-323">若要查看和使用本文中所述的报告，您需要是安全与合规中心内以下角色组&之一：</span><span class="sxs-lookup"><span data-stu-id="a21d1-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a21d1-324">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="a21d1-324">**Organization Management**</span></span>
- <span data-ttu-id="a21d1-325">**安全管理员**</span><span class="sxs-lookup"><span data-stu-id="a21d1-325">**Security Administrator**</span></span>
- <span data-ttu-id="a21d1-326">**安全读者**</span><span class="sxs-lookup"><span data-stu-id="a21d1-326">**Security Reader**</span></span>
- <span data-ttu-id="a21d1-327">**全局阅读器**</span><span class="sxs-lookup"><span data-stu-id="a21d1-327">**Global Reader**</span></span>

<span data-ttu-id="a21d1-328">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-328">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="a21d1-329">注意：将用户添加到 Microsoft 36 & 5 管理中心的相应 Azure Active Directory 角色会为用户提供安全与合规中心中所需的权限以及 Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="a21d1-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a21d1-330">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="a21d1-331">如果报告未显示数据，该做什么？</span><span class="sxs-lookup"><span data-stu-id="a21d1-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="a21d1-332">如果在 Defender for Office 365 报告中看不到数据，请仔细检查策略是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="a21d1-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="a21d1-333">你的组织必须定义[安全链接策略](set-up-atp-safe-links-policies.md)[和安全附件](set-up-atp-safe-attachments-policies.md)策略，以便 Defender for Office 365 保护就位。</span><span class="sxs-lookup"><span data-stu-id="a21d1-333">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="a21d1-334">另请参阅 [反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="a21d1-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a21d1-335">相关主题</span><span class="sxs-lookup"><span data-stu-id="a21d1-335">Related topics</span></span>

[<span data-ttu-id="a21d1-336">安全与合规中心内的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="a21d1-336">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a21d1-337">Azure Active Directory (角色权限</span><span class="sxs-lookup"><span data-stu-id="a21d1-337">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
