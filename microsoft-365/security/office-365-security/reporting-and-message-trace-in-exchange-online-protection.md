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
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 本文将介绍适用于 EOP 管理员的 Microsoft Exchange Online Protection (和) 工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 929fce14a9e128b724b4aa69d88e4a3062ed5640
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682408"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP 中的报告和邮件跟踪

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，EOP 提供了许多不同的报告，可帮助您确定您的总体状态和运行状况组织。 此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。

## <a name="usage-reports"></a>使用率报告

- **Microsoft 365组活动**：查看有关已创建Microsoft 365组数的信息。 有关详细信息，请参阅Microsoft 365中心[中的报告 - Microsoft 365组](../../admin/activity-reports/office-365-groups.md)。
- **电子邮件** 活动：查看有关整个组织中以及特定用户发送、接收和阅读的邮件数的信息。 有关详细信息，请参阅Microsoft 365[中心中的报表 - 电子邮件活动](../../admin/activity-reports/email-activity.md)。
- **电子邮件应用** 使用情况：查看有关使用的电子邮件应用的信息。 这包括每个应用的连接总数，以及连接Outlook版本。 有关详细信息，请参阅Microsoft 365中心[中的报告 - 电子邮件应用使用情况](../../admin/activity-reports/email-apps-usage.md)。
- **邮箱使用情况**：查看有关邮箱发送或读取 (使用的存储、配额消耗、项目计数和) 活动的信息。 有关详细信息，请参阅Microsoft 365中心[中的报告 - 邮箱使用情况](../../admin/activity-reports/mailbox-usage.md)。

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 门户中的安全报告

这些增强的报告为 EOP 管理员提供了交互式报告体验，其中包括摘要信息，以及深入了解更多详细信息的能力。

- **Defender for Office 365**： View information about 保险箱 Links and 保险箱 Attachments that are part of Microsoft Defender for Office 365. 有关详细信息，请参阅在 Office 365 门户中查看适用于[Microsoft 365 Defender报告](view-reports-for-mdo.md)。
- **EOP**：查看有关您组织的恶意软件检测、欺骗邮件、垃圾邮件检测和邮件流的信息。 有关详细信息，请参阅在电子邮件[门户中查看Microsoft 365 Defender报告](view-email-security-reports.md)。

## <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

有关详细信息，请参阅安全 [与合规中心内的邮件&见解](mail-flow-insights-v2.md)。

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph

使用 Microsoft Graph 以编程方式创建可在管理中心Graph。 有关详细信息，请参阅 [Microsoft](/graph/overview) Graph 概述Office 365 [Microsoft Graph](/graph/api/resources/report)。

## <a name="message-trace"></a>邮件跟踪

在电子邮件通过 EOP 时，追踪电子邮件信息。 您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。 它还显示在邮件达到最终状态之前对邮件采取的操作。

您可以使用此信息有效回答用户的问题、解决邮件流问题、验证策略更改，以及减少联系技术支持寻求帮助的需要。

请参阅[邮件门户中Microsoft 365 Defender跟踪](message-trace-scc.md)。

## <a name="audit-logging"></a>审核日志记录

跟踪管理员对您的组织做出的特定更改。 这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。 请参阅[审核报告中Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>报告和邮件跟踪数据的可用性与延迟

下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。

|报告类型|数据可用时间（回溯期）|延迟|
|---|---|---|
|邮件保护摘要报告|90 天|邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。|
|邮件保护详细信息报告|90 天|对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。 <p> 若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。|
|邮件跟踪数据|90 天|对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。<p> 对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。|

> [!NOTE]
> 无论是通过管理中心还是远程 PowerShell 请求，数据可用性和延迟都是相同的。
