---
title: 邮件流地图
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
description: 管理员可了解如何使用安全 & 合规中心的邮件流仪表板中的邮件流地图，直观显示和跟踪通过连接器和不使用连接器如何流出其组织的邮件流。
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826997"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>安全与合规中心&邮件流图

安全 &**合**[规中心的邮件流](mail-flow-insights-v2.md)仪表板中的邮件流图可以了解邮件流如何通过组织。 你可以使用此信息了解模式、识别异常并修复发生的问题。

![安全电子邮件合规性中心内邮件流仪表板中的邮件流&小部件](../../media/mfi-mail-flow-map-widget.png)

默认情况下，小部件显示图表（称为 *Sankey* 图表）中上一天的邮件流模式。 您可以使用向左箭头 ![ 和向右 ](../../media/scc-left-arrow.png) 键显示 ![ ](../../media/scc-right-arrow.png) 不同天的信息。 每种不同的颜色代表不同的入站或出站连接器的邮件流 (不使用连接器) 。 如果将鼠标悬停在特定颜色上，则将为该类型的连接线显示邮件数。

## <a name="report-view-for-the-mail-flow-map"></a>邮件流地图的报表视图

单击邮件流 **地图小部件** 可转到邮件流 **地图** 报告。

下面的图表提供了报表视图：

- **显示数据：概述**：此基本上是小部件的更大视图。 如果将鼠标悬停在特定颜色上，则会为该类型的连接线显示邮件数。

  ![邮件流地图报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- **显示数据：详细信息**：此视图显示有关连接器和目标域的详细信息。 会列出顶部发件人和收件人域，其他域将放入其他 **域**。 如果您将鼠标悬停在特定颜色和节的上，将显示消息数。

  ![邮件流地图报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

如果单击**筛选器 中的**筛选器报表视图，可以指定具有开始日期和结束**日期的****日期范围**。

若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**

相关见解（如果存在）到 (例如 [，Fix 可能的邮件循环见](mfi-mail-loop-insight.md) 解和时间见) 。

## <a name="details-table-view-for-the-mail-flow-map"></a>邮件流地图的详细信息表视图

如果单击 **链接控件中的** "查看详细信息报表视图，会显示以下信息：

- **Date**
- **类别**
- **连接器/第三方服务提供商**
- **发件人/收件人域**
- **邮件计数**

如果在详细信息**表视图中单击**"筛选器"，可以指定具有开始日期和结束**日期的****日期范围**。

如果选择行，类似于的详细信息会显示在浮出控件中：

![来自邮件流地图中详细信息表格的详细信息浮出控件](../../media/mfi-mail-flow-map-view-details-table-details.png)

若要通过电子邮件发送特定日期范围的报告，请单击"请求**下载"。**

若要返回报告视图，请单击"查看**报告"。**

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
