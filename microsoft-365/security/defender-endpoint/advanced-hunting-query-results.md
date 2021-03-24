---
title: 在 Microsoft Defender ATP 中处理高级搜寻查询结果
description: 充分利用 Microsoft Defender ATP 中的高级搜寻返回的查询结果
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 自定义检测， 架构， kusto， 可视化， 图表， 筛选器， 向下钻取
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8876eea8f8b1111a2039328296fbd7c2d50022cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056256"
---
# <a name="work-with-advanced-hunting-query-results"></a>使用高级搜寻查询结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

虽然你可以构造 [高级](advanced-hunting-overview.md) 搜寻查询以返回非常精确的信息，但您也可以使用查询结果来进一步获得见解并调查特定活动和指示器。 您可以对查询结果执行以下操作：

- 以表格或图表查看结果
- 导出表格和图表
- 向下钻取到详细的实体信息
- 直接从结果调整查询或应用筛选器

## <a name="view-query-results-as-a-table-or-chart"></a>以表或图表查看查询结果
默认情况下，高级搜寻将查询结果显示为表格数据。 还可以显示与图表相同的数据。 高级搜寻支持以下视图：

| 视图类型 | 说明 |
| -- | -- |
| **Table** | 以表格格式显示查询结果 |
| **柱形图** | 将 x 轴上的一系列唯一项呈现为垂直条，其高度代表另一个字段的数值 |
| **堆积柱形图** | 将 x 轴上的一系列唯一项呈现为堆积竖线，其高度代表来自一个或多个其他字段的数字值 |
| **饼图** | 呈现表示唯一项的节饼图。 每个饼图的大小表示来自另一个字段的数值。 |
| **Donut 图表** | 呈现表示唯一项的圆弧。 每个弧的长度表示来自另一个字段的数值。 |
| **折线图** | 绘制一系列唯一项的数值并连接绘制的值 |
| **散点图** | 绘制一系列唯一项的数值 |
| **面积图** | 绘制一系列唯一项的数值并填充绘制值下方的各部分 |

### <a name="construct-queries-for-effective-charts"></a>构造有效图表的查询
呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。 若要获取有意义的图表，请构造查询以返回您希望可视化的特定值。 下面是一些示例查询和生成的图表。

#### <a name="alerts-by-severity"></a>按严重性表示的警报
使用 `summarize` 运算符可获取要绘制图表的值的数值计数。 下面的查询使用 `summarize` 运算符按严重性获取警报数。

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
呈现结果时，柱形图将每个严重性值显示为单独的列：

![以柱形图显示的高级搜寻查询结果的图像 按严重性显示 ](images/advanced-hunting-column-chart.jpg)
 *为柱形图的警报查询结果*

#### <a name="alert-severity-by-operating-system"></a>按操作系统警报严重性
您还可以使用 运算符 `summarize` 为来自多个字段的图表值准备结果。 例如，你可能想要了解警报严重性如何在操作系统和操作系统之间 (分布) 。 

下面的查询使用运算符从表中拉取操作系统信息，然后使用 计算 `join` `DeviceInfo` 和 `summarize` 列中 `OSPlatform` `Severity` 的值：

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
使用堆积柱形图可以最好地可视化这些结果：

![以堆叠图表显示的高级搜寻查询结果的图像 按操作系统和严重性显示的警报查询结果显示为 ](images/advanced-hunting-stacked-chart.jpg)
 *堆积图表*

#### <a name="top-ten-device-groups-with-alerts"></a>具有警报的十大设备组
如果处理的值列表并不有限，可以使用 运算符仅绘制具有最多实例 `Top` 的值的图表。 例如，若要获取警报最多的前十个设备组，请使用以下查询：

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
使用饼图视图可有效显示顶部组的分布：

![以饼图饼图显示的高级搜寻查询结果的图像，该饼图显示 ](images/advanced-hunting-pie-chart.jpg)
 *警报在设备组的分布*

#### <a name="malware-detections-over-time"></a>一段时间的恶意软件检测
将 `summarize` 运算符与 `bin()` 函数一同使用，可以检查一段时间内是否涉及特定指示器的事件。 下面的查询以 30 分钟的间隔计算 EICAR 测试文件的检测次数，以显示该文件的检测峰值：

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
下面的线图清楚地突出显示了对测试恶意软件进行更多检测的时间段： 

![高级搜寻查询结果的图像，显示为显示一段时间测试恶意软件检测次数的线形图 ](images/advanced-hunting-line-chart.jpg)
 *的线形图*


## <a name="export-tables-and-charts"></a>导出表格和图表
运行查询后，选择 **"导出** "将结果保存到本地文件。 所选视图确定结果的导出方式：

- **表视图** — 查询结果以表格形式导出为 Microsoft Excel 工作簿
- **任何图表** — 查询结果导出为已呈现图表的 JPEG 图像

## <a name="drill-down-from-query-results"></a>从查询结果向下钻取
若要查看有关实体（如设备、文件、用户、IP 地址和 URL）详细信息，请在查询结果中单击实体标识符。 这将打开所选实体的详细配置文件页。

若要快速检查查询结果中的记录，请选择相应的行以打开"检查记录"面板。 面板根据所选记录提供以下信息：

- **资产** — 记录中发现 (、设备和用户的主要资产汇总) 丰富的可用信息，如风险和曝光级别
- **进程树** — 为包含流程信息的记录生成的图表，并且使用可用的上下文信息进行扩充;通常，返回更多列的查询可产生更丰富的进程树。
- **所有详细信息** — 列出记录中列的所有值

## <a name="tweak-your-queries-from-the-results"></a>调整结果中的查询
右键单击结果集中的值以快速增强查询。 可以使用这些选项执行以下操作：

- 显式查找选定值 (`==`)
- 从查询中排除选定值 (`!=`)
- 获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with` 

![高级搜寻设备结果集](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>筛选查询结果
右窗格中显示的筛选器提供列表的结果集。 每个列在窗格中都有自己的节，其中每个部分都列出了该列中找到的值以及实例数。

通过在要包含或排除的值上选择 或 按钮来优化 `+` `-` 查询。 然后选择"**运行查询"。**

![高级搜寻筛选器的图像](images/advanced-hunting-filter.png)

应用筛选器以修改查询并运行查询后，将相应更新结果。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [自定义检测概述](overview-custom-detections.md)
