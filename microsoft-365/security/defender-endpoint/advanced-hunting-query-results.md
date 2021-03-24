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
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="d0537-104">使用高级搜寻查询结果</span><span class="sxs-lookup"><span data-stu-id="d0537-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0537-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d0537-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0537-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d0537-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="d0537-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="d0537-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0537-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d0537-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="d0537-109">虽然你可以构造 [高级](advanced-hunting-overview.md) 搜寻查询以返回非常精确的信息，但您也可以使用查询结果来进一步获得见解并调查特定活动和指示器。</span><span class="sxs-lookup"><span data-stu-id="d0537-109">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="d0537-110">您可以对查询结果执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0537-110">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="d0537-111">以表格或图表查看结果</span><span class="sxs-lookup"><span data-stu-id="d0537-111">View results as a table or chart</span></span>
- <span data-ttu-id="d0537-112">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="d0537-112">Export tables and charts</span></span>
- <span data-ttu-id="d0537-113">向下钻取到详细的实体信息</span><span class="sxs-lookup"><span data-stu-id="d0537-113">Drill down to detailed entity information</span></span>
- <span data-ttu-id="d0537-114">直接从结果调整查询或应用筛选器</span><span class="sxs-lookup"><span data-stu-id="d0537-114">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="d0537-115">以表或图表查看查询结果</span><span class="sxs-lookup"><span data-stu-id="d0537-115">View query results as a table or chart</span></span>
<span data-ttu-id="d0537-116">默认情况下，高级搜寻将查询结果显示为表格数据。</span><span class="sxs-lookup"><span data-stu-id="d0537-116">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="d0537-117">还可以显示与图表相同的数据。</span><span class="sxs-lookup"><span data-stu-id="d0537-117">You can also display the same data as a chart.</span></span> <span data-ttu-id="d0537-118">高级搜寻支持以下视图：</span><span class="sxs-lookup"><span data-stu-id="d0537-118">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="d0537-119">视图类型</span><span class="sxs-lookup"><span data-stu-id="d0537-119">View type</span></span> | <span data-ttu-id="d0537-120">说明</span><span class="sxs-lookup"><span data-stu-id="d0537-120">Description</span></span> |
| -- | -- |
| <span data-ttu-id="d0537-121">**Table**</span><span class="sxs-lookup"><span data-stu-id="d0537-121">**Table**</span></span> | <span data-ttu-id="d0537-122">以表格格式显示查询结果</span><span class="sxs-lookup"><span data-stu-id="d0537-122">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="d0537-123">**柱形图**</span><span class="sxs-lookup"><span data-stu-id="d0537-123">**Column chart**</span></span> | <span data-ttu-id="d0537-124">将 x 轴上的一系列唯一项呈现为垂直条，其高度代表另一个字段的数值</span><span class="sxs-lookup"><span data-stu-id="d0537-124">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="d0537-125">**堆积柱形图**</span><span class="sxs-lookup"><span data-stu-id="d0537-125">**Stacked column chart**</span></span> | <span data-ttu-id="d0537-126">将 x 轴上的一系列唯一项呈现为堆积竖线，其高度代表来自一个或多个其他字段的数字值</span><span class="sxs-lookup"><span data-stu-id="d0537-126">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="d0537-127">**饼图**</span><span class="sxs-lookup"><span data-stu-id="d0537-127">**Pie chart**</span></span> | <span data-ttu-id="d0537-128">呈现表示唯一项的节饼图。</span><span class="sxs-lookup"><span data-stu-id="d0537-128">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="d0537-129">每个饼图的大小表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="d0537-129">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="d0537-130">**Donut 图表**</span><span class="sxs-lookup"><span data-stu-id="d0537-130">**Donut chart**</span></span> | <span data-ttu-id="d0537-131">呈现表示唯一项的圆弧。</span><span class="sxs-lookup"><span data-stu-id="d0537-131">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="d0537-132">每个弧的长度表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="d0537-132">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="d0537-133">**折线图**</span><span class="sxs-lookup"><span data-stu-id="d0537-133">**Line chart**</span></span> | <span data-ttu-id="d0537-134">绘制一系列唯一项的数值并连接绘制的值</span><span class="sxs-lookup"><span data-stu-id="d0537-134">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="d0537-135">**散点图**</span><span class="sxs-lookup"><span data-stu-id="d0537-135">**Scatter chart**</span></span> | <span data-ttu-id="d0537-136">绘制一系列唯一项的数值</span><span class="sxs-lookup"><span data-stu-id="d0537-136">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="d0537-137">**面积图**</span><span class="sxs-lookup"><span data-stu-id="d0537-137">**Area chart**</span></span> | <span data-ttu-id="d0537-138">绘制一系列唯一项的数值并填充绘制值下方的各部分</span><span class="sxs-lookup"><span data-stu-id="d0537-138">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="d0537-139">构造有效图表的查询</span><span class="sxs-lookup"><span data-stu-id="d0537-139">Construct queries for effective charts</span></span>
<span data-ttu-id="d0537-140">呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。</span><span class="sxs-lookup"><span data-stu-id="d0537-140">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="d0537-141">若要获取有意义的图表，请构造查询以返回您希望可视化的特定值。</span><span class="sxs-lookup"><span data-stu-id="d0537-141">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="d0537-142">下面是一些示例查询和生成的图表。</span><span class="sxs-lookup"><span data-stu-id="d0537-142">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="d0537-143">按严重性表示的警报</span><span class="sxs-lookup"><span data-stu-id="d0537-143">Alerts by severity</span></span>
<span data-ttu-id="d0537-144">使用 `summarize` 运算符可获取要绘制图表的值的数值计数。</span><span class="sxs-lookup"><span data-stu-id="d0537-144">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="d0537-145">下面的查询使用 `summarize` 运算符按严重性获取警报数。</span><span class="sxs-lookup"><span data-stu-id="d0537-145">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
<span data-ttu-id="d0537-146">呈现结果时，柱形图将每个严重性值显示为单独的列：</span><span class="sxs-lookup"><span data-stu-id="d0537-146">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="d0537-147">![以柱形图显示的高级搜寻查询结果的图像 按严重性显示 ](images/advanced-hunting-column-chart.jpg)
 *为柱形图的警报查询结果*</span><span class="sxs-lookup"><span data-stu-id="d0537-147">![Image of advanced hunting query results displayed as a column chart](images/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="d0537-148">按操作系统警报严重性</span><span class="sxs-lookup"><span data-stu-id="d0537-148">Alert severity by operating system</span></span>
<span data-ttu-id="d0537-149">您还可以使用 运算符 `summarize` 为来自多个字段的图表值准备结果。</span><span class="sxs-lookup"><span data-stu-id="d0537-149">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="d0537-150">例如，你可能想要了解警报严重性如何在操作系统和操作系统之间 (分布) 。</span><span class="sxs-lookup"><span data-stu-id="d0537-150">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="d0537-151">下面的查询使用运算符从表中拉取操作系统信息，然后使用 计算 `join` `DeviceInfo` 和 `summarize` 列中 `OSPlatform` `Severity` 的值：</span><span class="sxs-lookup"><span data-stu-id="d0537-151">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
<span data-ttu-id="d0537-152">使用堆积柱形图可以最好地可视化这些结果：</span><span class="sxs-lookup"><span data-stu-id="d0537-152">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="d0537-153">![以堆叠图表显示的高级搜寻查询结果的图像 按操作系统和严重性显示的警报查询结果显示为 ](images/advanced-hunting-stacked-chart.jpg)
 *堆积图表*</span><span class="sxs-lookup"><span data-stu-id="d0537-153">![Image of advanced hunting query results displayed as a stacked chart](images/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="top-ten-device-groups-with-alerts"></a><span data-ttu-id="d0537-154">具有警报的十大设备组</span><span class="sxs-lookup"><span data-stu-id="d0537-154">Top ten device groups with alerts</span></span>
<span data-ttu-id="d0537-155">如果处理的值列表并不有限，可以使用 运算符仅绘制具有最多实例 `Top` 的值的图表。</span><span class="sxs-lookup"><span data-stu-id="d0537-155">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="d0537-156">例如，若要获取警报最多的前十个设备组，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="d0537-156">For example, to get the top ten device groups with the most alerts, use the query below:</span></span>

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
<span data-ttu-id="d0537-157">使用饼图视图可有效显示顶部组的分布：</span><span class="sxs-lookup"><span data-stu-id="d0537-157">Use the pie chart view to effectively show distribution across the top groups:</span></span>

<span data-ttu-id="d0537-158">![以饼图饼图显示的高级搜寻查询结果的图像，该饼图显示 ](images/advanced-hunting-pie-chart.jpg)
 *警报在设备组的分布*</span><span class="sxs-lookup"><span data-stu-id="d0537-158">![Image of advanced hunting query results displayed as a pie chart](images/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of alerts across device groups*</span></span>

#### <a name="malware-detections-over-time"></a><span data-ttu-id="d0537-159">一段时间的恶意软件检测</span><span class="sxs-lookup"><span data-stu-id="d0537-159">Malware detections over time</span></span>
<span data-ttu-id="d0537-160">将 `summarize` 运算符与 `bin()` 函数一同使用，可以检查一段时间内是否涉及特定指示器的事件。</span><span class="sxs-lookup"><span data-stu-id="d0537-160">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="d0537-161">下面的查询以 30 分钟的间隔计算 EICAR 测试文件的检测次数，以显示该文件的检测峰值：</span><span class="sxs-lookup"><span data-stu-id="d0537-161">The query below counts detections of an EICAR test file at 30 minute intervals to show spikes in detections of that file:</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="d0537-162">下面的线图清楚地突出显示了对测试恶意软件进行更多检测的时间段：</span><span class="sxs-lookup"><span data-stu-id="d0537-162">The line chart below clearly highlights time periods with more detections of the test malware:</span></span> 

<span data-ttu-id="d0537-163">![高级搜寻查询结果的图像，显示为显示一段时间测试恶意软件检测次数的线形图 ](images/advanced-hunting-line-chart.jpg)
 *的线形图*</span><span class="sxs-lookup"><span data-stu-id="d0537-163">![Image of advanced hunting query results displayed as a line chart](images/advanced-hunting-line-chart.jpg)
*Line chart showing the number of detections of a test malware over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="d0537-164">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="d0537-164">Export tables and charts</span></span>
<span data-ttu-id="d0537-165">运行查询后，选择 **"导出** "将结果保存到本地文件。</span><span class="sxs-lookup"><span data-stu-id="d0537-165">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="d0537-166">所选视图确定结果的导出方式：</span><span class="sxs-lookup"><span data-stu-id="d0537-166">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="d0537-167">**表视图** — 查询结果以表格形式导出为 Microsoft Excel 工作簿</span><span class="sxs-lookup"><span data-stu-id="d0537-167">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="d0537-168">**任何图表** — 查询结果导出为已呈现图表的 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="d0537-168">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="d0537-169">从查询结果向下钻取</span><span class="sxs-lookup"><span data-stu-id="d0537-169">Drill down from query results</span></span>
<span data-ttu-id="d0537-170">若要查看有关实体（如设备、文件、用户、IP 地址和 URL）详细信息，请在查询结果中单击实体标识符。</span><span class="sxs-lookup"><span data-stu-id="d0537-170">To view more information about entities, such as devices, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="d0537-171">这将打开所选实体的详细配置文件页。</span><span class="sxs-lookup"><span data-stu-id="d0537-171">This opens a detailed profile page for the selected entity.</span></span>

<span data-ttu-id="d0537-172">若要快速检查查询结果中的记录，请选择相应的行以打开"检查记录"面板。</span><span class="sxs-lookup"><span data-stu-id="d0537-172">To quickly inspect a record in your query results, select the corresponding row to open the Inspect record panel.</span></span> <span data-ttu-id="d0537-173">面板根据所选记录提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="d0537-173">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="d0537-174">**资产** — 记录中发现 (、设备和用户的主要资产汇总) 丰富的可用信息，如风险和曝光级别</span><span class="sxs-lookup"><span data-stu-id="d0537-174">**Assets** — A summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="d0537-175">**进程树** — 为包含流程信息的记录生成的图表，并且使用可用的上下文信息进行扩充;通常，返回更多列的查询可产生更丰富的进程树。</span><span class="sxs-lookup"><span data-stu-id="d0537-175">**Process tree** — A chart generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="d0537-176">**所有详细信息** — 列出记录中列的所有值</span><span class="sxs-lookup"><span data-stu-id="d0537-176">**All details** — Lists all the values from the columns in the record</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="d0537-177">调整结果中的查询</span><span class="sxs-lookup"><span data-stu-id="d0537-177">Tweak your queries from the results</span></span>
<span data-ttu-id="d0537-178">右键单击结果集中的值以快速增强查询。</span><span class="sxs-lookup"><span data-stu-id="d0537-178">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="d0537-179">可以使用这些选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0537-179">You can use the options to:</span></span>

- <span data-ttu-id="d0537-180">显式查找选定值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="d0537-180">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="d0537-181">从查询中排除选定值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="d0537-181">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="d0537-182">获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="d0537-182">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高级搜寻设备结果集](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="d0537-184">筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="d0537-184">Filter the query results</span></span>
<span data-ttu-id="d0537-185">右窗格中显示的筛选器提供列表的结果集。</span><span class="sxs-lookup"><span data-stu-id="d0537-185">The filters displayed in the right pane provide a summary of the result set.</span></span> <span data-ttu-id="d0537-186">每个列在窗格中都有自己的节，其中每个部分都列出了该列中找到的值以及实例数。</span><span class="sxs-lookup"><span data-stu-id="d0537-186">Every column has its own section in the pane, each of which lists the values found in that column, and the number of instances.</span></span>

<span data-ttu-id="d0537-187">通过在要包含或排除的值上选择 或 按钮来优化 `+` `-` 查询。</span><span class="sxs-lookup"><span data-stu-id="d0537-187">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude.</span></span> <span data-ttu-id="d0537-188">然后选择"**运行查询"。**</span><span class="sxs-lookup"><span data-stu-id="d0537-188">Then select **Run query**.</span></span>

![高级搜寻筛选器的图像](images/advanced-hunting-filter.png)

<span data-ttu-id="d0537-190">应用筛选器以修改查询并运行查询后，将相应更新结果。</span><span class="sxs-lookup"><span data-stu-id="d0537-190">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0537-191">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0537-191">Related topics</span></span>
- [<span data-ttu-id="d0537-192">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="d0537-192">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0537-193">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="d0537-193">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0537-194">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="d0537-194">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d0537-195">了解架构</span><span class="sxs-lookup"><span data-stu-id="d0537-195">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="d0537-196">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="d0537-196">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d0537-197">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="d0537-197">Custom detections overview</span></span>](overview-custom-detections.md)
