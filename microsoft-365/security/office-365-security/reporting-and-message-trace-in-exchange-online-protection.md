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
description: 本文将介绍适用于 EOP 管理员的 Microsoft Exchange Online (报告和) 工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 783c7ea0aca47c805daf66592b401a98f739d071
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288075"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP 中的报告和邮件跟踪

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，EOP 提供了许多不同的报告，可帮助您确定组织的总体状态和运行状况。 此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。

## <a name="usage-reports"></a>使用率报告

**Microsoft 365** 组活动：查看有关创建和使用的 Microsoft 365 组数的信息。

**电子邮件活动**：查看有关整个组织中以及特定用户发送、接收和读取的邮件数的信息。

**电子邮件应用使用情况**：查看有关使用的电子邮件应用的信息。 这包括每个应用的连接总数以及连接的 Outlook 版本。

**邮箱使用情况**：查看有关已使用的存储、配额消耗、项目计数和上次 (发送或读取活动) 邮箱的信息。

有关详细信息，请参阅下列资源：

- [管理中心中的 Microsoft 365 报告 - Microsoft 365 组](../../admin/activity-reports/office-365-groups.md)

- [管理中心中的 Microsoft 365 报告 - 电子邮件活动](../../admin/activity-reports/email-activity.md)

- [管理中心中的 Microsoft 365 报告 - 电子邮件应用使用情况](../../admin/activity-reports/email-apps-usage.md)

- [管理中心中的 Microsoft 365 报告 - 邮箱使用情况](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft 365 &中的安全与合规报告

这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息以及深入了解更多详细信息的能力。

**Defender for Office 365：** 查看属于 Microsoft Defender for Office 365 的安全链接和安全附件的信息。

**EOP：** 查看有关恶意软件检测、欺骗邮件、垃圾邮件检测以及发送到组织以及从组织发送的邮件流的信息。

[查看适用于 Office 365 的 Defender 报告](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自定义报告

使用 Microsoft Graph 以编程方式创建管理中心中可用的报告。 有关详细信息，请参阅 [Microsoft Graph 概述](https://docs.microsoft.com/graph/overview) 和使用 Microsoft Graph 中的 Office [365 使用情况报告](https://docs.microsoft.com/graph/api/resources/report)。

## <a name="message-trace"></a>邮件跟踪

在电子邮件通过 EOP 时，追踪电子邮件信息。 您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。 它还显示邮件在达到最终状态之前对邮件采取的操作。

您可以使用此信息有效回答用户的问题、解决邮件流问题、验证策略更改，以及减少联系技术支持寻求帮助的需要。

请参阅 [安全与合规中心&跟踪](message-trace-scc.md)。

## <a name="audit-logging"></a>审核日志记录

跟踪管理员对您的组织做出的特定更改。 这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。 请参阅 [EOP 中的审核报告](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>报告和邮件跟踪数据的可用性与延迟

下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。

****

|报告类型|数据可用时间（回溯期）|延迟|
|---|---|---|
|邮件保护摘要报告|90 天|邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。|
|邮件保护详细信息报告|90 天|对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。 <p> 若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。|
|邮件跟踪数据|90 天|对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。<p> 对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。|
|

> [!NOTE]
> 无论是通过管理中心还是远程 PowerShell 请求，数据可用性和延迟都是相同的。
