---
title: 邮件流地图
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全 & 合规中心中的"邮件流"仪表板中的"邮件流"映射，直观呈现和跟踪通过连接器（不使用连接器）在组织中往来的邮件流。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd8df34c9484b7a2b8aa2bdd57d160e22f71d247
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473796"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>安全与合规中心&流程图

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

安全 **与合规中心的**"邮件 [](mail-flow-insights-v2.md)流"仪表板中的"邮件流"[&可](https://protection.office.com)深入了解邮件在组织中如何流动。 您可以使用此信息了解模式、识别异常并修复发生的问题。

:::image type="content" source="../../media/mfi-mail-flow-map-widget.png" alt-text="安全与合规中心内&quot;邮件流&quot;仪表板中的&quot;邮件流&小组件" lightbox="../../media/mfi-mail-flow-map-widget.png":::

默认情况下，小部件在称为 *Sankey* 图表的图表中显示前一天的邮件流模式。 可以使用向左箭头 ![。](../../media/scc-left-arrow.png) 和向右箭头 ![显示](../../media/scc-right-arrow.png) 不同日期的信息。 每种不同的颜色表示通过不同入站或出站连接器的邮件流 (或不使用连接器) 。 如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。

## <a name="report-view-for-the-mail-flow-map"></a>邮件流映射的报告视图

单击" **邮件流映射"** 小组件将进入 **"邮件流映射"** 报告。

下表中提供了以下报表视图：

- **显示数据：概述**：这基本上是小部件的较大视图。 如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-overview.png" alt-text="邮件流映射报告中的概述视图" lightbox="../../media/mfi-mail-flow-map-report-overview.png":::

- **显示数据：详细信息**：此视图显示有关连接器和目标域的详细信息。 列出顶级发件人和收件人域，其余域放入"其他 **"中**。 如果将鼠标悬停在特定颜色和分区上，将显示消息数。

    :::image type="content" source="../../media/mfi-mail-flow-map-report-detail.png" alt-text="邮件流映射报告中的详细信息视图" lightbox="../../media/mfi-mail-flow-map-report-detail.png":::

如果 **单击"筛选器**"，报表视图"开始日期"和"结束日期"来指定 **日期范围**。

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"**。

相关见解显示在邮件流映射下方（如果它们 (例如， [修复可能的邮件循环见解](mfi-mail-loop-insight.md)）。

## <a name="details-table-view-for-the-mail-flow-map"></a>邮件流映射的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- **Date**
- **类别**
- **连接器/第三方服务提供商**
- **发件人/收件人域**
- **邮件计数**

如果在详细信息 **表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。

如果您选择一行，则类似的详细信息将显示在一个飞出内容中：

:::image type="content" source="../../media/mfi-mail-flow-map-view-details-table-details.png" alt-text="&quot;邮件流&quot;映射中详细信息表的&quot;详细信息&quot;飞出" lightbox="../../media/mfi-mail-flow-map-view-details-table-details.png":::

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"**。

若要返回到报告视图，请单击" **查看报告"**。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心内& [见解](mail-flow-insights-v2.md)。
