---
title: 使用 Microsoft 威胁防护中的高级搜寻查询结果
description: 在 Microsoft 威胁防护中充分利用高级搜寻返回的最多查询结果
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、自定义检测、架构、kusto、microsoft 365、Microsoft 威胁防护、可视化、图表、筛选器、向下钻取
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929100"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="7b202-104">使用高级搜寻查询结果</span><span class="sxs-lookup"><span data-stu-id="7b202-104">Work with advanced hunting query results</span></span>

<span data-ttu-id="7b202-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7b202-105">**Applies to:**</span></span>
- <span data-ttu-id="7b202-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="7b202-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7b202-107">虽然您可以构建[高级搜寻](advanced-hunting-overview.md)查询以返回精确的信息，但您也可以使用查询结果来进一步了解并调查特定活动和指标。</span><span class="sxs-lookup"><span data-stu-id="7b202-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="7b202-108">您可以对查询结果执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b202-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="7b202-109">以表或图表的形式查看结果</span><span class="sxs-lookup"><span data-stu-id="7b202-109">View results as a table or chart</span></span>
- <span data-ttu-id="7b202-110">导出表和图表</span><span class="sxs-lookup"><span data-stu-id="7b202-110">Export tables and charts</span></span>
- <span data-ttu-id="7b202-111">向下钻取到详细实体信息</span><span class="sxs-lookup"><span data-stu-id="7b202-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="7b202-112">直接从结果或应用筛选器中调整您的查询</span><span class="sxs-lookup"><span data-stu-id="7b202-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="7b202-113">以表或图表的形式查看查询结果</span><span class="sxs-lookup"><span data-stu-id="7b202-113">View query results as a table or chart</span></span>
<span data-ttu-id="7b202-114">默认情况下，高级搜寻将查询结果显示为表格数据。</span><span class="sxs-lookup"><span data-stu-id="7b202-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="7b202-115">您还可以显示与图表相同的数据。</span><span class="sxs-lookup"><span data-stu-id="7b202-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="7b202-116">高级搜寻支持以下视图：</span><span class="sxs-lookup"><span data-stu-id="7b202-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="7b202-117">视图类型</span><span class="sxs-lookup"><span data-stu-id="7b202-117">View type</span></span> | <span data-ttu-id="7b202-118">说明</span><span class="sxs-lookup"><span data-stu-id="7b202-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="7b202-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="7b202-119">**Table**</span></span> | <span data-ttu-id="7b202-120">以表格格式显示查询结果</span><span class="sxs-lookup"><span data-stu-id="7b202-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="7b202-121">**柱形图**</span><span class="sxs-lookup"><span data-stu-id="7b202-121">**Column chart**</span></span> | <span data-ttu-id="7b202-122">将 x 轴上的一系列唯一项呈现为垂直条，其高度表示来自另一个字段的数字值</span><span class="sxs-lookup"><span data-stu-id="7b202-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="7b202-123">**堆积柱形图**</span><span class="sxs-lookup"><span data-stu-id="7b202-123">**Stacked column chart**</span></span> | <span data-ttu-id="7b202-124">将 x 轴上的一系列唯一项呈现为堆积垂直条形图，其高度表示来自一个或多个其他字段的数字值</span><span class="sxs-lookup"><span data-stu-id="7b202-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="7b202-125">**饼形图**</span><span class="sxs-lookup"><span data-stu-id="7b202-125">**Pie chart**</span></span> | <span data-ttu-id="7b202-126">呈现表示唯一项的剖饼图。</span><span class="sxs-lookup"><span data-stu-id="7b202-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="7b202-127">每个饼图的大小代表另一个字段中的数字值。</span><span class="sxs-lookup"><span data-stu-id="7b202-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="7b202-128">**圆环图**</span><span class="sxs-lookup"><span data-stu-id="7b202-128">**Donut chart**</span></span> | <span data-ttu-id="7b202-129">呈现表示唯一项的剖弧形。</span><span class="sxs-lookup"><span data-stu-id="7b202-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="7b202-130">每个弧的长度表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="7b202-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="7b202-131">**折线图**</span><span class="sxs-lookup"><span data-stu-id="7b202-131">**Line chart**</span></span> | <span data-ttu-id="7b202-132">绘制一系列唯一项的数值，并连接绘制的值</span><span class="sxs-lookup"><span data-stu-id="7b202-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="7b202-133">**散点图**</span><span class="sxs-lookup"><span data-stu-id="7b202-133">**Scatter chart**</span></span> | <span data-ttu-id="7b202-134">绘制一系列唯一项的数值</span><span class="sxs-lookup"><span data-stu-id="7b202-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="7b202-135">**面积图**</span><span class="sxs-lookup"><span data-stu-id="7b202-135">**Area chart**</span></span> | <span data-ttu-id="7b202-136">绘制一系列唯一项的数值，并填充绘制值下面的部分</span><span class="sxs-lookup"><span data-stu-id="7b202-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="7b202-137">构建有效图表的查询</span><span class="sxs-lookup"><span data-stu-id="7b202-137">Construct queries for effective charts</span></span>
<span data-ttu-id="7b202-138">在呈现图表时，高级搜寻将自动标识感兴趣的列和要聚合的数值。</span><span class="sxs-lookup"><span data-stu-id="7b202-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="7b202-139">若要获取有意义的图表，请构建查询以返回您想要以可视化方式查看的特定值。</span><span class="sxs-lookup"><span data-stu-id="7b202-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="7b202-140">下面是一些示例查询和生成的图表。</span><span class="sxs-lookup"><span data-stu-id="7b202-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="7b202-141">按严重性的警报</span><span class="sxs-lookup"><span data-stu-id="7b202-141">Alerts by severity</span></span>
<span data-ttu-id="7b202-142">使用`summarize`运算符获取要绘制图表的值的数值计数。</span><span class="sxs-lookup"><span data-stu-id="7b202-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="7b202-143">下面的查询使用`summarize`运算符按严重性获取警报数。</span><span class="sxs-lookup"><span data-stu-id="7b202-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="7b202-144">呈现结果时，柱形图将每个严重性值显示为单独的列：</span><span class="sxs-lookup"><span data-stu-id="7b202-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="7b202-145">![高级搜索查询结果的图像显示为](../../media/advanced-hunting-column-chart.jpg)
*按严重性显示为柱形图的警报*的柱形图查询结果</span><span class="sxs-lookup"><span data-stu-id="7b202-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="7b202-146">警报严重性（按操作系统）</span><span class="sxs-lookup"><span data-stu-id="7b202-146">Alert severity by operating system</span></span>
<span data-ttu-id="7b202-147">您还可以使用`summarize`运算符为来自多个字段的图表值准备结果。</span><span class="sxs-lookup"><span data-stu-id="7b202-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="7b202-148">例如，您可能想要了解如何在操作系统（OS）之间分布警报严重性。</span><span class="sxs-lookup"><span data-stu-id="7b202-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="7b202-149">下面`join`的查询使用运算符从`DeviceInfo`表中提取 OS 信息，然后使用`summarize`对和`OSPlatform` `Severity`列中的值进行计数：</span><span class="sxs-lookup"><span data-stu-id="7b202-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="7b202-150">以下是使用堆积柱形图的最佳可视化效果：</span><span class="sxs-lookup"><span data-stu-id="7b202-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="7b202-151">![高级搜索查询结果的图像显示为](../../media/advanced-hunting-stacked-chart.jpg)
*按 OS 和严重性显示为堆叠图表的通知图表查询结果*</span><span class="sxs-lookup"><span data-stu-id="7b202-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="7b202-152">多个前十个发件人域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="7b202-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="7b202-153">如果要处理不有限的值列表，则可以使用`Top`运算符仅绘制具有最多实例的值。</span><span class="sxs-lookup"><span data-stu-id="7b202-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="7b202-154">例如，若要获取最多包含最多网络钓鱼电子邮件的前十个发件人域，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="7b202-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="7b202-155">使用饼图视图有效显示跨顶级域的分布：</span><span class="sxs-lookup"><span data-stu-id="7b202-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="7b202-156">![以饼图](../../media/advanced-hunting-pie-chart.jpg)
形式显示的高级搜索查询结果的图像，该饼图*显示了多发件人域之间的网络钓鱼电子邮件分布情况*</span><span class="sxs-lookup"><span data-stu-id="7b202-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="7b202-157">一段时间内的文件活动</span><span class="sxs-lookup"><span data-stu-id="7b202-157">File activities over time</span></span>
<span data-ttu-id="7b202-158">将`summarize`运算符与`bin()`函数结合使用，可以检查一段时间内涉及特定指示器的事件。</span><span class="sxs-lookup"><span data-stu-id="7b202-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="7b202-159">下面的查询按30分钟的间隔`invoice.doc`对涉及文件的事件进行计数，以显示与该文件相关的活动峰值：</span><span class="sxs-lookup"><span data-stu-id="7b202-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="7b202-160">下面的行图清晰突出显示了包含更多活动`invoice.doc`的时间段：</span><span class="sxs-lookup"><span data-stu-id="7b202-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="7b202-161">![高级搜索查询结果的图像显示为折线图图表](../../media/advanced-hunting-line-chart.jpg)
*折线图，显示有关一段时间内涉及文件的事件数*</span><span class="sxs-lookup"><span data-stu-id="7b202-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="7b202-162">导出表和图表</span><span class="sxs-lookup"><span data-stu-id="7b202-162">Export tables and charts</span></span>
<span data-ttu-id="7b202-163">运行查询后，选择 "**导出**" 将结果保存到本地文件。</span><span class="sxs-lookup"><span data-stu-id="7b202-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="7b202-164">您选择的视图将确定导出结果的方式：</span><span class="sxs-lookup"><span data-stu-id="7b202-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="7b202-165">**表视图**-以表格形式将查询结果导出为 Microsoft Excel 工作簿</span><span class="sxs-lookup"><span data-stu-id="7b202-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="7b202-166">**任何图表**—查询结果将导出为呈现的图表的 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="7b202-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="7b202-167">从查询结果中向下钻取</span><span class="sxs-lookup"><span data-stu-id="7b202-167">Drill down from query results</span></span>
<span data-ttu-id="7b202-168">若要查看有关查询结果中的实体（如计算机、文件、用户、IP 地址和 URL）的详细信息，只需单击实体标识符。</span><span class="sxs-lookup"><span data-stu-id="7b202-168">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="7b202-169">这将为 Microsoft Defender 安全中心中的所选实体打开详细的配置文件页。</span><span class="sxs-lookup"><span data-stu-id="7b202-169">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="7b202-170">调整结果中的查询</span><span class="sxs-lookup"><span data-stu-id="7b202-170">Tweak your queries from the results</span></span>
<span data-ttu-id="7b202-171">右键单击结果集中的值以快速增强查询。</span><span class="sxs-lookup"><span data-stu-id="7b202-171">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="7b202-172">可以使用这些选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b202-172">You can use the options to:</span></span>

- <span data-ttu-id="7b202-173">显式查找选定值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="7b202-173">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="7b202-174">从查询中排除选定值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="7b202-174">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="7b202-175">获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="7b202-175">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高级搜寻结果集的图像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="7b202-177">筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="7b202-177">Filter the query results</span></span>
<span data-ttu-id="7b202-178">右侧显示的筛选器提供结果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="7b202-178">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="7b202-179">每列都有其自己的部分，其中列出了该列找到的非重复值和实例数。</span><span class="sxs-lookup"><span data-stu-id="7b202-179">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="7b202-180">通过选择要包含或排除`+`的`-`值上的或按钮，然后选择 "**运行查询**" 来优化查询。</span><span class="sxs-lookup"><span data-stu-id="7b202-180">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高级搜寻筛选器的图像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="7b202-182">应用筛选器以修改查询并运行查询后，将相应更新结果。</span><span class="sxs-lookup"><span data-stu-id="7b202-182">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b202-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b202-183">Related topics</span></span>
- [<span data-ttu-id="7b202-184">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="7b202-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b202-185">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="7b202-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7b202-186">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="7b202-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7b202-187">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="7b202-187">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7b202-188">了解架构</span><span class="sxs-lookup"><span data-stu-id="7b202-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7b202-189">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="7b202-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7b202-190">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="7b202-190">Custom detections overview</span></span>](custom-detections-overview.md)
