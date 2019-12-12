---
title: Exchange Online Protection 中的报告和邮件跟踪
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。下表描述了 EOP 管理员可用的报告和故障排除工具。
ms.openlocfilehash: 251286fca4ed54b87809c46e6e0f47ea618df747
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971502"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="f3850-105">Exchange Online Protection 中的报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="f3850-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="f3850-106">Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。</span><span class="sxs-lookup"><span data-stu-id="f3850-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="f3850-107">此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。</span><span class="sxs-lookup"><span data-stu-id="f3850-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="f3850-108">使用率报告</span><span class="sxs-lookup"><span data-stu-id="f3850-108">Usage reports</span></span>

<span data-ttu-id="f3850-109">**Office 365 组活动**：查看有关创建和使用的 office 365 组数量的信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="f3850-110">**电子邮件活动**：查看有关整个组织中发送、接收和读取的邮件数的信息以及特定用户的信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="f3850-111">**电子邮件应用程序用法**：查看有关使用的电子邮件应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="f3850-112">这包括每个应用的连接总数以及正在连接的 Outlook 的版本。</span><span class="sxs-lookup"><span data-stu-id="f3850-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="f3850-113">**邮箱使用情况**：查看邮箱的已用存储、配额消耗、项目计数和上次活动（发送或读取活动）的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="f3850-114">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f3850-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="f3850-115">Admin center 中的 office 365 报告-Office 365 组</span><span class="sxs-lookup"><span data-stu-id="f3850-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="f3850-116">管理中心内的 Office 365 报告-电子邮件活动</span><span class="sxs-lookup"><span data-stu-id="f3850-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="f3850-117">管理中心中的 Office 365 报表-电子邮件应用程序使用情况</span><span class="sxs-lookup"><span data-stu-id="f3850-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="f3850-118">管理中心中的 Office 365 报表-邮箱使用情况</span><span class="sxs-lookup"><span data-stu-id="f3850-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f3850-119">Microsoft 365 管理中心中的安全性 & 合规性报告</span><span class="sxs-lookup"><span data-stu-id="f3850-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f3850-120">这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息，以及深入了解更多详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="f3850-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="f3850-121">**高级威胁防护（ATP）**：查看有关作为 ATP 一部分的安全链接和安全附件的信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="f3850-122">**EOP**：查看组织中的恶意软件检测、欺骗邮件、垃圾邮件检测和邮件流的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="f3850-123">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="f3850-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="f3850-124">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="f3850-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="f3850-125">使用 Microsoft Graph 以编程方式创建 Microsoft 365 管理中心提供的报告。</span><span class="sxs-lookup"><span data-stu-id="f3850-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="f3850-126">请参阅[在 Microsoft Graph 中使用 Office 365 使用情况报告](https://docs.microsoft.com/graph/api/resources/report)的主题。</span><span class="sxs-lookup"><span data-stu-id="f3850-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="f3850-127">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="f3850-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="f3850-128">以编程方式创建报表。</span><span class="sxs-lookup"><span data-stu-id="f3850-128">Programmatically create reports.</span></span> <span data-ttu-id="f3850-129">请参阅[Microsoft Graph 概述](https://docs.microsoft.com/graph/overview)。</span><span class="sxs-lookup"><span data-stu-id="f3850-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="f3850-130">Message trace</span><span class="sxs-lookup"><span data-stu-id="f3850-130">Message trace</span></span>

<span data-ttu-id="f3850-131">在电子邮件通过 EOP 时，追踪电子邮件信息。</span><span class="sxs-lookup"><span data-stu-id="f3850-131">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="f3850-132">您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。</span><span class="sxs-lookup"><span data-stu-id="f3850-132">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="f3850-133">它还显示邮件在到达其最终状态之前对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f3850-133">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="f3850-134">您可以使用此信息有效地回答用户的问题，解决邮件流问题，验证策略更改，并缓解联系技术支持寻求帮助的需求。</span><span class="sxs-lookup"><span data-stu-id="f3850-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="f3850-135">请参阅[跟踪电子](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)邮件</span><span class="sxs-lookup"><span data-stu-id="f3850-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="f3850-136">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="f3850-136">Audit logging</span></span>

<span data-ttu-id="f3850-137">跟踪管理员对您的组织做出的特定更改。</span><span class="sxs-lookup"><span data-stu-id="f3850-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="f3850-138">这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。</span><span class="sxs-lookup"><span data-stu-id="f3850-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="f3850-139">请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f3850-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="f3850-140">报告和邮件跟踪数据的可用性与延迟</span><span class="sxs-lookup"><span data-stu-id="f3850-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="f3850-141">下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。</span><span class="sxs-lookup"><span data-stu-id="f3850-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="f3850-142">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="f3850-142">**Report type**</span></span>|<span data-ttu-id="f3850-143">**数据可用时间（回溯期）**</span><span class="sxs-lookup"><span data-stu-id="f3850-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="f3850-144">**延迟**</span><span class="sxs-lookup"><span data-stu-id="f3850-144">**Latency**</span></span>|
|<span data-ttu-id="f3850-145">邮件保护摘要报告</span><span class="sxs-lookup"><span data-stu-id="f3850-145">Mail protection summary reports</span></span>|<span data-ttu-id="f3850-146">90 天</span><span class="sxs-lookup"><span data-stu-id="f3850-146">90 days</span></span>|<span data-ttu-id="f3850-p108">邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。</span><span class="sxs-lookup"><span data-stu-id="f3850-p108">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="f3850-149">邮件保护详细信息报告</span><span class="sxs-lookup"><span data-stu-id="f3850-149">Mail protection detail reports</span></span>|<span data-ttu-id="f3850-150">90 天</span><span class="sxs-lookup"><span data-stu-id="f3850-150">90 days</span></span>|<span data-ttu-id="f3850-p109">对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。</span><span class="sxs-lookup"><span data-stu-id="f3850-p109">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="f3850-153">若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="f3850-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="f3850-154">邮件跟踪数据</span><span class="sxs-lookup"><span data-stu-id="f3850-154">Message trace data</span></span>|<span data-ttu-id="f3850-155">90 天</span><span class="sxs-lookup"><span data-stu-id="f3850-155">90 days</span></span>|<span data-ttu-id="f3850-156">对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="f3850-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="f3850-157">对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="f3850-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="f3850-158">无论是通过 Microsoft 365 管理中心还是远程 PowerShell 请求，数据可用性和延迟都是相同的。</span><span class="sxs-lookup"><span data-stu-id="f3850-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
