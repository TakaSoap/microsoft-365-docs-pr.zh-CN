---
title: 邮件流仪表板中的"非接受域"报告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"不接受域"报告来监视来自本地组织的邮件，其中发件人域未在 Microsoft 365 中配置。
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826937"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>安全电子邮件合规中心中的"非&域"报告

安全 & **合规** 中心的 [邮件流仪表板中的"](mail-flow-insights-v2.md) 未接受域"报告显示内部部署电子邮件组织中邮件的相关信息，其中发件人域未在 Microsoft 365 组织中配置为接受域。

如果我们有数据来证明这些邮件的意图是恶意邮件，Microsoft 365 可能会限制这些邮件。 因此，请务必了解发生的情况以及解决问题。

!["安全 &合规中心"""邮件流"仪表板中的"不接受&小部件](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>非接受域报告的报告视图

在"不接受域 **"小部件中单击** 此图表会将您转到 **"不接受域"** 报告。

默认情况下，会显示所有受影响连接器的活动。 如果您单击 **"显示数据"，** 可以在下拉列表中选择特定连接器。

如果您将鼠标悬停在图表 (的数据) 点，您将看到连接器的邮件总数。

![非接受域报告中的报告视图](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>非接受域报告的详细信息表视图

如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：

- **Date**
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例消息**：受影响邮件示例的邮件 ID。

如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的****日期范围**。

若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**

选择表中行后，将出现一个浮出控件，并显示以下信息：

- **Date**
- **入站连接器名称**
- **发件人域**
- **邮件计数**
- **示例消息**： 您可以单击 **"查看示例** 邮件"来 [查看受](message-trace-scc.md) 影响邮件的示例邮件跟踪结果。

![在非接受域报告的"详细信息表"视图中选择行后的详细信息浮出控件](../../media/mfi-non-accepted-domain-report-details-flyout.png)

若要返回报告视图，请单击"查看**报告"。**

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
