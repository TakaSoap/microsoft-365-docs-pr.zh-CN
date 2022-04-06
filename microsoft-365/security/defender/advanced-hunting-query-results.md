---
title: 使用高级搜寻查询结果Microsoft 365 Defender
description: 充分利用高级搜寻在Microsoft 365 Defender中返回的查询结果
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、搜索、查询、遥测、自定义检测、架构、kusto、可视化效果、图表、筛选器、向下钻取
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0bfec0b56a67b1242d8dfd76b845aa273a76d27e
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667243"
---
# <a name="work-with-advanced-hunting-query-results"></a>使用高级搜寻查询结果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

虽然可以构造 [高级搜寻](advanced-hunting-overview.md) 查询以返回精确信息，但还可以使用查询结果来获得进一步的见解并调查特定活动和指标。 可以对查询结果执行以下操作：

- 以表格或图表方式查看结果
- 导出表和图表
- 向下钻取到详细的实体信息
- 直接从结果中调整查询或应用筛选器

## <a name="view-query-results-as-a-table-or-chart"></a>以表或图表形式查看查询结果

默认情况下，高级搜寻将查询结果显示为表格数据。 还可以显示与图表相同的数据。 高级搜寻支持以下视图：

| 视图类型 | 说明 |
|--|--|
| **Table** | 以表格格式显示查询结果 |
| **柱形图** | 将 x 轴上的一系列唯一项呈现为垂直条，其高度表示来自另一个字段的数值 |
| **堆积柱形图** | 将 x 轴上的一系列唯一项呈现为堆积垂直条，其高度表示来自一个或多个其他字段的数字值 |
| **饼图** | 呈现表示唯一项的分区饼图。 每个饼图的大小表示来自另一个字段的数值。 |
| **甜甜圈图** | 呈现表示唯一项的分区弧线。 每个弧的长度表示来自另一个字段的数值。 |
| **折线图** | 绘制一系列唯一项的数值并连接绘图值 |
| **散点图** | 绘制一系列唯一项的数值 |
| **面积图** | 绘制一系列唯一项的数值，并填充绘图值下面的部分 |

### <a name="construct-queries-for-effective-charts"></a>为有效图表构造查询

呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。 若要获取有意义的图表，请构造查询以返回要看到可视化的特定值。 下面是一些示例查询和生成的图表。

#### <a name="alerts-by-severity"></a>按严重性列出的警报

使用运 `summarize` 算符获取要绘制图表的值的数值计数。 以下查询使用 `summarize` 运算符按严重性获取警报数。

```kusto
AlertInfo
| summarize Total = count() by Severity
```

呈现结果时，柱形图将每个严重性值显示为单独的列：

:::image type="content" source="../../media/advanced-hunting-column-chart-new.png" alt-text="在Microsoft 365 Defender门户中显示高级搜寻结果的图表示例" lightbox="../../media/advanced-hunting-column-chart-new.png":::
*按严重性查询警报的结果，显示为柱形图*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>跨十大发件人域网络钓鱼电子邮件

如果要处理的值列表不是有限值，则可以使用运 `Top` 算符仅绘制实例最多的值图表。 例如，若要获取网络钓鱼电子邮件最多的前 10 个发件人域，请使用以下查询：

```kusto
EmailEvents
| where ThreatTypes has "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```

使用饼图视图有效地显示跨顶级域的分布：

:::image type="content" source="../../media/advanced-hunting-pie-chart-new.png" alt-text="在Microsoft 365 Defender门户中显示高级搜寻结果的饼图" lightbox="../../media/advanced-hunting-pie-chart-new.png":::
*显示网络钓鱼电子邮件跨顶级发件人域分布的饼图*

#### <a name="file-activities-over-time"></a>随时间推移的文件活动
将运 `summarize` 算符与函数配合 `bin()` 使用，可以检查一段时间内涉及特定指示器的事件。 以下查询按 30 分钟间隔对涉及文件 `invoice.doc` 的事件进行计数，以显示与该文件相关的活动峰值：

```kusto
CloudAppEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```

下面的折线图清楚地突出显示了包含更多活动的时间段，涉及 `invoice.doc`以下内容：

:::image type="content" source="../../media/line-chart-a.png" alt-text="在Microsoft 365 Defender门户中显示高级搜寻结果的折线图" lightbox="../../media/line-chart-a.png":::
*显示一段时间内涉及文件的事件数的折线图*

## <a name="export-tables-and-charts"></a>导出表和图表

运行查询后，选择" **导** 出"以将结果保存到本地文件。 所选视图确定如何导出结果：

- **表视图** - 查询结果以表格形式导出为Microsoft Excel工作簿
- **任何图表** — 查询结果将导出为呈现图表的 JPEG 图像

## <a name="drill-down-from-query-results"></a>从查询结果向下钻取

若要快速检查查询结果中的记录，请选择相应的行以打开 **"检查记录** "面板。 该面板根据所选记录提供以下信息：

- **资产** -) 记录中找到的主要资产 (邮箱、设备和用户的汇总视图，其中扩充了可用信息，如风险和风险级别
- **所有详细信息** - 记录中列中的所有值

:::image type="content" source="../../media/results-inspect-record.png" alt-text="在Microsoft 365 Defender门户中使用面板检查记录的所选记录" lightbox="../../media/results-inspect-record.png":::

若要查看有关查询结果中特定实体（如计算机、文件、用户、IP 地址或 URL）的详细信息，请选择实体标识符以打开该实体的详细配置文件页。

## <a name="tweak-your-queries-from-the-results"></a>调整结果中的查询

选择 **"检查记录** "面板中任意列右侧的三个点。 可以使用这些选项执行以下操作：

- 显式查找选定值 (`==`)
- 从查询中排除选定值 (`!=`)
- 获取更高级的运算符，以便将值添加到查询，例如 `contains`， `starts with`以及 `ends with`

:::image type="content" source="../../media/work-with-query-tweak-query.png" alt-text="Microsoft 365 Defender门户中&quot;检查记录&quot;页上的&quot;操作类型&quot;窗格" lightbox="../../media/work-with-query-tweak-query.png":::

> [!NOTE]
> 本文中的某些表在Microsoft Defender for Endpoint可能不可用。 [启用Microsoft 365 Defender](m365d-enable.md)以使用更多数据源来搜寻威胁。 可以按照[从Microsoft Defender for Endpoint迁移高级搜寻查询](advanced-hunting-migrate-from-mde.md)中的步骤，将高级搜寻工作流从Microsoft Defender for Endpoint移动到Microsoft 365 Defender。

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)
