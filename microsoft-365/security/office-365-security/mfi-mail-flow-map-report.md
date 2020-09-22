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
description: 管理员可以了解如何使用安全 & 合规性中心中邮件流仪表板中的邮件流映射，直观地显示和跟踪邮件在其组织中的流动和发件人，而无需使用连接器。
ms.openlocfilehash: 74cabb7f7b34be6248d18d71565c8a9729d7e38b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199367"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>安全 & 合规中心中的邮件流映射

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[安全 & 合规性中心](https://protection.office.com)的邮件[流仪表板](mail-flow-insights-v2.md)中的**邮件流映射**可提供邮件在组织中流动的见解。 您可以使用此信息来了解模式、确定异常并在出现问题时解决问题。

![安全 & 合规性中心的邮件流仪表板中的邮件流映射小部件](../../media/mfi-mail-flow-map-widget.png)

默认情况下，该小部件显示来自前一天的邮件流模式（称为 " *Sankey* 图表"）。 您可以使用向左箭头 ![ ](../../media/scc-left-arrow.png) 和向右箭头向 ![ 右箭头 ](../../media/scc-right-arrow.png) 来显示不同天的信息。 每种不同的颜色代表不同入站或出站连接器上的邮件流 (或不使用连接器) 。 如果将鼠标悬停在特定颜色上，则将显示该类型的连接符的邮件数。

## <a name="report-view-for-the-mail-flow-map"></a>邮件流映射的报告视图

单击 " **邮件流地图** " 小部件将转到 **邮件流地图** 报告。

报表视图中提供了以下图表：

- **显示数据：概述**：这基本上是小部件的更大视图。 如果将鼠标悬停在特定颜色上，则将显示该类型的连接符的邮件数。

  ![邮件流映射报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- **显示以下项的数据：详细**信息：此视图显示有关连接器和目标域的详细信息。 将列出最上面的发件人和收件人域，其余部分将放入 **其他**域中。 如果将鼠标悬停在特定的颜色和节上，则会显示邮件数。

  ![邮件流映射报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

如果您在报告视图中单击 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。

若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。

如果可用，相关的见解将显示在邮件流地图的下面 (例如， [修复可能的邮件循环真知灼见](mfi-mail-loop-insight.md)) 。

## <a name="details-table-view-for-the-mail-flow-map"></a>邮件流映射的详细信息表格视图

如果您在报告视图中单击 " **查看详细信息表** "，将显示以下信息：

- **Date**
- **类别**
- **连接器/第三方服务提供商**
- **发件人/收件人域**
- **邮件计数**

如果单击 "详细信息" 表视图中的 " **筛选器** "，则可以指定具有 " **开始日期** " 和 " **结束日期**" 的日期范围。

如果选择行，则在浮出控件中显示类似的详细信息：

![详细信息从邮件流映射的详细信息表中飞出控件](../../media/mfi-mail-flow-map-view-details-table-details.png)

若要通过电子邮件将特定日期范围的报告发送给一个或多个收件人，请单击 " **请求下载**"。

若要返回到 "报告" 视图，请单击 " **查看报告**"。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
