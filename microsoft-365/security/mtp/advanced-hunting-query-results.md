---
title: 在 Microsoft 365 Defender 中处理高级搜寻查询结果
description: 充分利用 Microsoft 365 Defender 中的高级搜寻返回的查询结果
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 自定义检测， 架构， kusto， microsoft 365， Microsoft 威胁防护， 可视化， 图表， 筛选器， 深化
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932300"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="502aa-104">使用高级搜寻查询结果</span><span class="sxs-lookup"><span data-stu-id="502aa-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="502aa-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="502aa-105">**Applies to:**</span></span>
- <span data-ttu-id="502aa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="502aa-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="502aa-107">虽然可以构造 [高级](advanced-hunting-overview.md) 搜寻查询以返回非常精确的信息，但您也可以使用查询结果来进一步深入了解和调查特定活动和指示器。</span><span class="sxs-lookup"><span data-stu-id="502aa-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="502aa-108">您可以对查询结果执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="502aa-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="502aa-109">以表格或图表查看结果</span><span class="sxs-lookup"><span data-stu-id="502aa-109">View results as a table or chart</span></span>
- <span data-ttu-id="502aa-110">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="502aa-110">Export tables and charts</span></span>
- <span data-ttu-id="502aa-111">向下钻取到详细的实体信息</span><span class="sxs-lookup"><span data-stu-id="502aa-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="502aa-112">直接从结果调整查询或应用筛选器</span><span class="sxs-lookup"><span data-stu-id="502aa-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="502aa-113">以表或图表查看查询结果</span><span class="sxs-lookup"><span data-stu-id="502aa-113">View query results as a table or chart</span></span>
<span data-ttu-id="502aa-114">默认情况下，高级搜寻将查询结果显示为表格数据。</span><span class="sxs-lookup"><span data-stu-id="502aa-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="502aa-115">还可以显示与图表相同的数据。</span><span class="sxs-lookup"><span data-stu-id="502aa-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="502aa-116">高级搜寻支持以下视图：</span><span class="sxs-lookup"><span data-stu-id="502aa-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="502aa-117">视图类型</span><span class="sxs-lookup"><span data-stu-id="502aa-117">View type</span></span> | <span data-ttu-id="502aa-118">说明</span><span class="sxs-lookup"><span data-stu-id="502aa-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="502aa-119">**Table**</span><span class="sxs-lookup"><span data-stu-id="502aa-119">**Table**</span></span> | <span data-ttu-id="502aa-120">以表格格式显示查询结果</span><span class="sxs-lookup"><span data-stu-id="502aa-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="502aa-121">**柱形图**</span><span class="sxs-lookup"><span data-stu-id="502aa-121">**Column chart**</span></span> | <span data-ttu-id="502aa-122">将 x 轴上的一系列唯一项呈现为垂直条，其高度代表另一个字段的数值</span><span class="sxs-lookup"><span data-stu-id="502aa-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="502aa-123">**堆积柱形图**</span><span class="sxs-lookup"><span data-stu-id="502aa-123">**Stacked column chart**</span></span> | <span data-ttu-id="502aa-124">将 x 轴上的一系列唯一项呈现为堆积垂直条，其高度代表来自一个或多个其他字段的数值</span><span class="sxs-lookup"><span data-stu-id="502aa-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="502aa-125">**饼图**</span><span class="sxs-lookup"><span data-stu-id="502aa-125">**Pie chart**</span></span> | <span data-ttu-id="502aa-126">呈现表示唯一项的节饼图。</span><span class="sxs-lookup"><span data-stu-id="502aa-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="502aa-127">每个饼图的大小表示另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="502aa-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="502aa-128">**Donut 图表**</span><span class="sxs-lookup"><span data-stu-id="502aa-128">**Donut chart**</span></span> | <span data-ttu-id="502aa-129">呈现表示唯一项的节弧。</span><span class="sxs-lookup"><span data-stu-id="502aa-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="502aa-130">每个弧的长度表示来自另一个字段的数值。</span><span class="sxs-lookup"><span data-stu-id="502aa-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="502aa-131">**折线图**</span><span class="sxs-lookup"><span data-stu-id="502aa-131">**Line chart**</span></span> | <span data-ttu-id="502aa-132">绘制一系列唯一项的数值并连接绘制的值</span><span class="sxs-lookup"><span data-stu-id="502aa-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="502aa-133">**散点图**</span><span class="sxs-lookup"><span data-stu-id="502aa-133">**Scatter chart**</span></span> | <span data-ttu-id="502aa-134">绘制一系列唯一项的数值</span><span class="sxs-lookup"><span data-stu-id="502aa-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="502aa-135">**面积图**</span><span class="sxs-lookup"><span data-stu-id="502aa-135">**Area chart**</span></span> | <span data-ttu-id="502aa-136">绘制一系列唯一项的数值并填充绘制值下方的部分</span><span class="sxs-lookup"><span data-stu-id="502aa-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="502aa-137">构造有效图表的查询</span><span class="sxs-lookup"><span data-stu-id="502aa-137">Construct queries for effective charts</span></span>
<span data-ttu-id="502aa-138">呈现图表时，高级搜寻会自动标识感兴趣的列和要聚合的数字值。</span><span class="sxs-lookup"><span data-stu-id="502aa-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="502aa-139">若要获取有意义的图表，请构造查询以返回您希望可视化的特定值。</span><span class="sxs-lookup"><span data-stu-id="502aa-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="502aa-140">下面是一些示例查询和生成的图表。</span><span class="sxs-lookup"><span data-stu-id="502aa-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="502aa-141">按严重性表示的警报</span><span class="sxs-lookup"><span data-stu-id="502aa-141">Alerts by severity</span></span>
<span data-ttu-id="502aa-142">使用 `summarize` 运算符获取要绘制图表的值的数值计数。</span><span class="sxs-lookup"><span data-stu-id="502aa-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="502aa-143">下面的查询使用 `summarize` 运算符按严重性获取警报数。</span><span class="sxs-lookup"><span data-stu-id="502aa-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="502aa-144">呈现结果时，柱形图将每个严重性值显示为单独的列：</span><span class="sxs-lookup"><span data-stu-id="502aa-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="502aa-145">![显示为柱形图的按严重性显示的警报的柱形图查询结果的高级搜寻 ](../../media/advanced-hunting-column-chart.jpg)
 *查询结果的图像，显示为柱形图*</span><span class="sxs-lookup"><span data-stu-id="502aa-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="502aa-146">按操作系统的警报严重性</span><span class="sxs-lookup"><span data-stu-id="502aa-146">Alert severity by operating system</span></span>
<span data-ttu-id="502aa-147">您还可以使用运算符 `summarize` 为来自多个字段的图表值准备结果。</span><span class="sxs-lookup"><span data-stu-id="502aa-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="502aa-148">例如，你可能希望了解警报严重性如何分布在操作系统和操作系统 (操作系统) 。</span><span class="sxs-lookup"><span data-stu-id="502aa-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="502aa-149">下面的查询使用运算符从表中拉取操作系统信息，然后用于计算列 `join` `DeviceInfo` `summarize` 和列 `OSPlatform` `Severity` 的值：</span><span class="sxs-lookup"><span data-stu-id="502aa-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="502aa-150">这些结果最好使用堆积柱形图进行可视化：</span><span class="sxs-lookup"><span data-stu-id="502aa-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="502aa-151">![显示为按操作系统显示的警报和严重性的堆叠图表查询结果的高级搜寻查询结果的图像，显示为堆积 ](../../media/advanced-hunting-stacked-chart.jpg)
 *图表*</span><span class="sxs-lookup"><span data-stu-id="502aa-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="502aa-152">跨前十个发件人域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="502aa-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="502aa-153">如果处理的值列表并不有限，可以使用运算符仅绘制包含最多实例 `Top` 的值的图表。</span><span class="sxs-lookup"><span data-stu-id="502aa-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="502aa-154">例如，若要获取具有网络钓鱼电子邮件最多的前十个发件人域，请使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="502aa-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
<span data-ttu-id="502aa-155">使用饼图视图可有效显示顶部域的分布：</span><span class="sxs-lookup"><span data-stu-id="502aa-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="502aa-156">![以饼图饼图显示高级搜寻查询结果的图像，显示钓鱼电子邮件在 ](../../media/advanced-hunting-pie-chart.jpg)
 *顶部发件人域中的分布*</span><span class="sxs-lookup"><span data-stu-id="502aa-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="502aa-157">一段时间的文件活动</span><span class="sxs-lookup"><span data-stu-id="502aa-157">File activities over time</span></span>
<span data-ttu-id="502aa-158">将 `summarize` 运算符与 `bin()` 函数一同使用，可以检查一段时间是否涉及特定指示器的事件。</span><span class="sxs-lookup"><span data-stu-id="502aa-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="502aa-159">下面的查询按 30 分钟的间隔计算涉及文件的事件，以显示与该文件相关的活动 `invoice.doc` 峰值：</span><span class="sxs-lookup"><span data-stu-id="502aa-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="502aa-160">下面的图表清楚地突出显示了具有更多活动的时间段，包括 `invoice.doc` ：</span><span class="sxs-lookup"><span data-stu-id="502aa-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="502aa-161">![高级搜寻查询结果的图像，显示为显示一段时间涉及文件的事件数的直线图表 ](../../media/advanced-hunting-line-chart.jpg)
 </span><span class="sxs-lookup"><span data-stu-id="502aa-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="502aa-162">导出表格和图表</span><span class="sxs-lookup"><span data-stu-id="502aa-162">Export tables and charts</span></span>
<span data-ttu-id="502aa-163">运行查询后，选择" **导出** "将结果保存到本地文件。</span><span class="sxs-lookup"><span data-stu-id="502aa-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="502aa-164">所选的视图确定结果的导出方式：</span><span class="sxs-lookup"><span data-stu-id="502aa-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="502aa-165">**表视图** — 查询结果以表格形式导出为 Microsoft Excel 工作簿</span><span class="sxs-lookup"><span data-stu-id="502aa-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="502aa-166">**任何图表** — 查询结果导出为呈现图表的 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="502aa-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="502aa-167">从查询结果向下钻取</span><span class="sxs-lookup"><span data-stu-id="502aa-167">Drill down from query results</span></span>
<span data-ttu-id="502aa-168">若要快速检查查询结果中的记录，请选择相应的行以打开 **"检查记录"** 面板。</span><span class="sxs-lookup"><span data-stu-id="502aa-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="502aa-169">面板根据所选记录提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="502aa-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="502aa-170">**资产** — 记录中 (邮箱、设备和用户) 资产汇总视图，其中丰富了可用信息，如风险和曝光级别</span><span class="sxs-lookup"><span data-stu-id="502aa-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="502aa-171">**进程树** — 为包含流程信息的记录生成，并且使用可用上下文信息进行扩充;通常，返回更多列的查询可以产生更丰富的进程树。</span><span class="sxs-lookup"><span data-stu-id="502aa-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="502aa-172">**所有详细信息** - 记录中列的所有值</span><span class="sxs-lookup"><span data-stu-id="502aa-172">**All details** — all the values from the columns in the record</span></span>  

![包含用于检查记录的面板的选定记录的图像](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="502aa-174">若要查看查询结果（如计算机、文件、用户、IP 地址或 URL）中特定实体的详细信息，请选择实体标识符以打开该实体的详细配置文件页。</span><span class="sxs-lookup"><span data-stu-id="502aa-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="502aa-175">调整结果中的查询</span><span class="sxs-lookup"><span data-stu-id="502aa-175">Tweak your queries from the results</span></span>
<span data-ttu-id="502aa-176">右键单击结果集中的值以快速增强查询。</span><span class="sxs-lookup"><span data-stu-id="502aa-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="502aa-177">可以使用这些选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="502aa-177">You can use the options to:</span></span>

- <span data-ttu-id="502aa-178">显式查找选定值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="502aa-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="502aa-179">从查询中排除选定值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="502aa-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="502aa-180">获取用于将值添加到查询的更高级运算符，如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="502aa-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![高级搜寻技术结果集](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="502aa-182">筛选查询结果</span><span class="sxs-lookup"><span data-stu-id="502aa-182">Filter the query results</span></span>
<span data-ttu-id="502aa-183">右侧显示的筛选器提供结果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="502aa-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="502aa-184">每列都有其自己的部分，其中列出了该列找到的非重复值和实例数。</span><span class="sxs-lookup"><span data-stu-id="502aa-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="502aa-185">通过选择要包含或排除的值上的或按钮，然后选择"运行查询"来 `+` `-` **优化查询**。</span><span class="sxs-lookup"><span data-stu-id="502aa-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高级搜寻筛选器的图像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="502aa-187">应用筛选器以修改查询并运行查询后，将相应更新结果。</span><span class="sxs-lookup"><span data-stu-id="502aa-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="502aa-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="502aa-188">Related topics</span></span>
- [<span data-ttu-id="502aa-189">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="502aa-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="502aa-190">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="502aa-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="502aa-191">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="502aa-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="502aa-192">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="502aa-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="502aa-193">了解架构</span><span class="sxs-lookup"><span data-stu-id="502aa-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="502aa-194">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="502aa-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="502aa-195">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="502aa-195">Custom detections overview</span></span>](custom-detections-overview.md)
