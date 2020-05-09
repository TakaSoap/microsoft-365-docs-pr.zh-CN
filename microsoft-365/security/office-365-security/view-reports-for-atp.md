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
description: 在安全&amp;合规中心中查找和使用适用于 Office 365 高级威胁防护的报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c202e7df274e81da5395f7466199d85443361c05
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173318"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="081a9-103">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="081a9-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="081a9-104">如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)（ATP），并且您具有[必要的权限](#what-permissions-are-needed-to-view-the-atp-reports)，则可以在安全&amp;合规中心中使用多个 ATP 报告。</span><span class="sxs-lookup"><span data-stu-id="081a9-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="081a9-105">（转到 "**报表** \> "**仪表板**。）</span><span class="sxs-lookup"><span data-stu-id="081a9-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![安全&amp;合规中心仪表板可帮助您了解高级威胁防护的工作情况](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="081a9-107">ATP 报告包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="081a9-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="081a9-108">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="081a9-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="081a9-109">ATP 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="081a9-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="081a9-110">ATP 邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="081a9-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="081a9-111">[实时检测或资源管理器](threat-explorer.md)（取决于您是否拥有 OFFICE 365 ATP 计划1或2）</span><span class="sxs-lookup"><span data-stu-id="081a9-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="081a9-112">...[等等](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="081a9-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="081a9-113">阅读本文，了解有关 ATP 报告以及如何使用它们的概述。</span><span class="sxs-lookup"><span data-stu-id="081a9-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="081a9-114">威胁防护状态</span><span class="sxs-lookup"><span data-stu-id="081a9-114">Threat Protection Status report</span></span>

<span data-ttu-id="081a9-115">**威胁防护状态**报告是一个视图，它将有关检测到的恶意内容和恶意电子邮件的信息，以及[Exchange Online Protection](exchange-online-protection-overview.md) （EOP）和 Office 365 ATP （）和[Office ATP](office-365-atp.md)结合在一起。</span><span class="sxs-lookup"><span data-stu-id="081a9-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="081a9-116">此报告可用于查看一段时间内的检测（最多90天），并使安全管理员能够确定趋势或确定策略是否需要调整。</span><span class="sxs-lookup"><span data-stu-id="081a9-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="081a9-117">该报告提供了包含恶意内容的独特电子邮件的聚合计数，如反恶意软件引擎阻止的文件或网站地址（Url）、[零小时自动清除（ZAP）](zero-hour-auto-purge.md)和 atp 功能（如[atp 安全链接](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和[atp 反网络钓鱼](set-up-anti-phishing-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="081a9-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="081a9-118">信息的筛选器和细目允许对此报告中的信息进行更精细的分类。</span><span class="sxs-lookup"><span data-stu-id="081a9-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="081a9-119">具体来说，**电子邮件** \> **网络钓鱼**和**电子邮件** \> **恶意软件视图**包含 "分解方式" 菜单。</span><span class="sxs-lookup"><span data-stu-id="081a9-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="081a9-120">它会将数据分解为：</span><span class="sxs-lookup"><span data-stu-id="081a9-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="081a9-121">按检测类型</span><span class="sxs-lookup"><span data-stu-id="081a9-121">By detection type</span></span>|<span data-ttu-id="081a9-122">哪些策略有助于捕捉这些威胁？</span><span class="sxs-lookup"><span data-stu-id="081a9-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="081a9-123">按检测技术</span><span class="sxs-lookup"><span data-stu-id="081a9-123">By detection technology</span></span>|<span data-ttu-id="081a9-124">哪种基本的 Microsoft 技术会发现威胁？</span><span class="sxs-lookup"><span data-stu-id="081a9-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="081a9-125">按传递状态</span><span class="sxs-lookup"><span data-stu-id="081a9-125">By delivery status</span></span>|<span data-ttu-id="081a9-126">作为威胁检测到的电子邮件发生了什么？</span><span class="sxs-lookup"><span data-stu-id="081a9-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="081a9-127">电子邮件 > 网络钓鱼 |恶意软件视图对所示的检测技术有细微的细分，其中类别如*ATP 生成的文件信誉*、*文件沙箱*、 *URL 沙箱*、*反欺骗： DMARC 故障*，例如，有助于准确准确地查明组织要拦截威胁的功能 led。</span><span class="sxs-lookup"><span data-stu-id="081a9-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![显示 "分解依据" 的威胁 Protection 状态报告下拉列表。](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="081a9-129">这些视图为您提供通过按钮单击（在**电子邮件** \> **网络钓鱼**、**电子邮件** \> **恶意软件**和**内容** \> **恶意软件**视图）中导出的选项。</span><span class="sxs-lookup"><span data-stu-id="081a9-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="081a9-130">可以在 Excel 中打开导出到您的计算机上的聚合数据。</span><span class="sxs-lookup"><span data-stu-id="081a9-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![此图显示了导出为恶意软件视图菜单中的一个选项、"创建计划" 和 "请求报告"。](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="081a9-132">**注意**：可以为**网络钓鱼**和**恶意软件**导出的最大条目数就是10000。</span><span class="sxs-lookup"><span data-stu-id="081a9-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="081a9-133">如果导出视图，则仅导出最新的10000项。</span><span class="sxs-lookup"><span data-stu-id="081a9-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="081a9-134">概述和电子邮件视图将在处理小时数（而不是24小时）内显示信息（请求重新）。</span><span class="sxs-lookup"><span data-stu-id="081a9-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="081a9-135">此处的提高速度是一个清晰的信号）！</span><span class="sxs-lookup"><span data-stu-id="081a9-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="081a9-136">拥有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](exchange-online-protection-eop.md) （EOP）的客户可以使用威胁防护状态报告;但是，在 ATP 客户的威胁防护状态报告中显示的信息可能包含不同的 EOP 客户可能看到的数据。</span><span class="sxs-lookup"><span data-stu-id="081a9-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="081a9-137">例如，ATP 客户的威胁防护状态报告将包含有关[在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](atp-for-spo-odb-and-teams.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="081a9-138">此类信息特定于 ATP，因此具有 EOP 但不是 ATP 的客户将不会在其威胁防护状态报告中看到这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="081a9-139">若要查看威胁防护状态报告，请在[安全&amp;合规性中心](https://protection.office.com)中转到 "**报告** \> "**仪表板** \> **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="081a9-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![ATP 威胁防护状态报告](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="081a9-141">若要获取一天的详细状态，请将鼠标悬停在关系图上。</span><span class="sxs-lookup"><span data-stu-id="081a9-141">To get detailed status for a day, hover over the graph.</span></span>

![一天的 ATP 威胁防护状态数据](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="081a9-143">默认情况下，威胁防护状态报告显示过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="081a9-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="081a9-144">不过，您可以选择 "**筛选器**" 并将日期范围更改为查看最多90天的数据。</span><span class="sxs-lookup"><span data-stu-id="081a9-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="081a9-145">（如果使用的是试用订阅，则可能限制为30天的数据。）</span><span class="sxs-lookup"><span data-stu-id="081a9-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![ATP 威胁防护状态筛选器](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="081a9-147">您还可以使用 "**查看数据依据**" 菜单来更改报表中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![查看 ATP 威胁保护状态报告的选项](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="081a9-149">URL 保护状态报告</span><span class="sxs-lookup"><span data-stu-id="081a9-149">URL Protection Status report</span></span>

<span data-ttu-id="081a9-150">此报告基于每次单击收集的数据和检测到的威胁（而大多数其他电子邮件威胁相关报告针对每个邮件数据）。</span><span class="sxs-lookup"><span data-stu-id="081a9-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="081a9-151">此报告旨在显示来自电子邮件和文档中的超链接的威胁，每次单击。</span><span class="sxs-lookup"><span data-stu-id="081a9-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="081a9-152">有两种视图：</span><span class="sxs-lookup"><span data-stu-id="081a9-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="081a9-153">URL 单击保护操作</span><span class="sxs-lookup"><span data-stu-id="081a9-153">URL click protection action</span></span>|<span data-ttu-id="081a9-154">查看阻止的 Url 的数量、被阻止但被用户通过单击覆盖的 Url，通过用户的单击覆盖和允许。</span><span class="sxs-lookup"><span data-stu-id="081a9-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="081a9-155">按应用程序单击的 URL</span><span class="sxs-lookup"><span data-stu-id="081a9-155">URL click by application</span></span>|<span data-ttu-id="081a9-156">查看从中单击了 URL 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="081a9-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="081a9-157">在详细信息表中，您将能够看到有关单击时间和用户信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="081a9-158">最后，请记住 URL 保护状态报告显示来自 ATP 安全链接功能的保护，因此只有启用了 ATP 安全链接的客户才会看到此报告上反映的数据。</span><span class="sxs-lookup"><span data-stu-id="081a9-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="081a9-159">这是一个 "*保护趋势" 报告*，即数据表示较大数据集中的趋势。</span><span class="sxs-lookup"><span data-stu-id="081a9-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="081a9-160">因此，在这里，聚合视图中的数据不是实时提供的，但详细信息表视图中的数据是，因此在这两种视图之间可能会出现细微差异。</span><span class="sxs-lookup"><span data-stu-id="081a9-160">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="081a9-161">ATP 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="081a9-161">ATP File Types report</span></span>

<span data-ttu-id="081a9-162">**Atp 文件类型**报告显示通过[ATP 安全附件](atp-safe-attachments.md)检测为恶意的文件类型。</span><span class="sxs-lookup"><span data-stu-id="081a9-162">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="081a9-163">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **ATP 文件类型**。</span><span class="sxs-lookup"><span data-stu-id="081a9-163">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![ATP 文件类型报告](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="081a9-165">当您将鼠标悬停在特定的一天时，您可以看到[ATP 安全附件](atp-safe-attachments.md)和[ &amp;反垃圾邮件反恶意软件保护](anti-spam-and-anti-malware-protection.md)检测到的恶意文件的类型细目。</span><span class="sxs-lookup"><span data-stu-id="081a9-165">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP 文件类型报告一天的数据](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="081a9-167">ATP 邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="081a9-167">ATP Message Disposition report</span></span>

<span data-ttu-id="081a9-168">**ATP 邮件处置**报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="081a9-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="081a9-169">若要查看此报告，请[在&amp;安全合规性中心](https://protection.office.com)中，转到 "**报告** \> "**仪表板** \> **ATP 邮件处置**。</span><span class="sxs-lookup"><span data-stu-id="081a9-169">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![ATP 邮件处置报告](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="081a9-171">当您将鼠标悬停在图表中的某条上时，可以看到在那天中对检测到的电子邮件执行了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="081a9-171">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![一天的 ATP 邮件处置报告数据](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="081a9-173">要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="081a9-173">Additional reports to view</span></span>

<span data-ttu-id="081a9-174">除了本文中介绍的 ATP 报告之外，还有几个其他报告可供使用，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="081a9-174">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="081a9-175">**报告**</span><span class="sxs-lookup"><span data-stu-id="081a9-175">**Report(s)**</span></span>|<span data-ttu-id="081a9-176">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="081a9-176">**Details**</span></span>|
|<span data-ttu-id="081a9-177">**浏览器**或**实时检测**：（Office 365 ATP 计划2客户具有资源管理器;Office 365 ATP 计划1客户具有实时检测。</span><span class="sxs-lookup"><span data-stu-id="081a9-177">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="081a9-178">威胁资源管理器（和实时检测）</span><span class="sxs-lookup"><span data-stu-id="081a9-178">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="081a9-179">**电子邮件安全报告**，如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="081a9-179">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="081a9-180">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="081a9-180">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="081a9-181">**ATP 安全链接 URL 跟踪**：（这是使用 PowerShell 生成的报告。）此报告显示过去七（7）天的 ATP 安全链接操作的结果。</span><span class="sxs-lookup"><span data-stu-id="081a9-181">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="081a9-182">UrlTrace cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="081a9-182">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|<span data-ttu-id="081a9-183">**EOP 和 ATP 结果**：（这是使用 PowerShell 生成的自定义报表）。</span><span class="sxs-lookup"><span data-stu-id="081a9-183">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="081a9-184">此报告包含域、日期、事件类型、方向、操作和邮件计数等信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-184">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="081a9-185">MailTrafficATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="081a9-185">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|<span data-ttu-id="081a9-186">**EOP 和 ATP 检测**：（这是使用 PowerShell 生成的自定义报告）。</span><span class="sxs-lookup"><span data-stu-id="081a9-186">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="081a9-187">此报告包含有关电子邮件或文件中的恶意文件或 Url、网络钓鱼企图、模拟和其他潜在威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="081a9-187">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="081a9-188">MailDetailATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="081a9-188">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="081a9-189">查看 ATP 报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="081a9-189">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="081a9-190">为了查看和使用本文中介绍的报告，**必须为安全&amp;合规中心和 Exchange 管理中心分配适当的角色**。</span><span class="sxs-lookup"><span data-stu-id="081a9-190">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="081a9-191">对于安全&amp;合规中心，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="081a9-191">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="081a9-192">组织管理</span><span class="sxs-lookup"><span data-stu-id="081a9-192">Organization Management</span></span>
  - <span data-ttu-id="081a9-193">安全管理员（可在 Azure Active Directory 管理中心中分配（[https://aad.portal.azure.com](https://aad.portal.azure.com)））</span><span class="sxs-lookup"><span data-stu-id="081a9-193">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="081a9-194">安全操作员（可在 Azure Active Directory 管理中心中分配（[https://aad.portal.azure.com](https://aad.portal.azure.com)））</span><span class="sxs-lookup"><span data-stu-id="081a9-194">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="081a9-195">安全读取者</span><span class="sxs-lookup"><span data-stu-id="081a9-195">Security Reader</span></span>

- <span data-ttu-id="081a9-196">对于 Exchange Online，必须在 Exchange 管理中心（[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)）或 PowerShell cmdlet 中分配以下角色之一（请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)）：</span><span class="sxs-lookup"><span data-stu-id="081a9-196">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="081a9-197">组织管理</span><span class="sxs-lookup"><span data-stu-id="081a9-197">Organization Management</span></span>
  - <span data-ttu-id="081a9-198">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="081a9-198">View-only Organization Management</span></span>
  - <span data-ttu-id="081a9-199">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="081a9-199">View-Only Recipients role</span></span>
  - <span data-ttu-id="081a9-200">合规性管理</span><span class="sxs-lookup"><span data-stu-id="081a9-200">Compliance Management</span></span>

<span data-ttu-id="081a9-201">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="081a9-201">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="081a9-202">安全&amp;合规性中心中的权限</span><span class="sxs-lookup"><span data-stu-id="081a9-202">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="081a9-203">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="081a9-203">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="081a9-204">如果报告不显示数据，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="081a9-204">What if the reports aren't showing data?</span></span>

<span data-ttu-id="081a9-205">如果您未在 ATP 报告中看到数据，请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="081a9-205">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="081a9-206">您的组织必须定义[Atp 安全链接策略](set-up-atp-safe-links-policies.md)和[atp 安全附件策略](set-up-atp-safe-attachments-policies.md)，以便将 ATP 保护设置到位。</span><span class="sxs-lookup"><span data-stu-id="081a9-206">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="081a9-207">另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="081a9-207">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="081a9-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="081a9-208">Related topics</span></span>

[<span data-ttu-id="081a9-209">安全&amp;合规中心中的报告和见解</span><span class="sxs-lookup"><span data-stu-id="081a9-209">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="081a9-210">在安全&amp;合规中心中创建报表的日程安排</span><span class="sxs-lookup"><span data-stu-id="081a9-210">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="081a9-211">在安全&amp;合规中心中设置和下载自定义报告</span><span class="sxs-lookup"><span data-stu-id="081a9-211">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="081a9-212">角色权限（Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="081a9-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
