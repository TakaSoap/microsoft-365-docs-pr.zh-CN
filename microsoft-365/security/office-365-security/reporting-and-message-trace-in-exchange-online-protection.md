---
title: 报告和邮件跟踪
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
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解 Microsoft Exchange Online Protection （EOP）管理员可用的报告和故障排除工具。
ms.openlocfilehash: af41f1d3b6ccc7632b392f58c36344239200f915
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206438"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="b8efa-103">EOP 中的报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="b8efa-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="b8efa-104">在没有 Exchange Online 邮箱的 Exchange Online 或独立 Exchange Online Protection （EOP）组织中具有邮箱的 Microsoft 365 组织中，EOP 提供了许多不同的报告，可帮助您确定组织的总体状态和运行状况。</span><span class="sxs-lookup"><span data-stu-id="b8efa-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="b8efa-105">此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。</span><span class="sxs-lookup"><span data-stu-id="b8efa-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="b8efa-106">使用率报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-106">Usage reports</span></span>

<span data-ttu-id="b8efa-107">**Microsoft 365 组活动**：查看有关创建和使用的 microsoft 365 组数量的信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="b8efa-108">**电子邮件活动**：查看有关整个组织中发送、接收和读取的邮件数的信息以及特定用户的信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="b8efa-109">**电子邮件应用程序用法**：查看有关使用的电子邮件应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="b8efa-110">这包括每个应用的连接总数以及正在连接的 Outlook 的版本。</span><span class="sxs-lookup"><span data-stu-id="b8efa-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="b8efa-111">**邮箱使用情况**：查看邮箱的已用存储、配额消耗、项目计数和上次活动（发送或读取活动）的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="b8efa-112">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="b8efa-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="b8efa-113">Microsoft 365 组-管理中心中的 microsoft 365 报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="b8efa-114">Microsoft 365 管理中心内的报告-电子邮件活动</span><span class="sxs-lookup"><span data-stu-id="b8efa-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="b8efa-115">管理中心中的 Microsoft 365 报表-电子邮件应用程序使用情况</span><span class="sxs-lookup"><span data-stu-id="b8efa-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="b8efa-116">"管理中心" 中的 Microsoft 365 报表-邮箱使用情况</span><span class="sxs-lookup"><span data-stu-id="b8efa-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b8efa-117">Microsoft 365 管理中心中的安全性 & 合规性报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b8efa-118">这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息，以及深入了解更多详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="b8efa-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="b8efa-119">**高级威胁防护（ATP）**：查看有关作为 ATP 一部分的安全链接和安全附件的信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="b8efa-120">**EOP**：查看组织中的恶意软件检测、欺骗邮件、垃圾邮件检测和邮件流的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="b8efa-121">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="b8efa-122">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="b8efa-123">使用 Microsoft Graph 以编程方式创建在管理中心中可用的报告。</span><span class="sxs-lookup"><span data-stu-id="b8efa-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="b8efa-124">有关详细信息，请参阅[microsoft Graph 概述](https://docs.microsoft.com/graph/overview)和使用[Microsoft Graph 中的 Office 365 使用率报告](https://docs.microsoft.com/graph/api/resources/report)。</span><span class="sxs-lookup"><span data-stu-id="b8efa-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="b8efa-125">邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="b8efa-125">Message trace</span></span>

<span data-ttu-id="b8efa-126">在电子邮件通过 EOP 时，追踪电子邮件信息。</span><span class="sxs-lookup"><span data-stu-id="b8efa-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="b8efa-127">您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。</span><span class="sxs-lookup"><span data-stu-id="b8efa-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="b8efa-128">它还显示邮件在到达其最终状态之前对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b8efa-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="b8efa-129">您可以使用此信息有效地回答用户的问题，解决邮件流问题，验证策略更改，并缓解联系技术支持寻求帮助的需求。</span><span class="sxs-lookup"><span data-stu-id="b8efa-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="b8efa-130">请参阅[安全性 & 合规性中心中的邮件跟踪](message-trace-scc.md)。</span><span class="sxs-lookup"><span data-stu-id="b8efa-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="b8efa-131">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="b8efa-131">Audit logging</span></span>

<span data-ttu-id="b8efa-132">跟踪管理员对您的组织做出的特定更改。</span><span class="sxs-lookup"><span data-stu-id="b8efa-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="b8efa-133">这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。</span><span class="sxs-lookup"><span data-stu-id="b8efa-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="b8efa-134">请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="b8efa-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="b8efa-135">报告和邮件跟踪数据的可用性与延迟</span><span class="sxs-lookup"><span data-stu-id="b8efa-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="b8efa-136">下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。</span><span class="sxs-lookup"><span data-stu-id="b8efa-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="b8efa-137">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="b8efa-137">**Report type**</span></span>|<span data-ttu-id="b8efa-138">**数据可用时间（回溯期）**</span><span class="sxs-lookup"><span data-stu-id="b8efa-138">**Data available for (look back period)**</span></span>|<span data-ttu-id="b8efa-139">**延迟**</span><span class="sxs-lookup"><span data-stu-id="b8efa-139">**Latency**</span></span>|
|<span data-ttu-id="b8efa-140">邮件保护摘要报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-140">Mail protection summary reports</span></span>|<span data-ttu-id="b8efa-141">90 天</span><span class="sxs-lookup"><span data-stu-id="b8efa-141">90 days</span></span>|<span data-ttu-id="b8efa-p106">邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。</span><span class="sxs-lookup"><span data-stu-id="b8efa-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="b8efa-144">邮件保护详细信息报告</span><span class="sxs-lookup"><span data-stu-id="b8efa-144">Mail protection detail reports</span></span>|<span data-ttu-id="b8efa-145">90 天</span><span class="sxs-lookup"><span data-stu-id="b8efa-145">90 days</span></span>|<span data-ttu-id="b8efa-p107">对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。</span><span class="sxs-lookup"><span data-stu-id="b8efa-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="b8efa-148">若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="b8efa-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="b8efa-149">邮件跟踪数据</span><span class="sxs-lookup"><span data-stu-id="b8efa-149">Message trace data</span></span>|<span data-ttu-id="b8efa-150">90 天</span><span class="sxs-lookup"><span data-stu-id="b8efa-150">90 days</span></span>|<span data-ttu-id="b8efa-151">对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="b8efa-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="b8efa-152">对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="b8efa-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="b8efa-153">无论是通过管理员中心还是远程 PowerShell 请求，数据可用性和延迟都是相同的。</span><span class="sxs-lookup"><span data-stu-id="b8efa-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
