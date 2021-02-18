---
title: 邮件流地图
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用安全与合规中心的邮件流仪表板中的邮件流映射可视化和跟踪邮件通过连接器和不使用连接器从组织流动的情况。 &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290581"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>安全与合规中心内&映射

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

安全 **与合规中心** 的邮件流 [](mail-flow-insights-v2.md)仪表板中的邮件 [流](https://protection.office.com)&可深入了解邮件在组织中如何流动。 您可以使用此信息了解模式、识别异常并修复出现问题。

![安全与合规中心的邮件流仪表板中的"邮件流&小组件](../../media/mfi-mail-flow-map-widget.png)

默认情况下，小部件在称为 *Sankey* 图表的图表中显示前一天的邮件流模式。 可以使用左箭头向左箭头和向右箭头显示不同 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 日期的信息。 每种颜色表示通过不同入站或出站连接器的邮件流 (或不使用连接器) 。 如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。

## <a name="report-view-for-the-mail-flow-map"></a>邮件流映射的报告视图

单击" **邮件流映射"** 小部件将进入 **邮件流映射** 报告。

以下图表可在以下报表视图：

- **显示数据：概述**：这基本上是小部件的较大视图。 如果将鼠标悬停在特定颜色上，将显示该类型的连接器的消息数。

  ![邮件流映射报告中的概述视图](../../media/mfi-mail-flow-map-report-overview.png)

- **显示数据：详细信息**：此视图显示有关连接器和目标域的详细信息。 列出顶级发件人和收件人域，其余域放在"其他 **"中**。 如果将鼠标悬停在特定颜色和节上，将显示消息数。

  ![邮件流映射报告中的详细信息视图](../../media/mfi-mail-flow-map-report-detail.png)

如果 **单击"筛选器**"报表视图，可以指定开始日期和 **结束日期的日期范围**。 

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

相关见解显示在邮件流映射下方（如果可用 (例如 [，修复](mfi-mail-loop-insight.md) 可能的邮件循环见解) 。

## <a name="details-table-view-for-the-mail-flow-map"></a>邮件流映射的详细信息表视图

如果单击 **视图中的"** 查看详细信息报表视图，将显示以下信息：

- "日期"
- **类别**
- **连接器/第三方服务提供商**
- **发件人/收件人域**
- **邮件计数**

如果在 **详细信息表** 视图中单击"筛选器"，可以指定开始日期和 **结束日期的日期范围**。 

如果选择行，则类似的详细信息将显示在一个飞出内容中：

![邮件流映射中详细信息表中的详细信息飞出](../../media/mfi-mail-flow-map-view-details-table-details.png)

若要将特定日期范围的报告通过电子邮件发送给一个或多个收件人，请单击"请求 **下载"。**

若要返回到报告视图，请单击"**查看报告"。**

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
