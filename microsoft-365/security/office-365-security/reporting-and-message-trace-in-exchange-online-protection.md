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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您将了解适用于 EOP 迁移管理员的Microsoft Exchange Online () 工具。
ms.openlocfilehash: 149f7fa36a717a92d3cda5f6f3f82651f0144d73
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827625"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP 中的报告和邮件跟踪

在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的) 独立 Exchange Online Protection (EOP 组织，EOP 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。 此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。

## <a name="usage-reports"></a>使用率报告

**Microsoft 365 组**活动：查看有关已创建和使用的 Microsoft 365 组数量的信息。

**电子邮件活动**：查看有关在整个组织中发送、接收和阅读以及特定用户发送、接收和阅读的邮件数的信息。

**电子邮件应用使用**情况：查看有关使用的电子邮件应用的信息。 其中包括每个应用的连接总数和连接的 Outlook 版本。

**邮箱使用**情况：查看有关使用存储、配额使用情况、项目计数和最后活动的信息， (发送或读取) 活动。

有关详细信息，请参阅下列资源：

- [管理中心内的 Microsoft 365 报表 - Microsoft 365 组](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [管理中心内的 Microsoft 365 报表 - 电子邮件活动](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [管理中心内的 Microsoft 365 报表 - 电子邮件应用使用情况](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [管理中心内的 Microsoft 365 报表 - 邮箱使用情况](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft & Microsoft 365 管理中心的安全和合规性报告

这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息以及详细信息详细信息的深入功能。

**高级威胁 (ATP) ： **查看属于 ATP 的安全链接和安全附件的信息。

**EOP：** 查看有关恶意软件检测、欺骗邮件、垃圾邮件检测和流入组织和从组织发出的邮件流的信息。

[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自定义报告

以编程方式创建在管理中心中通过使用 Microsoft Graph 提供的报表。 有关详细信息，请参阅 Microsoft [Graph 和 Microsoft Graph 中使用](https://docs.microsoft.com/graph/overview) Office [365 使用情况报表的概述](https://docs.microsoft.com/graph/api/resources/report)。

## <a name="message-trace"></a>邮件跟踪

在电子邮件通过 EOP 时，追踪电子邮件信息。 您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。 它还显示邮件在到达最终状态之前对邮件所执行的操作。

您可以使用此信息有效回答用户的问题，解决邮件流问题，验证策略更改，并缩短联系技术支持人员获取帮助的需要。

请参阅 [安全与合规中心&跟踪](message-trace-scc.md)。

## <a name="audit-logging"></a>审核日志记录

跟踪管理员对您的组织做出的特定更改。 这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。 请参阅 [EOP 中的审核报告](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>报告和邮件跟踪数据的可用性与延迟

下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。

****

|报告类型|数据可用时间（回溯期）|延迟|
|---|---|---|
|邮件保护摘要报告|90 天|邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。|
|邮件保护详细报告|90 天|对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。 <br/><br/> 若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。|
|邮件跟踪数据|90 天|对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。<br/><br/> 对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。|
|

> [!NOTE]
> 不分为通过管理中心还是远程 PowerShell 请求数据可用性和延迟都是相同的。
