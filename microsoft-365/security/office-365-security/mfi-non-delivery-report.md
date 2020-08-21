---
title: 邮件流仪表板中的未送达报告
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
description: 管理员可了解如何使用安全 & 合规中心中邮件流仪表板中的"未送达详细信息"报告，来监视组织中发件人的未送达报告 (也称为"NDR"或"退回) 邮件"中的最常见错误代码。
ms.openlocfilehash: bdc2a2a16f76f4e6ada629c82b86423422ab56c9
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826913"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>安全与合规中心中的未&报告

安全 &**合规中心的**[邮件流仪表板中的](mail-flow-insights-v2.md)未送达报告显示未送达报告 (也称为"NDR"或"退回) 中的组织" 此报告显示 NDR 的详细信息，以便您可以解决电子邮件传递问题。

![安全与合规中心的邮件流仪表板中的未送达&小部件](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>未送达报告的报告视图

单击未 **送达报告小** 部件会将您转到 **未送达报告**。

默认情况下，会显示所有错误代码的活动。 如果单击 **"显示数据"，** 你可以从下拉列表中选择特定的错误代码。

如果您将鼠标悬停在图表 (一天) 的特定颜色上，您将看到错误的总消息数。

![非接受域报告中的报告视图](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>未送达报告的详细信息表视图

如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：

- **Date**
- **未送达报告代码**
- **Count**
- **示例消息**：受影响邮件示例的邮件 ID。

如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的****日期范围**。

若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**

选择表中行后，将出现一个浮出控件，并显示以下信息：

- **Date**
- **未送达报告代码**： 可以单击链接，以查找有关特定错误代码的原因和解决方案的详细信息。
- **Count**
- **示例消息**： 您可以单击 **"查看示例邮件** "来 [查看受](message-trace-scc.md) 影响邮件的示例邮件跟踪结果。

![在未送达报告的"详细信息表"视图中选择行后的浮出控件详细信息](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>相关主题

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
