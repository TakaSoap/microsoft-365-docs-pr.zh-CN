---
title: 在 Microsoft 365 Defender 中处理高级搜寻查询结果
description: 充分利用 Microsoft 365 Defender 中高级搜寻返回的查询结果
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， Microsoft 威胁防护， 可视化， 图表， 筛选器， 向下钻取
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3481190a615cfa8914b3623f09d4079468bd431f
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712110"
---
# <a name="work-with-advanced-hunting-query-results"></a>使用高级搜寻查询结果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

虽然可以 [构造高级搜寻](advanced-hunting-overview.md) 查询以返回非常精确的信息，但您也可以使用查询结果来进一步获得见解并调查特定活动和指示器。 您可以对查询结果执行以下操作：

- 以表或图表查看结果
- 导出表和图表
- 向下钻取到详细的实体信息
- 直接从结果调整查询或应用筛选器

## <a name="view-query-results-as-a-table-or-chart"></a>以表或图表查看查询结果
默认情况下，高级搜寻将查询结果显示为表格数据。 还可以显示与图表相同的数据。 高级搜寻支持以下视图：

| 视图类型 | 说明 |
| -- | -- |
| **Table** | 以表格格式显示查询结果 |
| **柱形图** | 将 x 轴上的一系列唯一项呈现为垂直条，其高度表示来自另一个字段的数值 |
| **堆积柱形图** | 将 x 轴上的一系列唯一项呈现为堆积垂直条，其高度表示来自一个或多个其他字段的数值 |
| **饼图** | 呈现表示唯一项的部分饼图。 每个饼图的大小表示来自另一个字段的数值。 |
| **Donut 图表** | 呈现表示唯一项的弧形。 每个弧的长度表示另一个字段的数值。 |
| **折线图** | 绘制一系列唯一项的数值并连接绘制的值 |
| **散点图** | 绘制一系列唯一项的数值 |
| **面积图** | 绘制一系列唯一项的数值并填充绘制值下方的部分 |

### <a name="construct-queries-for-effective-charts"></a>构造有效图表的查询
呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。 若要获取有意义的图表，请构造查询以返回您希望可视化的特定值。 下面是一些示例查询和生成的图表。

#### <a name="alerts-by-severity"></a>按严重性表示的警报
使用 `summarize` 运算符可获取要绘制图表的值的数值计数。 下面的查询使用 `summarize` 运算符按严重性获取警报数。

```kusto
AlertInfo
| summarize Total = count() by Severity
```
呈现结果时，柱形图将每个严重性值显示为单独的列：

![显示为柱形图的高级搜寻查询结果的图像（按严重性显示为柱形图的警报 ](../../media/advanced-hunting-column-chart.jpg)
 *查询结果）*

#### <a name="alert-severity-by-operating-system"></a>按操作系统的警报严重性
您还可以使用运算符 `summarize` 为来自多个字段的图表值准备结果。 例如，你可能希望了解警报严重性如何在操作系统和操作系统 (分布) 。 

下面的查询使用运算符从表中拉取操作系统信息，然后用于计算列 `join` `DeviceInfo` `summarize` 和列 `OSPlatform` `Severity` 的值：

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
这些结果最好使用堆积柱形图进行可视化：

![按操作系统显示的警报和严重性显示为堆积图表的堆积图表查询结果的高级搜寻 ](../../media/advanced-hunting-stacked-chart.jpg)
 *查询结果的图像*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>跨前 10 个发件人域的网络钓鱼电子邮件
如果处理的值列表并不有限，可以使用运算符仅绘制具有最多实例 `Top` 的值的图表。 例如，若要获取具有网络钓鱼电子邮件最多的前十个发件人域，请使用以下查询：

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
使用饼图视图可有效显示顶部域的分布：

![显示为饼图饼图的高级搜寻查询结果的图像，该饼图显示网络钓鱼电子邮件 ](../../media/advanced-hunting-pie-chart.jpg)
 *在顶部发件人域之间的分布*

#### <a name="file-activities-over-time"></a>一段时间的文件活动
将运算符与函数一同使用，可以检查 `summarize` `bin()` 一段时间内是否涉及特定指示器的事件。 下面的查询按 30 分钟的间隔计算涉及文件的事件数，以显示与该文件相关的 `invoice.doc` 活动峰值：

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
下面的直线图清楚地突出显示了具有更多活动涉及的时间段 `invoice.doc` ： 

![高级搜寻查询结果的图像，显示为线形图表，显示一段时间涉及 ](../../media/advanced-hunting-line-chart.jpg)
 *文件的事件数*


## <a name="export-tables-and-charts"></a>导出表和图表
运行查询后，选择 **"导出** "将结果保存到本地文件。 所选视图确定结果的导出方式：

- **表视图** — 查询结果以表格形式导出为 Microsoft Excel 工作簿
- **任何图表** — 查询结果导出为呈现图表的 JPEG 图像

## <a name="drill-down-from-query-results"></a>从查询结果向下钻取
若要快速检查查询结果中的记录，请选择相应的行以打开 **"检查记录"** 面板。 面板基于所选记录提供以下信息：

- **资产** — 记录中 (邮箱、设备和用户) 资产汇总视图，其中丰富了可用信息，如风险和曝光级别
- **进程树** — 为包含进程信息的记录生成，并且使用可用的上下文信息进行扩充;通常，返回更多列的查询可能会导致进程树更丰富。
- **所有详细信息** - 记录中列的所有值  

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/inspect-record.png)

若要查看查询结果（如计算机、文件、用户、IP 地址或 URL）中特定实体的详细信息，请选择实体标识符以打开该实体的详细配置文件页。

## <a name="tweak-your-queries-from-the-results"></a>调整结果中的查询
右键单击结果集中的值以快速增强查询。 可以使用这些选项执行以下操作：

- 显式查找选定值 (`==`)
- 从查询中排除选定值 (`!=`)
- 获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with` 

![高级搜寻结果集](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>筛选查询结果
右侧显示的筛选器提供结果集的摘要。 每列都有其自己的部分，其中列出了该列找到的非重复值和实例数。

优化查询，选择要包含或排除的值上的或按钮，然后选择 `+` `-` "运行 **查询"。**

![高级搜寻筛选器的图像](../../media/advanced-hunting-filter.png)

应用筛选器以修改查询并运行查询后，将相应更新结果。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](custom-detections-overview.md)
