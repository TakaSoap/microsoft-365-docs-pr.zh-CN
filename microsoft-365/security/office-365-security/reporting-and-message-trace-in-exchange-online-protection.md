---
title: 报告和邮件跟踪
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 本文将介绍适用于 EOP 管理员的 Microsoft Exchange Online Protection (和) 工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d5e5493925a17725bfb9d6698b3f94050960ccc7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203587"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="97f89-103">EOP 中的报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="97f89-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97f89-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="97f89-104">**Applies to**</span></span>
- [<span data-ttu-id="97f89-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97f89-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="97f89-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="97f89-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97f89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97f89-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="97f89-108">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 提供了许多不同的报告，可帮助您确定组织的总体状态和运行状况。</span><span class="sxs-lookup"><span data-stu-id="97f89-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="97f89-109">此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。</span><span class="sxs-lookup"><span data-stu-id="97f89-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="97f89-110">使用率报告</span><span class="sxs-lookup"><span data-stu-id="97f89-110">Usage reports</span></span>

<span data-ttu-id="97f89-111">**Microsoft 365 组活动**：查看有关创建和使用的 Microsoft 365 组数的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="97f89-112">**电子邮件活动**：查看有关整个组织中以及特定用户发送、接收和阅读的邮件数的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="97f89-113">**电子邮件应用** 使用情况：查看有关使用的电子邮件应用的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="97f89-114">这包括每个应用程序的连接总数以及连接的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="97f89-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="97f89-115">**邮箱使用情况**：查看有关已使用的存储、配额消耗、项目计数以及邮箱发送 (读取活动) 活动的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="97f89-116">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="97f89-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="97f89-117">管理中心中的 Microsoft 365 报表 - Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="97f89-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="97f89-118">管理中心中的 Microsoft 365 报表 - 电子邮件活动</span><span class="sxs-lookup"><span data-stu-id="97f89-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="97f89-119">管理中心中的 Microsoft 365 报表 - 电子邮件应用使用情况</span><span class="sxs-lookup"><span data-stu-id="97f89-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="97f89-120">管理中心中的 Microsoft 365 报表 - 邮箱使用情况</span><span class="sxs-lookup"><span data-stu-id="97f89-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="97f89-121">Microsoft 365 &中心中的安全与合规性报告</span><span class="sxs-lookup"><span data-stu-id="97f89-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="97f89-122">这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息，以及深入了解更多详细信息的能力。</span><span class="sxs-lookup"><span data-stu-id="97f89-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="97f89-123">**适用于 Office 365** 的 Defender：查看有关属于 Microsoft Defender for Office 365 的安全链接和安全附件的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="97f89-124">**EOP：** 查看有关您组织的恶意软件检测、欺骗邮件、垃圾邮件检测和邮件流的信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="97f89-125">查看适用于 Office 365 的 Defender 报告</span><span class="sxs-lookup"><span data-stu-id="97f89-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="97f89-126">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="97f89-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="97f89-127">使用 Microsoft Graph 以编程方式创建管理中心中可用的报告。</span><span class="sxs-lookup"><span data-stu-id="97f89-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="97f89-128">有关详细信息，请参阅 [Microsoft Graph 概述](/graph/overview) 和在 Microsoft Graph 中处理 Office [365 使用情况报告](/graph/api/resources/report)。</span><span class="sxs-lookup"><span data-stu-id="97f89-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="97f89-129">邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="97f89-129">Message trace</span></span>

<span data-ttu-id="97f89-130">在电子邮件通过 EOP 时，追踪电子邮件信息。</span><span class="sxs-lookup"><span data-stu-id="97f89-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="97f89-131">您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。</span><span class="sxs-lookup"><span data-stu-id="97f89-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="97f89-132">它还显示在邮件达到最终状态之前对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="97f89-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="97f89-133">您可以使用此信息有效回答用户的问题、解决邮件流问题、验证策略更改，以及减少联系技术支持寻求帮助的需要。</span><span class="sxs-lookup"><span data-stu-id="97f89-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="97f89-134">请参阅 [安全与合规中心&邮件跟踪](message-trace-scc.md)。</span><span class="sxs-lookup"><span data-stu-id="97f89-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="97f89-135">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="97f89-135">Audit logging</span></span>

<span data-ttu-id="97f89-136">跟踪管理员对您的组织做出的特定更改。</span><span class="sxs-lookup"><span data-stu-id="97f89-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="97f89-137">这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。</span><span class="sxs-lookup"><span data-stu-id="97f89-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="97f89-138">请参阅 [EOP 中的审核报告](auditing-reports-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="97f89-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="97f89-139">报告和邮件跟踪数据的可用性与延迟</span><span class="sxs-lookup"><span data-stu-id="97f89-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="97f89-140">下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。</span><span class="sxs-lookup"><span data-stu-id="97f89-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="97f89-141">报告类型</span><span class="sxs-lookup"><span data-stu-id="97f89-141">Report type</span></span>|<span data-ttu-id="97f89-142">数据可用时间（回溯期）</span><span class="sxs-lookup"><span data-stu-id="97f89-142">Data available for (look back period)</span></span>|<span data-ttu-id="97f89-143">延迟</span><span class="sxs-lookup"><span data-stu-id="97f89-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="97f89-144">邮件保护摘要报告</span><span class="sxs-lookup"><span data-stu-id="97f89-144">Mail protection summary reports</span></span>|<span data-ttu-id="97f89-145">90 天</span><span class="sxs-lookup"><span data-stu-id="97f89-145">90 days</span></span>|<span data-ttu-id="97f89-p106">邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。</span><span class="sxs-lookup"><span data-stu-id="97f89-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="97f89-148">邮件保护详细信息报告</span><span class="sxs-lookup"><span data-stu-id="97f89-148">Mail protection detail reports</span></span>|<span data-ttu-id="97f89-149">90 天</span><span class="sxs-lookup"><span data-stu-id="97f89-149">90 days</span></span>|<span data-ttu-id="97f89-p107">对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。</span><span class="sxs-lookup"><span data-stu-id="97f89-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="97f89-152">若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="97f89-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="97f89-153">邮件跟踪数据</span><span class="sxs-lookup"><span data-stu-id="97f89-153">Message trace data</span></span>|<span data-ttu-id="97f89-154">90 天</span><span class="sxs-lookup"><span data-stu-id="97f89-154">90 days</span></span>|<span data-ttu-id="97f89-155">对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="97f89-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="97f89-156">对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="97f89-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="97f89-157">无论是通过管理中心还是远程 PowerShell 请求，数据可用性和延迟都是相同的。</span><span class="sxs-lookup"><span data-stu-id="97f89-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>